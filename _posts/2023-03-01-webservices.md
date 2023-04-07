---
layout: post
title: Evolution of Remote Procedure Calls into Web Services
last_modified_at: 2023-03-01 12:30:00 +0300
categories: 
  - posts
tags:
  - rpc
  - soap
  - rest
  - graphql
  - grpc
---

As soon as computer networks emerged, software developers started building distributed applications. Initially these were simple client-server applications that communicated through proprietary application-level protocols over [TCP](/wiki/network#tcp) or [UDP](/wiki/network#udp) (using socket connections). But soon came the need of using services that are provided by 3rd party applications through public application programming interfaces (APIs). This need led to the development of standard [protocols](/wiki/protocols) for invoking remote APIs. These protocols have evolved into [Web Services](/wiki/web-services).

The notion of *Remote Procedure Calls (RPC)* emerged in the beginning of the 80’s. The idea was to implement request–response protocols for invoking procedures (subroutines) to be executed in a different context within a remote process. In 1991, the *Common Object Request Broker Architecture (CORBA)* was introduced. This system was put in place to ensure that applications built on various platforms could talk to each other. Five years later, Microsoft released the *Distributed Component Object Model (DCOM)* as a proprietary technology for communication between software components on networked computers. In 1997, Sun Microsystems released JDK 1.1, which included *Java Remote Method Invocation (Java RMI)*, a Java API that performs remote method invocation across different Java Virtual Machines (JVMs). In 1998, the *XML-RPC* protocol was created by Dave Winer. XML-RPC has evolved into the *Simple Object Access Protocol (SOAP)*, a messaging protocol specification for exchanging structured information in computer networks. SOAP introduced the concept of Web Services, where Internet protocols such as [HTTP](/wiki/protocols#http) are used for transferring machine-readable data formats such as XML and JSON.

In 2000, Roy Fielding wrote his dissertation and introduced the world to an architecture for distributed systems called “Representational State Transfer,” or *REST* for short. REST is the most popular API development technology in modern web development. In 2015, Facebook released *GraphQL*, an open-source data query and manipulation language for APIs, and a query runtime engine. A year later, Google released its implementation of RPC, known as *gRPC*, a performance-centric framework for enabling web communication between systems.


