- [Paramiko](#paramiko)
  - [Client Side](#client-side)
- [Schedule](#schedule)
  - [Using a decorator to schedule the job](#using-a-decorator-to-schedule-the-job)
  - [Passing arguments to the job](#passing-arguments-to-the-job)
  - [Retrieve all the jobs](#retrieve-all-the-jobs)
  - [Cancelling the job(s)](#cancelling-the-jobs)
  - [Running jobs until a certain time](#running-jobs-until-a-certain-time)
  - [How to run the thread in the background](#how-to-run-the-thread-in-the-background)
  - [Disadvantages](#disadvantages)
- [Logging](#logging)
  - [Why we need logger?](#why-we-need-logger)
  - [The Logging Module](#the-logging-module)
- [Basic Configurations](#basic-configurations)


# Paramiko

- **SSH** is the method typically used to access a remote machine and run commands, retrieve files or upload files.
- You can transfer files from the remote machine to the local or vice versa using **SFTP** (Secure File Transfer Protocol) and **SCP**(Secure Copy Protocol).
- The python **paramiko** model gives an abstraction of the **SSHv2** protocol with both the client side and server side functionality.
- As a **client**, you can authenticate yourself using a password or key and as a **server** you can decide which users are allowed accesss and the channels you allow

## Client Side

- The primary client of Paramiko is `Paramiko.SSHClient`. An instance of the `Paramiko.SSHClient` can be used to make connections to the remote server and transfer files
- `type(stdin)` and `type(stdout)` is `paramiko.channel.ChannelFile` , `type(stderr)` is class `paramiko.channel.ChannelStderrFile`. They are all python file like objects.
- The **stdin** is a write-only file which can be used for commands requiring input
- The **stdout** file give the output of the command
- The **stderr** gives the errors returned on executing the command. Will be empty if there is no error
- **File transfers** are handled by the `paramiko.SFTPClient` which you get from calling `open_sftp()` on an instance of `Paramiko.SSHClient`.

```python
## COMMANDS REQUIRING NO INPUT
import paramiko

command = "hostname"

host = "10.61.17.180"
username = "root"
password = "password"

client = paramiko.client.SSHClient()
clent.set_missing_host_key_policy(paramiko.AutoAddPolicy())
client.connect(host, username=username, password=password)
_stdin, _stdout, _stderr = client.exec_command(command)
print(_stdout.read().decode())
client.close()

######## OUTPUT
GUI.maa.nokia.com

```

```python
## COMMANDS REQUIRING INPUT
stdin, stdout, stderr = ssh.exec_command(“sudo ls”)
stdin.write(‘mypassword\n’)
print stdout.readlines()
```

```python
## FILE TRANSFERS
# Downloading a file from remote machine
ftp_client=ssh_client.open_sftp()
ftp_client.get(‘remotefileth’,’localfilepath’)
ftp_client.close()

# Uploading file from local to remote machine
ftp_client=ssh.open_sftp()
ftp_client.put(‘localfilepath’,remotefilepath’)
ftp_client.close()
```

# Schedule
- The **schedule** package is a simple and an elegant solution that can help you automate daily tasks such as sending mails, processing excel/csv,  etc. 
- schedule package is **not** what you need if you are looking for:
    - Job persistence (remember schedule between restarts)
    - Exact timing (sub-second precision execution)
    - Concurrent execution (multiple threads)
    - Localization (time zones, workdays, or holidays)
- If your requirement is to automate/schedule scripts in production, then I would recommend you explore **Apache-AirFlow** and **Apscheduler**.
- *schedule is a job scheduler well-suited for periodic tasks, preferably ones with relatively small intervals between executions*
- schedule package also provides some more features such as parallel execution, logging, exception handling, etc.

```python
import schedule
import time

def job():
    print("I'm working...")
    
schedule.every(5).seconds.do(job)

while True:
    schedule.run_pending()
    time.sleep(1)

###### OUTPUT
I'm working...
I'm working...
I'm working...
I'm working...
I'm working...
```

- Some more examples of scheduling python jobs:

```python
# Run the job to run every 5 minutes from now
schedule.every(5).minutes.do(job)

# Run the job to run every 5 hours from now
schedule.every(5).hours.do(job)

# Run the job to run every 5 days from now
schedule.every(5).days.do(job)

# Run the job to run every 5 weeks from now
schedule.every(5).weeks.do(job)

# Run job on a specific day & time of the week
schedule.every().monday.do(job)
schedule.every().sunday.at("06:00").do(job)

# Run job every day at specific HH:MM and next HH:MM:SS
schedule.every().day.at("10:30:00").do(job)
```

## Using a decorator to schedule the job
- We can also use **@repeat** decorator to schedule the jobs.

```python
from schedule import every, repeat, run_pending
import time

@repeat(every(5).seconds)
def job():
    print("Job scheduled using decorator...")

while True:
    run_pending()
    time.sleep(1)

#### OUTPUT
Job scheduled using decorator...
Job scheduled using decorator...
Job scheduled using decorator...
```

## Passing arguments to the job
- Sometimes you may want to pass the argument to the job. Since it’s a function we are scheduling, you can pass positional and keyword arguments as per your need.

```python
import time
import schedule

def job(type):
    if type == 'female':
        print('Hey lady')
    elif type == 'male':
        print('Hello mister')

schedule.every(1).seconds.do(job, type='female')
schedule.every(2).seconds.do(job, type='male')

while True:
    schedule.run_pending()
    time.sleep(1)

##### OUTPUT
Hey lady
Hello mister
Hey lady
Hey lady
Hello mister
Hey lady
Hey lady
Hello mister
Hey lady
```

## Retrieve all the jobs
- If you want to see all the jobs that are scheduled then you can use `get_jobs()` method. 

```python
import schedule

def job():
    print('Hello world')

schedule.every().second.do(job)
schedule.every().minute.do(job)
schedule.every().hour.do(job)

print(schedule.get_jobs())

###### OUTPUT
[Every 1 second do job() (last run: [never], next run: 2023-03-22 15:14:41),
Every 1 minute do job() (last run: [never], next run: 2023-03-22 15:15:40),
Every 1 hour do job() (last run: [never], next run: 2023-03-22 16:14:40)]
```

## Cancelling the job(s)
- You can cancel one or more jobs using `cancel_job(<job_name>)` and `clear()` methods respectively. 

```python
import schedule

def greet():
    print('Welcome !!!')

job1 = schedule.every().second.do(greet)
job2 = schedule.every().minute.do(greet)
job3 = schedule.every().hour.do(greet)

print('# of jobs scheduled', len(schedule.get_jobs()))

# Cancelling job1
print('Cancelling job-1....')
schedule.cancel_job(job1)
print('# of jobs scheduled', len(schedule.get_jobs()))

# Cancelling all jobs (job2 and job3)
print('Cancelling job-2 and job-3....')
schedule.clear()
print('# of jobs scheduled', len(schedule.get_jobs()))

###### OUTPUT
# of jobs scheduled 3
Cancelling job-1....
# of jobs scheduled 2
Cancelling job-2 and job-3....
# of jobs scheduled 0
```

## Running jobs until a certain time
- If you want to schedule the jobs to run until a certain time, you could use **until** method.

```python
import schedule
import time as t
from datetime import datetime, timedelta, time

def job():
    print('Welcomeeee')

# Run job until a 15:30 today
schedule.every(1).seconds.until("15:37").do(job)

# Run job until a 2030-01-01 18:33 today
schedule.every(2).hours.until("2024-10-31 23:59").do(job)

# Run job to run for the next 12 hours
schedule.every(3).hours.until(timedelta(hours=12)).do(job)

# Run my_job until today 23:59:59
schedule.every(4).hours.until(time(23, 59, 59)).do(job)

# Run job until a specific datetime
schedule.every(5).hours.until(datetime(2024, 12, 31, 23, 59, 59)).do(job)
print(schedule.get_jobs())

###### OUTPUT
[Every 1 second do job() (last run: [never], next run: 2023-03-22 15:36:57),
Every 2 hours do job() (last run: [never], next run: 2023-03-22 17:36:56),
Every 3 hours do job() (last run: [never], next run: 2023-03-22 18:36:56),
Every 4 hours do job() (last run: [never], next run: 2023-03-22 19:36:56),
Every 5 hours do job() (last run: [never], next run: 2023-03-22 20:36:56)]
```

## How to run the thread in the background
- In the above examples, the jobs you are scheduling are blocking the main thread. 
- To continuously run the scheduler in the background without blocking the main thread, we can create our own thread.
- In the below example, 
    - **run_continuously()** function creates a thread and returns threading event **cease_continuous_run**.
    - **background_job_1** and **background_job_2** are the two jobs that you want to run in the background without blocking the main thread.
    - In the main code, you are scheduling both the jobs to run every second.
    - Next, when **run_continuously()** function is called, it starts the thread for both the background jobs. The jobs will run in the background even when the main function is completed. Refer to the output shown below and you will understand. 
    - If you want you can also stop all the background jobs by running **stop_run_continuously.set()**.

```python
import schedule
import logging
import threading
import time

def run_continuously():
    cease_continuous_run = threading.Event()
    class ScheduleThread(threading.Thread):
        @classmethod
        def run(cls):
            while not cease_continuous_run.is_set():
                schedule.run_pending()
    continuous_thread = ScheduleThread()
    continuous_thread.start()
    return cease_continuous_run

def background_job_1():
    logging.info("Background 1 thread running...")

def background_job_2():
    logging.info("Background 2 thread running...")

if __name__ == "__main__":
    format = "%(asctime)s: %(message)s"
    logging.basicConfig(format=format, level=logging.INFO, datefmt="%H:%M:%S")
    logging.info("Main - starting thread")
    schedule.every().second.do(background_job_1)
    schedule.every().second.do(background_job_2)
    stop_run_continuously = run_continuously()
    logging.info("Main: completed !!")
    time.sleep(5)
    stop_run_continuously.set()

###### OUTPUT
22:39:29: Main - starting thread
22:39:29: Main: completed !!
22:39:30: Background 1 thread running...
22:39:30: Background 2 thread running...
22:39:31: Background 1 thread running...
22:39:31: Background 2 thread running...
22:39:32: Background 2 thread running...
22:39:32: Background 1 thread running...
22:39:33: Background 1 thread running...
22:39:33: Background 2 thread running...
22:39:35: Background 1 thread running...
22:39:35: Background 2 thread running...
```

## Disadvantages
- The main disadvantage with schedule package is that you need to keep your computer up and running all the time in order to run the scripts in the background. 
- This should not be a problem for non-production tasks but for production tasks you may have to create your own server or use some 3rd party cloud services.
- As mentioned earlier, schedule is not suited for the tasks that require job persistence, concurrent execution, localization, etc.

# Logging

## Why we need logger?
- Help develop a better understanding of the flow of a program
- Discover scenarios that you might not even have thought of while developing
- They can store information, like which user or IP accessed the application. 
- If an error occurs, then they can provide more insights than a stack trace by telling you what the state of the program was before it arrived at the line of code where the error occurred.
- By logging useful data from the right places, you can not only debug errors easily but also use the data to analyze the performance of the application

## The Logging Module

- With the logging module imported, you can use something called a “logger” to log messages that you want to see.
- By default, there are **5 standard levels** indicating the severity of events. Each has a corresponding method that can be used to log events at that level of severity. Below are the levels in **order of increasing severity**
  - DEBUG
  - INFO
  - WARNING
  - ERROR
  - CRITICAL
- The logging module provides you with a **default logger** that allows you to get started without needing to do much configuration.
- In below example, `root` is the name the `logging` module gives to its default logger. Default output format is  `level:name:message`. **Output format can be configured** to include things like timestamp, line number, and other details.
- By default, the logging module logs the messages with a severity level of **WARNING or above**. This can be changed by configuring the logging module to log events of all levels if you want.
- it's possible to define our **own severity levels** by changing configurations but its not recommended since it might create issues while using logger with third party applications
- 
```python
import logging

logging.debug('This is a debug message')
logging.info('This is an info message')
logging.warning('This is a warning message')
logging.error('This is an error message')
logging.critical('This is a critical message')

####### OUTPUT
WARNING:root:This is a warning message
ERROR:root:This is an error message
CRITICAL:root:This is a critical message
```

# Basic Configurations
- You can use the `basicConfig(**kwargs)` method to configure the logging.
- Some of the commonly used parameters for `basicConfig()` are the following:
    - `level`: The root logger will be set to the specified severity level.
    - `filename`: This specifies the file.
    - `filemode`: If filename is given, the file is opened in this mode. The default is a, which means append.
    - `format`: This is the format of the log message.

