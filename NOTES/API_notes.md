# What is a REST API?
- An **API**, or *application programming interface*, is a set of rules that define how applications or devices can connect to and communicate with each other. 
- A **REST API** is an API that conforms to the design principles of the **REST**, or **representational state transfer** architectural style. For this reason, REST APIs are sometimes referred to RESTful APIs.
- REST provides a relatively high level of **flexibility** and freedom for developers. This flexibility is just one reason why REST APIs have emerged as a common method for connecting components and applications in a microservices architecture.

# REST design principles
- At the most basic level, an **API** is a mechanism that enables an application or service to access a resource within another application or service. 
- The application or service doing the accessing is called the **client**, and the application or service containing the resource is called the **server**.
- Some APIs, such as SOAP or XML-RPC, impose a *strict framework* on developers. But REST APIs can be developed using virtually any programming language and support a variety of data formats. 
- The only requirement is that they align to the following *six REST design principles* - also known as *architectural constraints*:

1) **Uniform interface** - All API requests for the same resource should look the same, no matter where the request comes from. The REST API should ensure that the same piece of data, such as the name or email address of a user, belongs to only one uniform resource identifier (URI). Resources shouldn’t be too large but should contain every piece of information that the client might need.

2) **Client-server decoupling** - In REST API design, client and server applications must be completely independent of each other. The only information the client application should know is the URI of the requested resource; it can't interact with the server application in any other ways. Similarly, a server application shouldn't modify the client application other than passing it to the requested data via HTTP.

3) **Statelessness** - REST APIs are stateless, meaning that each request needs to include all the information necessary for processing it. In other words, REST APIs do not require any server-side sessions. Server applications aren’t allowed to store any data related to a client request.

Cacheability. When possible, resources should be cacheable on the client or server side. Server responses also need to contain information about whether caching is allowed for the delivered resource. The goal is to improve performance on the client side, while increasing scalability on the server side.