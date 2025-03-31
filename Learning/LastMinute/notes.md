# Networking concepts

## TCP 3-way handshake
- Process used to establish connection between a client (your browser) and a server (google.com)
- sequence numbers here are used to track data packets transmitted during the connection

#### Step 1 >> SYN >> client to server
- src IP and port (client ip and port)
- dest IP and port (server ip and port)
- random client sequence number (ISN - initial sequence number)
#### Step 2 >> SYN-ACK >> server to client
- src IP and port (server ip and port)
- dest IP and port (client ip and port)
- client sequence number (ISN) + 1 (ack)
- random server sequence number (ISN)
#### Step 3 >> ACK >> client to server
- src IP and port (client ip and port)
- dest IP and port (server ip and port)
- server sequence number (ISN) + 1 (ack)

## TCP 4-way handshake
- Process used to terminate or teardown a TCP connection
- When a server/client sends a FIN packet, it means it does not have any more data to send
- This process helps maintain reliability and integrity of TCP connections
- Step 1 >> FIN >> client to server
- Step 2 >> ACK >> server to client
- Step 3 >> FIN >> server to client
- Step 4 >> ACK >> client to server

## What happens when I search something on Google?
### 1) DNS Resolution
- When you type "google.com" into your browser, first thing that your computer does is a DNS lookup (Domain Name System)
- DNS lookup >> Sends a DNS query to a DNS server (provided by internet provider)
- The DNS server translated "google.com" into corresponding IP address. This is essential because computers communicate using IP addresses and not domain names
### 2) TCP/IP Connection
- Browser establishes a TCP connection with the Google's server using resolved IP address
- TCP is reliable and connection oriented protocol ensuring correct data delivery in right order
- This connection typically uses 443 port for HTTPS (Hypertext Transfer Protocol Secure)
### 3) HTTP/HTTPS Request
- Your browser sends an HTTP request to Google's server containing your search query
- This request is formatted according to HTTP protocol (method, body headers etc)
### 4) Load Balancing
- Google uses load balancers to distribute incoming requests accross its massive network of servers
### 5) Google's data centers
- Google servers, located in data centers around the world. receive and process your request
### 6) DB query and Response
- Google's search algorithms query its massive DBs to find relevant results
- These results are formatted into HTTP response which is sent back to your browser
### 7) Packet Transmission
- The response from Google servers are broken down into small packets of data
- These packets are transmitted over internet using IP (internet Protocol)
- Routers along the way forward the packets to your computer's IP address
### 8) TCP Reassembly and Display
- Ypur computer's TCP stack reassembles the packets into complete HTTP response
- Your browser then renders the HTML, CSS and JavaScript in the response to display the search results on your screen
- The browser then may make further network requests to pull images or other resources as needed.

## OSI Model
Imagine sending a letter. The OSI (Open Systems Interconnection) model is like a set of rules that break down that process into seven simple steps, ensuring everyone understands how to send and receive information over a network. **(Please Do Not Throw Sausage Pizza Away)**

Here's a breakdown of the seven layers, from the bottom up:
### Physical Layer (Layer 1):
- This is the "hardware" layer.
- It deals with the actual cables, wires, and signals that transmit data.
- Think of it as the physical road the letter travels on.
### Data Link Layer (Layer 2):
- This layer handles the reliable transfer of data between two directly connected devices.
- It's like making sure the letter gets from one street to the next without getting lost.
- It handles things like MAC addresses.
### Network Layer (Layer 3):
- This layer handles routing data across multiple networks.
- It's like the postal service figuring out the best route for your letter to reach its destination.
- It handles IP addresses.
### Transport Layer (Layer 4):
- This layer ensures that data is delivered reliably and in the correct order.
- It's like making sure all the pages of your letter arrive in the right sequence.
- This is where TCP and UDP operate.
### Session Layer (Layer 5):
- This layer manages the "conversation" between two applications.
- It's like setting up and maintaining a phone call.
- It establishes, manages, and terminates connections.
### Presentation Layer (Layer 6):
- This layer translates data into a format that applications can understand.
- It's like translating a letter from one language to another.
- It handles data encryption and compression.
### Application Layer (Layer 7):
- This is the layer that users interact with.
- It's like the actual letter you write or the email you send.
- This is where HTTP, FTP, and other application protocols operate.

In essence, the OSI model provides a structured way to understand how data travels across a network, with each layer handling a specific aspect of the communication process.

## HTTP
- Language used by web browsers and web servers to talk to each other
- Works on **request-response** model
- **Text based** >> uses plain text to communicate
- **Stateless** >> Each request is treated independently. The server doesnt remember the previous request. This is why websited use cookies to maintain user information
- **Uses TCP** >> Relies on TCP to ensure reliable delivery of data
- **Action based** >> HTP defines specific actions that can be performed like GET, POST, PATCH, PUT

## TLS
- Stands for **Transport Layer Security**
- Protocol designed to provide communication security over a network
- Primarity used to encrypt communication between web browsers and web servers
- TLS uses **encryption** to scramble data and uses **authentication** to verify the identity of server using digital certificates.
- TLS is successor to SSL (Secure Sockets Layer)

## TLS Handshake
- User's browser connects to a website using HTTPS
- The server sends its digital certificate to the browser
- The browser checks the certificate
    - Checks if its issued by trusted CA
    - Checks if cert domain name matches website's domain 
    name
    - Uses the public key from certificate to encrypt data
- If cert is valid, browser and server establish a secure and encrypted connection
- All data exchanged between browser and server is encrypted using the public key of the certificate

# Linux commands

## free
Command used to display the amount of frewe and used system memory (RAM)
```
free -h    # human readable format
free -m    # in megabytes
free -g    # in gigabytes
free -s <x>    # update output every x seconds
free -t    # displays a "total" line at bottom (sum)
free -w    # more info about buffers and cache   
```

## ls
Command used for listing files and directories. Use **man ls** command to get documentation
```
-l    # (long listing format) gives lot of details
-a    # (all) lists all including hidden
-h    # (human-readable) file size will be GB, MB etc
-r    # (reverse) list in reverse order by letter or time
-t    # (time) list files sorted by time
-S    # (size) list files sorted by file size
-R    # (recursive) list the content of sub-dir as well
-d    # (directory) list dirs themselves
-i    # (inode) display inode no. of each file
-1    # (one) list one line per file (looks neat)
--color    # colors the output to distinguish file types
```

