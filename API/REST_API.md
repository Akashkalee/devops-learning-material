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

1.4. **Cacheable**

The cacheable constraint requires that a response should implicitly or explicitly label itself as cacheable or non-cacheable.

If the response is cacheable, the client application gets the right to reuse the response data later for equivalent requests and a specified period.



1.5. **Layered System**

The layered system style allows an architecture to be composed of hierarchical layers by constraining component behavior. In a layered system, each component cannot see beyond the immediate layer they are interacting with.

A layman’s example of a layered system is the MVC pattern. The MVC pattern allows for a clear separation of concerns, making it easier to develop, maintain, and scale the application.

1.6. **Code on Demand (Optional)**

REST also allows client functionality to be extended by downloading and executing code in the form of applets or scripts.

The downloaded code simplifies clients by reducing the number of features required to be pre-implemented. Servers can provide part of the features delivered to the client in the form of code, and the client only needs to execute the code.

         
2. **What is a Resource?**

The key abstraction of information in REST is a resource. Any information that we can name can be a resource. For example, a REST resource can be a document or image, a temporal service, a collection of other resources, or a non-virtual object (e.g., a person).

The state of the resource at any particular time is known as the resource representation. The resource representations consist of:

- the data
- the metadata describing the data
- and the hypermedia links that can help the clients transition to the next desired state.

```
A REST API consists of an assembly of interlinked resources. This set of resources is known as the REST API’s resource model.
```
2.1. **Resource Identifiers**

REST uses resource identifiers to identify each resource involved in the interactions between the client and the server components.

2.2. **Hypermedia**

The data format of a representation is known as a media type. The media type identifies a specification that defines how a representation is to be processed.

A RESTful API looks like hypertext. Every addressable unit of information carries an address, either explicitly (e.g., link and id attributes) or implicitly (e.g., derived from the media type definition and representation structure).

```
Hypertext (or hypermedia) means the simultaneous presentation of information and controls such that the information becomes the affordance through which the user (or automaton) obtains choices and selects actions.

Remember that hypertext does not need to be HTML (or XML or JSON) on a browser. Machines can follow links when they understand the data format and relationship types.
```

2.3. **Self-Descriptive**

Further, resource representations shall be self-descriptive: the client does not need to know if a resource is an employee or a device. It should act based on the media type associated with the resource.

So in practice, we will create lots of custom media types – usually one media type associated with one resource.

Every media type defines a default processing model. For example, HTML defines a rendering process for hypertext and the browser behavior around each element.

```
Media Types have no relation to the resource methods GET/PUT/POST/DELETE/… other than the fact that some media type elements will define a process model that goes like “anchor elements with an href attribute create a hypertext link that, when selected, invokes a retrieval request (GET) on the URI corresponding to the CDATA-encoded href attribute.”
```

2.4. **Example**

Consider the following REST resource that represents a blog post with links to related resources in an HTTP-based REST API. This has the necessary information about the blog post, as well as the hypermedia links to the related resources such as author and comments. Clients can follow these links to discover additional information or perform actions.


```
{
  "id": 123,
  "title": "What is REST",
  "content": "REST is an architectural style for building web services...",
  "published_at": "2023-11-04T14:30:00Z",
  "author": {
    "id": 456,
    "name": "John Doe",
    "profile_url": "https://example.com/authors/456"
  },
  "comments": {
    "count": 5,
    "comments_url": "https://example.com/posts/123/comments"
  },
  "self": {
    "link": "https://example.com/posts/123"
  }
}
```



6. **Resource Methods**
7. **REST and HTTP are Not the Same**
8. **Summary**




