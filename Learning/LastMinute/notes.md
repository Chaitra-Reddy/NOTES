- Networking concepts
  - [OSI Model](#osi-model)
  - [TCP/IP Model](#tcpip-model)
    - [Key Differences:](#key-differences)
      - [Number of Layers:](#number-of-layers)
      - [Focus:](#focus)
      - [Layer Functions:](#layer-functions)
      - [Adoption:](#adoption)
  - [TCP/IP vs OSI model](#tcpip-vs-osi-model)
  - [What happens layer wise when you google "cat facts" ?](#what-happens-layer-wise-when-you-google-cat-facts-)
    - [Application Layer (Your Browser):](#application-layer-your-browser)
    - [Presentation Layer:](#presentation-layer)
    - [Session Layer:](#session-layer)
    - [Transport Layer:](#transport-layer)
    - [Network Layer:](#network-layer)
    - [Data Link Layer:](#data-link-layer)
    - [Physical Layer:](#physical-layer)
  - [What happens when you generally search something on Google?](#what-happens-when-you-generally-search-something-on-google)
    - [1) DNS Resolution](#1-dns-resolution)
    - [2) TCP/IP Connection](#2-tcpip-connection)
    - [3) HTTP/HTTPS Request](#3-httphttps-request)
    - [4) Load Balancing](#4-load-balancing)
    - [5) Google's data centers](#5-googles-data-centers)
    - [6) DB query and Response](#6-db-query-and-response)
    - [7) Packet Transmission](#7-packet-transmission)
    - [8) TCP Reassembly and Display](#8-tcp-reassembly-and-display)
  - [Handshakes](#handshakes)
    - [TCP 3-way handshake](#tcp-3-way-handshake)
      - [Step 1 >> SYN >> client to server](#step-1--syn--client-to-server)
      - [Step 2 >> SYN-ACK >> server to client](#step-2--syn-ack--server-to-client)
      - [Step 3 >> ACK >> client to server](#step-3--ack--client-to-server)
    - [TCP 4-way handshake](#tcp-4-way-handshake)
  - [Protocols](#protocols)
    - [TCP (Transmission Control Protocol)](#tcp-transmission-control-protocol)
    - [UDP (User Datagram Protocol)](#udp-user-datagram-protocol)
    - [HTTP](#http)
    - [TLS (Transport Layer Security) (v1.3)](#tls-transport-layer-security-v13)
      - [What layer does it work on?](#what-layer-does-it-work-on)
      - [TLS Handshake](#tls-handshake)
  - [DNS](#dns)
    - [Step-by-step DNS Lookup](#step-by-step-dns-lookup)
      - [Browser Request:](#browser-request)
      - [Local DNS Cache Check:](#local-dns-cache-check)
      - [DNS Resolver Query:](#dns-resolver-query)
      - [Root Server Query:](#root-server-query)
      - [TLD Server Query:](#tld-server-query)
      - [Authoritative Name Server Query:](#authoritative-name-server-query)
      - [Resolver Response:](#resolver-response)
      - [Browser Connection:](#browser-connection)
    - [Common DNS record types:](#common-dns-record-types)
- Linux Commands
  - [free](#free)
  - [ls](#ls)
- Requests Library
  - [HTTP Methods](#http-methods)

# Networking concepts
## OSI Model
The Open Systems Interconnection (OSI) model is a conceptual framework that describes how network communication occurs. It has seven layers:


| Layer    |  Function   |  Data   | Whats in data? |
| --- | --- | --- | -- |
| Physical Layer |  Raw bit transmission over a physical medium. Deals with electrical signals, radio waves, or light pulses | Bits (0s and 1s). | It's the most basic form of data. |
| Data Link Layer | Handles local network communication, including framing, MAC addressing, and error control. Divides the bit stream into manageable chunks. | Frames | Includes headers (MAC address), payload (nw layer data), trailer (error check info) |
| Network Layer | Routes data packets between networks using IP addresses. Manages logical addressing and routing | Packet | Includes header (src and dst IP addr), payload (data from transport layer) |
| Transport Layer | Provides reliable (TCP) or unreliable (UDP) end-to-end data delivery. Manages segmentation and reassembly of data. | Segments (TCP) or Datagrams (UDP) | Includes header (src and dest port numbers, sequence numbers), payload (data from session layer) |
| Session Layer | Manages communication sessions between applications. Establishes, maintains, and terminates connections | Data is handled in form of session data | Session IDs, parameters, synchronization points etc. |
| Presentation Layer | Handles data formatting, encryption, and compression. Ensures data is in a format that the receiving application can understand | Data is presented in the format the application layer requires | This layer translates data. It may encrypt or compress the application layer data.|
| Application Layer | Provides network services to applications (HTTP, SMTP, etc.). This is the layer closest to the end user. | Application data | This is the data that the user interacts with (e.g., email messages, web pages, files). |

## TCP/IP Model
Fundamentally, both the TCP/IP and OSI models are conceptual frameworks that describe how different layers of networking protocols work together to enable communication. However, they differ in their structure and focus.
### Key Differences:
#### Number of Layers:
- The OSI model has seven layers, while the TCP/IP model has four.   
#### Focus:
- The OSI model is a more theoretical model, intended to provide a comprehensive framework for network communication.   
- The TCP/IP model is a more practical model, designed specifically for the implementation of the internet protocol suite.   
#### Layer Functions:
- Some layers in the OSI model are combined or have slightly different functions in the TCP/IP model. For example, the TCP/IP Application layer combines the functions of the OSI Application, Presentation, and Session layers. 
#### Adoption:
- The TCP/IP model is the model that the internet is built upon, and is the model that is used in practice. The OSI model is used more for educational purposes.

## TCP/IP vs OSI model
| TCP/IP Layer | OSI Layer | Key differences |
| -- | -- | -- |
| Network Access Layer | Physical and Data Link Layer | TCP/IP combines the physical transmission and local network addressing into one layer. OSI separates these functions. |
| Internet Layer | Network Layer | These layers are functionally very similar, both handling logical addressing (IP) and routing. |
| Transport Layer | Transport Layer | These layers are also functionally very similar, providing end-to-end communication (TCP, UDP). |
| Application Layer | Application Layer, Presentation Layer, Session Layer | TCP/IP combines the application-specific services, data formatting/translation, and session management into a single layer. OSI separates these functions. |


## What happens layer wise when you google "cat facts" ?
### Application Layer (Your Browser):
- You type "cat facts" into your browser's search bar and press Enter.
- Your browser (the application) creates an HTTP request, which is the data at this layer.
- This request is passed down to the Presentation Layer.
### Presentation Layer:
- The request is formatted for transmission. This might involve:
- Encoding the data into a standard format (e.g., UTF-8 [character encoding standard]).
- Encrypting the data (if it's an HTTPS request) for secure transmission.
- The formatted data is passed down to the Session Layer.
### Session Layer:
- A session is established between your browser and Google's web server.
- This layer manages the communication dialogue, ensuring that the request and response are properly handled.
- The session data is passed to the transport layer.
### Transport Layer:
- The data is broken into **segments** (if using TCP, which is typical for HTTP).
- Port numbers are added to the segments (e.g., port 80 for HTTP or 443 for HTTPS) to identify the browser and web server applications.
- Sequence numbers are added for reliable delivery.
- The segments (or datagrams if it was UDP) are passed down to the Network Layer.
### Network Layer:
- IP addresses are added to the segments, indicating your computer's IP address (source) and Google's web server's IP address (destination).
- The segments are now called **packets**.
- The packets are passed down to the Data Link Layer.
### Data Link Layer:
- MAC addresses are added to the packets, indicating your computer's network interface card (NIC) MAC address (source) and the MAC address of the next hop (e.g., your router).
- The packets are now called frames.
- Error-checking information (CRC) is added to the **frames**.
- The frames are passed down to the Physical Layer.
### Physical Layer:
- The frames are converted into a stream of **bits**.
- These bits are transmitted over the physical medium (e.g., Ethernet cable, Wi-Fi).
- The bits travel through your local network, to your internet service provider (ISP), and then across the internet to Google's servers.

</br>

>> Google's servers receive the bits, and the process is reversed. The bits are converted back into frames, packets, segments, and finally, application data. Google's servers process your search request and generate a response. The response data then travels back through the layers starting from physical layer.

## What happens when you generally search something on Google?
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

## Handshakes
### TCP 3-way handshake
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

### TCP 4-way handshake
- Process used to terminate or teardown a TCP connection
- When a server/client sends a FIN packet, it means it does not have any more data to send
- This process helps maintain reliability and integrity of TCP connections
- Step 1 >> FIN >> client to server
- Step 2 >> ACK >> server to client
- Step 3 >> FIN >> server to client
- Step 4 >> ACK >> client to server

## Protocols
### TCP (Transmission Control Protocol)
- **Reliable**: Guarantees data delivery.
- **Connection-oriented**: Establishes a connection first.
- **Ordered**: Data arrives in the correct sequence.
- **Slower**: Due to reliability checks.
- **Used for**: Web browsing, file transfer, email.

### UDP (User Datagram Protocol)
- **Unreliable**: Does not guarantee delivery.
- **Connectionless**: Sends data without establishing a connection.
- **Fast: Lower** overhead, faster transmission.
- **Out-of-order**: Packets may arrive in any sequence.
- **Used for**: Streaming, gaming, VoIP.

### HTTP
- Language used by web browsers and web servers to talk to each other
- Works on **request-response** model
- **Text based** >> uses plain text to communicate
- **Stateless** >> Each request is treated independently. The server doesnt remember the previous request. This is why websited use cookies to maintain user information
- **Uses TCP** >> Relies on TCP to ensure reliable delivery of data
- **Action based** >> HTP defines specific actions that can be performed like GET, POST, PATCH, PUT

### TLS (Transport Layer Security) (v1.3)
- TLS is successor to SSL (Secure Sockets Layer)
- **Security protocol**: Encrypts data for secure communication.
- **Ensures privacy**: Prevents eavesdropping.
- **Authentication**: Verifies the identity of the server.
- **Used with**: HTTPS (secure web browsing), email, and other applications.
- **Provides**: Confidentiality, integrity, and authentication.
#### What layer does it work on?
- TLS doesn't fit perfectly into a single layer
- TLS operates between the Transport Layer (TCP) and the Application Layer.
- **Transport Layer (TCP)**: TLS relies on TCP's reliable connection. TCP ensures that the encrypted data arrives in the correct order without errors.
- **Application Layer**: Applications like web browsers (HTTPS), email clients (SMTPS, IMAPS), and other secure communication tools use TLS to protect their data.
- **TLS's Role**: It takes the application data (e.g., HTTP requests, email messages) and encrypts it before it's passed down to TCP. It also decrypts the data received from TCP before passing it to the application.
#### TLS Handshake
- **Client Hello**: Your browser (the client) sends a "Client Hello" message to the website's server. This message includes the TLS version, supported encryption methods, and a random number.
- **Server Hello**: The server responds with a "Server Hello" message, which includes its chosen TLS version, encryption method, and its own random number. It also sends its digital certificate.
- **Certificate Verification**: Your browser verifies the server's certificate. This involves:
  - Checking if the certificate is issued by a trusted Certificate Authority (CA).
  - Verifying that the certificate's domain name matches the website's address.
  - Checking the certificate's expiration date.
- **Key Exchange**: Your browser generates a pre-master secret, encrypts it with the server's public key (from the certificate), and sends it to the server.
- **Session Key Generation**: Both the browser and the server use the random numbers and the pre-master secret to generate a shared secret key (the session key). This key will be used to encrypt and decrypt the actual data.
- **Encrypted Communication**: All subsequent data exchanged between the browser and the server is encrypted using the session key.

## DNS
- Stands for Domain Name System
- Essentially the internet's phonebook. Converts human-readable domain namnes into machine-readable IP addresses
### Step-by-step DNS Lookup
#### Browser Request:
- You type www.example.com into your browser's address bar and press Enter.
- Your browser needs the IP address of www.example.com to connect to the website's server.
#### Local DNS Cache Check:
- Your computer first checks its local DNS cache. It might have stored the IP address from a previous visit.
- If the IP address is found (and hasn't expired), the lookup stops here, and your browser connects to the server using the cached IP.
#### DNS Resolver Query:
- If the IP address isn't in your local cache, your computer sends a DNS query to your configured DNS resolver (usually your ISP's DNS server).
- This resolver will now take on the task of finding the correct IP.
#### Root Server Query:
- The resolver first contacts a root DNS server.
- Root servers don't know the IP of www.example.com directly, but they know the addresses of the TLD (Top-Level Domain) servers for .com.
- The root server responds with the addresses of the .com TLD servers.
#### TLD Server Query:
- The resolver then queries a .com TLD server.
- The .com TLD server knows the addresses of the authoritative name servers for the example.com domain.
- The .com TLD server responds with the addresses of the example.com authoritative name servers.
#### Authoritative Name Server Query:
- The resolver finally queries one of the example.com authoritative name servers.
- These servers hold the actual DNS records for the example.com domain, including the A record that maps www.example.com to its IP address.
- The authoritative name server responds with the IP address of www.example.com.
#### Resolver Response:
- The resolver receives the IP address from the authoritative name server.
- The resolver stores (caches) this IP address for a specified time (TTL - Time To Live) to speed up future lookups.
- The resolver sends the IP address back to your computer.
#### Browser Connection:
- Your computer receives the IP address.
- Your browser uses this IP address to establish a connection with the www.example.com server.
- The website's content is then displayed in your browser.

### Common DNS record types:
- A: IPv4 address.
- AAAA: IPv6 address.
- CNAME: Domain alias.
- MX: Mail server.
- NS: Name server.
- TXT: Text data.
- SOA: Zone info.
- PTR: IP to domain.
- SRV: Service location.

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

# Requests Library
Used to send HTTP requests to web serversd and receive their responses
## HTTP Methods
- GET: Retrieve data from server
- POST: Send data to a server to create or update a resource
- PUT: Replace an existing resource with new data
- DELETE: Remove a resource from a server
- PATCH: Apply partial modifications to a resource
- HEAD: Retrieve only the headers of a response
- OPTIONS: Get the communication options for a target resource

Basic example,
```
import requests
resp = requests.get("http://www.example.com")
if resp.status_code == 200:
    print("yayy")
else:
    print("Ou NOuu")
```

Request data,
- **url** >> str
- **params** >> dict >> query string parameters to add to URL
- **data** >> dict >> request body
- **json** >> dict >> request body
- **headers** >> dict >> custom headers
- **timeout** >> int >> no. of secs to wait before giving up
- **verify** >> bool >> to disable/enable SSL verification
- **cookies** >> dict or CookieJar >> send cookies with request
- **auth** >> tuple >> a tuple of username and password
- **allow_redirects** >> bool >> whether requests should follow redirects
- **proxies** >> dict >> specify proxies for the request
- **stream** >> bool >> when true the resp content is downloded immediately allowing you to stream large responses
- **cert** >> str or tuple >> specify client side cert as single file

Response data,
- **status_code** >> The HTTP status code
- **text** >> The response content as a string
- **content** >> The response content as bytes
- **json()** >> Parse response as json
- **headers** >> Dictionary of response headers
- **cookies** >> A *RequestCookieJar* of cookies sent back from the server
- **raise_for_status()** >> Raises an HTTPError for bad responses
