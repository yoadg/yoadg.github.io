---
layout: page
title: Web Services
permalink: /wiki/web-services/
date: 2023-03-01
categories: 
  - interfaces
tags:
  - soap
  - rest
  - grpc
  - graphql
---

A web service is a generic name for a software system that supports interoperable machine-to-machine (M2M) interaction over a [computer network](/wiki/network). It allows distributed software applications to communicate and exchange data over the [Internet](/wiki/network#internet-protocol-suite), using Web protocols. A web service is typically based on a request-response model, where a server provides a set of functions that are hosted at a network addressable location, which can be remotely accessed by clients. A web technology such as [HTTP](/wiki/protocols#http) or [HTTPS](/wiki/protocols#https) is used for transferring machine-readable data formats such as XML and JSON. The protocol allows software programs written in a variety of programming languages and running on a variety of platforms to exchange data in a standardized and independent manner. This independence encourages web service based applications to be loosely coupled, component-oriented, cross-technology implementations. Web services can be used alone or with other web services to carry out a complex aggregation or a business transaction. 

Web services are based on the following principles:
- **Loosely Coupled** – The client and the web service are not bound to each other, which means that even if the web service changes over time, it should not change the way the client calls the web service. 
- **Synchronous and Asynchronous Operations** – In synchronous operations, the client blocks and waits for the web service to complete an operation. Asynchronous operations allow a client to invoke a service and then execute other functions in parallel. 
- **Remote Procedure Calls (RPC)** – Web services enable clients to invoke procedures, functions, and methods in a remote address space on the server side. Remote procedures expose a well-defined Application Programming Interface (API) that is accessible over the network.
- **Document Exchange** – XML and JSON can represent not only plain data but also structured documents. Web services support the transparent transfer of documents to facilitate business integration.

## API Protocols
An *Application Programming Interface (API)* is a set of defined rules that enable different applications to communicate with each other. It’s sometimes referred to as a contract between an information provider and an information user – establishing the content required from the consumer (the request) and the content required by the producer (the response).
It acts as an intermediary layer that processes data transfers between systems, letting companies open their application data and functionality to external third-party developers, business partners, and internal departments within their companies.

Traditionally, an API referred to an interface connected to a middleware, created with any of the low-level programming languages, such as C/C++, Java and Python. Such APIs are accessible within the application process through local procedure calling. Modern Web APIs however, are mostly remote, which means that they interact through a communication network to manipulate resources outside of the computer making the request. Web APIs are typically built on top of HTTP, resulting in developer-friendly interfaces that are easily accessible. 

In order to integrate applications quickly and at scale, APIs are realized using protocols and specifications to define the semantics and syntax of the messages passed across the wire. Several API protocols have been developed to facilitate standardized information exchange, such as:
- *The XML-Remote Procedure Call (XML-RPC)* protocol relies on a specific XML format to transfer data over HTTP. 
- *JSON-RPC* is a remote procedure call like XML-RPC, but JSON is used instead of XML to transfer data.
- *SOAP* (formerly the Simple Object Access Protocol) enables endpoints to send and receive data through XML over HTTP or SMTP. 
- *REpresentational State Transfer (REST)* is a set of web API architecture principles. 
- *GraphQL* is a data query language that uniquely allows clients to request any specific data that they need.
- *gRPC* is a high-performance, open-source RPC framework, which uses Protocol Buffers to serialize and parse data. 

### XML-RPC
**XML-RPC** is a simple protocol which permits programs to make function or procedure calls across a network over HTTP. It uses a small XML vocabulary to describe the nature of requests and responses. XML-RPC client specifies a procedure name and parameters in XML format, which is sent to the server in an HTTP POST request. The server returns either a fault or a response in XML format. XML-RPC parameters are a simple list of types and content – structs and arrays are the most complex types available. It has no notion of objects and no mechanism for including information that uses other XML vocabulary.

### JSON-RPC
**JSON-RPC** is a light-weight protocol that is similar to XML-RPC. It defines only a few data types and commands, which are serialized using the JSON format. Unlike XML-PRC, it allows for notifications (data sent to the server that does not require a response) and for multiple calls to be sent to the server which may be answered asynchronously. A JSON-RPC request contains the name of the method to be invoked, parameters that are passed to this method and optionally an ID that will be used to match the response. The response contains the result or error and the ID of the request. 

### SOAP
**SOAP** is a transport-independent messaging protocol for exchanging structured information in the form of SOAP Messages. It uses XML for its message format, and relies on application layer protocols, most often HTTP, although some legacy systems communicate over SMTP, for message negotiation and transmission.

A SOAP message is composed of:
- The envelope tag that begins and ends every message is the essential element that identifies an XML document as a SOAP message.
- The header is an optional element that can make it possible to add new features and functionalities using SOAP Modules.
- The body contains the actual message: the request or response.
- An optional fault tag informing of any errors that may occur throughout the request processing. 

SOAP supports both stateful and stateless operations. Stateful means that the server keeps the information that it receives from the client across multiple requests, which can be useful for operations involving multiple parties and complex transactions.

The SOAP API logic is written in *Web Service Description Language (WSDL)*, which provides information about the functionalities of any particular web service. This API description language defines the endpoints and describes all processes that can be performed. The importance of WSDL is that it allows developers and machines to analyze a web service that supports SOAP to learn about the nuances of information exchange over the network. Furthermore, the WSDL explains how to format the SOAP request and answer messages supported by the provided service.

The *Universal Description, Discovery, and Integration (UDDI)* specification defines a way to publish and discover information about SOAP services. UDDI provides a repository where WSDL files can be hosted and published, so that a client application can discover a WSDL file to learn about the various actions that a web service offers. As a result, the client application will have full access to the UDDI, which serves as a directory for all WSDL files.

### REST
**REST** is a software architectural style for developing APIs to provide a simple, uniform interface. These can be used to make data, content, algorithms, media, and other digital resources accessible via web URLs, allowing them to be consumed via the web, mobile, and device applications. REST is defined by a set of architectural constraints that makes use of existing and widely adopted technologies, specifically HTTP, and does not create any new standards. API developers can implement REST in a variety of ways. REST allows data exchange in simple machine-readable formats such as JSON and XML, but can also be used for other formats as well. 

RESTful architecture should comply with six architectural constraints:
- **Uniform interface**: A resource in the system should have only one logical URI, and that should provide a way to fetch related or additional data. Also, the resource representations across the system should follow specific guidelines such as naming conventions, link formats, or data format.
- **Stateless**: The necessary state to handle the request as contained within the request itself and without the server storing anything related to the session.
- **Cacheability**: Caching shall be applied to resources when applicable, and then these resources MUST declare themselves cacheable. 
- **Client-server architecture**: Client applications and server applications must be able to evolve separately without any dependency on each other.
- **Layered system**: RESTful systems have a multilayered structure in which each layer operates independently and interacts only with the layers directly connected to it.
- **Code on demand**: The ability for servers to provide executable code to the client (optional). 

RESTful web services communicate between applications using REST principles. Uniform interface means everything in RESTful web service is a resource. Resource can be a data, information or any block of data, which is accessed by a Uniform Resource Identifier (URI). RESTful web services make use of HTTP methods like GET, PUT, POST and DELETE to access a resource specified by the URI itself. However, while REST makes some suggestions about how HTTP transmissions should be formatted, there is no enforcement mechanis

## GraphQL
**GraphQL** is a query language and server-side runtime for APIs that prioritizes giving clients exactly the data they request and no more. It provides a web API approach in which clients define the structure of the data to be returned by the server. The client provides a query in the form of a string, which is then submitted to the server. The server processes the query and delivers the response to the client in JSON format. GraphQL allows users to request data from several resources using a single request. Rather than making multiple requests to fetch data, the client can use it to make ad-hoc queries to a single endpoint and access all the required data. GraphQL manipulates the data using queries, mutations (data updates), and subscriptions (update notifications).

GraphQL is a strongly typed language in which each level of a GraphQL query corresponds to a different type, and each type represents a different set of accessible fields. As a result, it is similar to SQL in that it offers informative error warnings prior to performing a query. GraphQL has a hierarchical structure in which relationships between objects are defined in a graph data model. Every object type represents a component in this context, and every related field from one object type to another represents a component wrapping another component. 

GraphQL starts with building a schema, which is a description of all the queries that can be done in a GraphQL API and all the types that they return. Having the schema before querying, a client can validate their query against making sure the server will be able to respond to it. On reaching the backend application, a GraphQL operation is interpreted against the entire schema, and resolved with data for the frontend application. Sending one massive query to the server, the API returns a JSON response with exactly the shape of the data that the client asked for. 

## gRPC
**gRPC** is a schema-driven RPC framework that brings performance benefits and modern features to client-server applications. It is a cross-platform, open-source, contract-based communication protocol that streamlines and controls interservice communication by providing a set of functions to remote clients. Built on top of HTTP/2, gRPC leverages features such as authentication, bidirectional streaming and flow control, blocking or nonblocking bindings, and cancellation and timeouts. It enables more efficient communication through serialized binary payloads. gRPC uses Protocol Buffers (Protobuf) by default as its mechanism for structured data serialization.

Protocol Buffers are more than just a serialized format. They are used as an *Interface Definition Language (IDL)* which defines the API interface (service definition). It serves as a contract between the client and the server, specifying the supported services, methods and messages (data structures). gRPC generates cross-platform client and server bindings for many languages. On the server side, the server implements the API interface and runs a gRPC server to handle client calls. On the client side, the client has a stub (referred to as just a client in some languages) that provides the same methods as the server.

There are 4 communication methods supported by gRPC:
- **Unary**: First, the client makes a single request to the server. Then, the server sends a single response.
- **Client-Streaming**: First, the client streams a series of requests to the server, followed by a message to inform that the stream is over. Finally, the server sends a single reply.
- **Server-Streaming**: First, the client makes a single request to the server. Then, the server sends a stream of messages to the client.
- **Bidirectional Streaming**: Both client and the server can send messages at any time after establishing the initial connection.
