# What is a REST API?
- An **API**, or *application programming interface*, is a set of rules that define how applications or devices can connect to and communicate with each other. 
- A **REST API** is an API that conforms to the design principles of the **REST**, or **representational state transfer** architectural style. For this reason, REST APIs are sometimes referred to RESTful APIs.
- REST provides a relatively high level of **flexibility** and freedom for developers. This flexibility is just one reason why REST APIs have emerged as a common method for connecting components and applications in a microservices architecture.

# REST design principles
- At the most basic level, an **API** is a mechanism that enables an application or service to access a resource within another application or service. 
- The application or service doing the accessing is called the **client**, and the application or service containing the resource is called the **server**.
- Some APIs, such as SOAP or XML-RPC, impose a *strict framework* on developers. But REST APIs can be developed using virtually any programming language and support a variety of data formats. 
- The only requirement is that they align to the following *six REST design principles* - also known as *architectural constraints*:

1) **Uniform interface** - All API requests for the same resource should look the same, no matter where the request comes from. The REST API should ensure that the same piece of data, such as the name or email address of a user, belongs to only one uniform resource identifier (URI). Resources shouldn’t be too large but should contain every piece of information that the client might need. Uniform interface imposes four architectural constraints:
    **A)** Requests should identify resources. They do so by using a uniform resource identifier.
    **B)** Clients have enough information in the resource representation to modify or delete the resource if they want to. The server meets this condition by sending metadata that describes the resource further.
    **C)** Clients receive information about how to process the representation further. The server achieves this by sending self-descriptive messages that contain metadata about how the client can best use them.
    **D)** Clients receive information about all other related resources they need to complete a task. The server achieves this by sending hyperlinks in the representation so that clients can dynamically discover more resources.

2) **Client-server decoupling** - In REST API design, client and server applications must be completely independent of each other. The only information the client application should know is the URI of the requested resource; it can't interact with the server application in any other ways. Similarly, a server application shouldn't modify the client application other than passing it to the requested data via HTTP. *{ Client and server comm. should remain ame regardless of what type of client is there, example :tab, mobile, laptop etc }*

3) **Statelessness** - REST APIs are stateless, meaning that each request needs to include all the information necessary for processing it. In other words, REST APIs do not require any server-side sessions. Server applications aren’t allowed to store any data related to a client request.*{ Whenever client sends a request, the server will  never store any info regarding that request. Hence everytime the request should contain all the info that might be needed by the server }*

4) **Cacheability** - When possible, resources should be cacheable on the client or server side. Server responses also need to contain information about whether caching is allowed for the delivered resource. The goal is to improve performance on the client side, while increasing scalability on the server side. *{ cacheable means storing data in memory for fast retrieval }*

5) **Layered system architecture** - In REST APIs, the calls and responses go through different layers. As a rule of thumb, don’t assume that the client and server applications connect directly to each other. There may be a number of different intermediaries in the communication loop. REST APIs need to be designed so that neither the client nor the server can tell whether it communicates with the end application or an intermediary.*{ The client and server should not communicate directly. There should be some intermediate layers }*

6) **Code on demand (optional)** - REST APIs usually send static resources, but in certain cases, responses can also contain executable code (such as Java applets). In these cases, the code should only run on-demand.

# What are the benefits of RESTful APIs?

- **Scalability** - Systems that implement REST APIs can scale efficiently because REST optimizes client-server interactions. Statelessness removes server load because the server does not have to retain past client request information. Well-managed caching partially or completely eliminates some client-server interactions. All these features support scalability without causing communication bottlenecks that reduce performance.

- **Flexibility** - RESTful web services support total client-server separation. They simplify and decouple various server components so that each part can evolve independently. Platform or technology changes at the server application do not affect the client application. The ability to layer application functions increases flexibility even further. For example, developers can make changes to the database layer without rewriting the application logic.

- **Independence** - REST APIs are independent of the technology used. You can write both client and server applications in various programming languages without affecting the API design. You can also change the underlying technology on either side without affecting the communication.

# How do RESTful APIs work?

1) The client sends a request to the server. The client follows the API documentation to format the request in a way that the server understands.
2) The server authenticates the client and confirms that the client has the right to make that request.
3) The server receives the request and processes it internally.
4) The server returns a response to the client. The response contains information that tells the client whether the request was successful. The response also includes any information that the client requested.

# What components does the RESTful API client request contain?

## Unique resource identifier
- The server identifies each resource with unique resource identifiers. For REST services, the server typically performs resource identification by using a Uniform Resource Locator (URL). 
- The URL specifies the path to the resource. A URL is similar to the website address that you enter into your browser to visit any webpage. The URL is also called the request endpoint and clearly specifies to the server what the client requires.

## Method
Developers often implement RESTful APIs by using the Hypertext Transfer Protocol (HTTP). An HTTP method tells the server what it needs to do to the resource. The following are four common HTTP methods:
- **GET** : Clients use GET to access resources that are located at the specified URL on the server. They can cache GET requests and send parameters in the RESTful API request to instruct the server to filter data before sending.
- **POST** : Clients use POST to send data to the server. They include the data representation with the request. Sending the same POST request multiple times has the side effect of creating the same resource multiple times.
- **PUT** : Clients use PUT to update existing resources on the server. Unlike POST, sending the same PUT request multiple times in a RESTful web service gives the same result.
- **DELETE** : Clients use the DELETE request to remove the resource. A DELETE request can change the server state. However, if the user does not have appropriate authentication, the request fails.

## HTTP headers
Request headers are the metadata exchanged between the client and server. For instance, the request header indicates the format of the request and response, provides information about request status, and so on.

- **Data** : REST API requests might include data for the POST, PUT, and other HTTP methods to work successfully.

- **Parameters** : RESTful API requests can include parameters that give the server more details about what needs to be done. The following are some different types of parameters:
    - Path parameters that specify URL details.
    - Query parameters that request more information about the resource.
    - Cookie parameters that authenticate clients quickly.

# What are RESTful API authentication methods?
- A RESTful web service must authenticate requests before it can send a response. 
- **Authentication** is knowing the identity of the user. For example, Alice logs in with her username and password, and the server uses the password to authenticate Alice. **Authorization** is deciding whether a user is allowed to perform an action. For example, Alice has permission to get a resource but not create a resource.
- RESTful API has four common authentication methods:

1) **HTTP authentication** - HTTP defines some authentication schemes that you can use directly when you are implementing REST API. The following are two of these schemes:
    - *Basic authentication* : In basic authentication, the client sends the user name and password in the request header. It encodes them with base64, which is an encoding technique that converts the pair into a set of 64 characters for safe transmission.
    - *Bearer authentication* : The term bearer authentication refers to the process of giving access control to the token bearer. The bearer token is typically an encrypted string of characters that the server generates in response to a login request. The client sends the token in the request headers to access resources.

2) **API keys** - API keys are another option for REST API authentication. In this approach, the server assigns a unique generated value to a first-time client. Whenever the client tries to access resources, it uses the unique API key to verify itself. API keys are less secure because the client has to transmit the key, which makes it vulnerable to network theft.

3) **OAuth** - OAuth combines passwords and tokens for highly secure login access to any system. The server first requests a password and then asks for an additional token to complete the authorization process. It can check the token at any time and also over time with a specific scope and longevity.

# HTTP Status Codes
- **1XX** — Informational codes: The server acknowledges and is processing the request.
- **2XX** — Success codes: The server successfully received, understood, and processed the request.
- **3XX** — Redirection codes: The server received the request, but there’s a redirect to somewhere else (or, in rare cases, some additional action other than a redirect must be completed). 
- **4XX** — Client error codes: The server couldn’t find (or reach) the page or website. This is an error on the site’s side. 
- **5XX** — Server error codes: The client made a valid request, but the server failed to complete the request. 

<table>
<tbody><tr><td> <p><strong>Status Code</strong></p> </td><td> <p><strong>Function</strong></p> </td></tr><tr><td> <p>1XX — Informational</p> </td><td>&nbsp;</td></tr><tr><td> <p>100</p> </td><td> <p>Continue</p> </td></tr><tr><td> <p>101</p> </td><td> <p>Switching Protocols</p> </td></tr><tr><td> <p>102</p> </td><td> <p>Processing</p> </td></tr><tr><td> <p>103</p> </td><td> <p>Early Hints</p> </td></tr><tr><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td> <p>2XX — Success</p> </td><td>&nbsp;</td></tr><tr><td> <p>200</p> </td><td> <p>OK</p> </td></tr><tr><td> <p>201</p> </td><td> <p>Created</p> </td></tr><tr><td> <p>202</p> </td><td> <p>Accepted</p> </td></tr><tr><td> <p>203</p> </td><td> <p>Non-Authoritative Information</p> </td></tr><tr><td> <p>204</p> </td><td> <p>No Content</p> </td></tr><tr><td> <p>205</p> </td><td> <p>Reset Content</p> </td></tr><tr><td> <p>206</p> </td><td> <p>Partial Content</p> </td></tr><tr><td> <p>207</p> </td><td> <p>Multi-Status</p> </td></tr><tr><td> <p>208</p> </td><td> <p>Already Reported</p> </td></tr><tr><td> <p>226</p> </td><td> <p>IM Used</p> </td></tr><tr><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td> <p>3XX — Redirection</p> </td><td>&nbsp;</td></tr><tr><td> <p>300</p> </td><td> <p>Multiple Choices</p> </td></tr><tr><td> <p>301</p> </td><td> <p>Moved Permanently</p> </td></tr><tr><td> <p>302</p> </td><td> <p>Found</p> </td></tr><tr><td> <p>303</p> </td><td> <p>See Other</p> </td></tr><tr><td> <p>304</p> </td><td> <p>Not Modified</p> </td></tr><tr><td> <p>307</p> </td><td> <p>Temporary Redirect</p> </td></tr><tr><td> <p>308</p> </td><td> <p>Permanent Redirect</p> </td></tr><tr><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td> <p>4XX — Client Error</p> </td><td>&nbsp;</td></tr><tr><td> <p>400</p> </td><td> <p>Bad Request</p> </td></tr><tr><td> <p>401&nbsp;</p> </td><td> <p>Unauthorized</p> </td></tr><tr><td> <p>402</p> </td><td> <p>Payment Required</p> </td></tr><tr><td> <p>403</p> </td><td> <p>Forbidden</p> </td></tr><tr><td> <p>404</p> </td><td> <p>Not Found</p> </td></tr><tr><td> <p>405</p> </td><td> <p>Method Not Allowed</p> </td></tr><tr><td> <p>406</p> </td><td> <p>Not Acceptable</p> </td></tr><tr><td> <p>407</p> </td><td> <p>Proxy Authentication Required</p> </td></tr><tr><td> <p>408</p> </td><td> <p>Request Timeout</p> </td></tr><tr><td> <p>409</p> </td><td> <p>Conflict</p> </td></tr><tr><td> <p>410</p> </td><td> <p>Gone</p> </td></tr><tr><td> <p>411</p> </td><td> <p>Length Required</p> </td></tr><tr><td> <p>412</p> </td><td> <p>Precondition Failed</p> </td></tr><tr><td> <p>413</p> </td><td> <p>Content Too Large</p> </td></tr><tr><td> <p>414</p> </td><td> <p>URI Too Long</p> </td></tr><tr><td> <p>415</p> </td><td> <p>Unsupported Media Type</p> </td></tr><tr><td> <p>416</p> </td><td> <p>Range Not Satisfiable</p> </td></tr><tr><td> <p>417</p> </td><td> <p>Expectation Failed</p> </td></tr><tr><td> <p>421</p> </td><td> <p>Misdirected Request</p> </td></tr><tr><td> <p>422</p> </td><td> <p>Unprocessable Content</p> </td></tr><tr><td> <p>423</p> </td><td> <p>Locked</p> </td></tr><tr><td> <p>424</p> </td><td> <p>Failed Dependency</p> </td></tr><tr><td> <p>425</p> </td><td> <p>Too Early</p> </td></tr><tr><td> <p>426</p> </td><td> <p>Upgrade Required</p> </td></tr><tr><td> <p>428</p> </td><td> <p>Precondition Required</p> </td></tr><tr><td> <p>429</p> </td><td> <p>Too Many Requests</p> </td></tr><tr><td> <p>431</p> </td><td> <p>Request Header Fields Too Large</p> </td></tr><tr><td> <p>451</p> </td><td> <p>Unavailable for Legal Reasons</p> </td></tr><tr><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td> <p>5XX — Server Error</p> </td><td>&nbsp;</td></tr><tr><td> <p>500</p> </td><td> <p>Internal Server Error</p> </td></tr><tr><td> <p>501</p> </td><td> <p>Not Implemented</p> </td></tr><tr><td> <p>502</p> </td><td> <p>Bad Gateway</p> </td></tr><tr><td> <p>503</p> </td><td> <p>Service Unavailable</p> </td></tr><tr><td> <p>504</p> </td><td> <p>Gateway Timeout</p> </td></tr><tr><td> <p>505</p> </td><td> <p>HTTP Version Not Supported</p> </td></tr><tr><td> <p>506</p> </td><td> <p>Variant Also Negotiates</p> </td></tr><tr><td> <p>507</p> </td><td> <p>Insufficient Storage</p> </td></tr><tr><td> <p>508</p> </td><td> <p>Loop Detected</p> </td></tr><tr><td> <p>511</p> </td><td> <p>Network Authentication Required</p> </td></tr></tbody>
</table>











