# REST API

## What's an API?
An API is a set of definitions and protocols for building and integrating application software. It’s sometimes referred to as a contract between an information provider and an information user—establishing the content required from the consumer (the call) and the content required by the producer (the response). For example, the API design for a weather service could specify that the user supply a zip code and that the producer reply with a 2-part answer, the first being the high temperature, and the second being the low.  

In other words, if you want to interact with a computer or system to retrieve information or perform a function, an API helps you communicate what you want to that system so it can understand and fulfill the request. 

You can think of an API as a mediator between the users or clients and the resources or web services they want to get. It’s also a way for an organization to share resources and information while maintaining security, control, and authentication—determining who gets access to what. 

Another advantage of an API is that you don’t have to know the specifics of caching—how your resource is retrieved or where it comes from.


## What is REST?
REST is an acronym for REpresentational State Transfer and an architectural style for distributed hypermedia systems.
Roy Fielding first presented it in 2000 in his famous dissertation. Since then, it has become one of the most widely used appraches for building web-based APIs(Application Programming Interfaces). 

REST is not a protocol or a standard, it is an architectural style. During the development phase, API developers can implement REST in a variety of ways.
Like the other architectural styles, REST also has its guiding principles and constraits. These principles must be satisfied if a service interface is to be referred to as RESTful.

```
A Web API (or Web Service) conforming to the REST architectural style is called a REST API (or RESTful API)
```
1. **The Six Guiding Principles of REST**
At the most basic level, an API is a mechanism that enables an application or service to access a resource within another application, service or database. The application or service that accesses resources is the client and the application or service that contains the resource is the server.

Some APIs, such as SOAP or XML-RPC, impose a strict framework on developers. But developers can develop REST APIs by using virtually any programming language and support various data formats. The only requirement is that they align to the following six REST design principles, also known as architectural constraints.

REST is based on some constraints and priciples that promote simplicity, scalability, and statelessness in the design. The six guiding priniciples or constraints of the RESTful architecture are:

1.1. **Uniform Interface**

By applying the principle generality to the components interface, we can simplify the overall system architecture and improve the visibility of interactions. 

Multiple architectural constraints help in obtaining a uniform interface and guiding the behavior of components.

The following four constraints can achieve a uniform REST interface:

1. **Identification of resources** - The interface must uniquely identify each resource involved in the interaction between the client and the server.
2. **Manipulation of resources through representations** - The resources should have uniform representations in the server response. API consumers should use these representations to modify the resource state in the server.
3. **Self-descriptive messages** - Each resource represetation should carry enough information to describe how to process the message. It should also provide information on the additional actions that the client can perform on the resource.
4. **Hypermedia as the engine of application state** – The client should have only the initial URI of the application. The client application should dynamically drive all other resources and interactions with the use of hyperlinks.

In simpler words, REST defines a consistent and uniform interface for interactions between clients and servers. For example, the HTTP-based REST APIs make use of the standard HTTP methods (GET, POST, PUT, DELETE, etc.) and the URIs (Uniform Resource Identifiers) to identify resources.
   
1.2. **Client-Server**

The client-server design pattern enforces the separation of concerns, which helps the client and the server components evolve independently.

By separating the user interface concerns (client) from the data storage concerns(server), we improve the portability of the user interface across multiple platforms and improve scalability by simplifying the server components.

While the client and the server evolve, we have to make sure that the interface/contract between the client and the server does not break.
   
1.3. **Stateless**

Statelessness mandates that each request from the client to the server must contain all of the information necessary to understand and complete the request.

The server cannot take advantage of any previously stored context information on the server.

For this reason, the client application must entirely keep the session state.




         
5. **What is a Resource?**
6. **Resource Methods**
7. **REST and HTTP are Not the Same**
8. **Summary**




