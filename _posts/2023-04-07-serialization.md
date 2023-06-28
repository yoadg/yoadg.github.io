---
layout: post
title: Evolution of Data Serialization Formats
last_modified_at: 2023-04-07 22:00:00 +0300
categories: 
  - posts
tags:
  - csv
  - xml
  - json
  - yaml
  - protobuf
---

Computer programs need to read and write data, which is stored in databases or files, or transmitted as messages across the network. When data is exported from an in-memory representation into some sort of external media, it must be encoded. For simple data types such as plain text and numbers, encoding is straightforward. But it becomes complex when we need to deal with data structures such as objects, arrays (lists), trees and tables. Initially, data was structured in a proprietary manner per application. However, in order to allow interoperability, standard formats were required and this is where [data serialization](/wiki/serialization) comes into play. 

One of the first data serialization formats was CSV that was used in IBM Fortran machines from as early as 1972. The name CSV (Comma-Separated Values) itself is coined in the era of modern PCs, around 1983. In 1997, The term serialization was used in the context of data for the first time. Built-in support for language-specific serialization was introduced in the Java language: Serializable interface for built-in support and Externalizable interface for user-defined implementation. 

HTML that was introduced in 1991 came from Standard Generalized Markup Language (SGML) invented in the 1970s by IBM. In the late 1990s, the eXtensible Markup Language (XML) was introduced. Like SGML, XML is not itself a markup language, but a specification for the definition of markup languages. XML was an evolution from SGML – designed to provide a means to define, and to enforce, structured content. In 2001, Douglas Crockford sent the first JSON message. JSON quickly became popular and suppressed XML as the most widely used data serialization format. Yet Another Markup Language (YAML), which was first proposed by Clark Evans in 2001, was officially released in 2004. It was then repurposed as YAML Ain't Markup Language, a recursive acronym.

The above data serialization formats were text-based, making them human-readable and editable. However, in terms of efficiency, binary formats are smaller in data size and faster to process. In 2008, two binary serialization formats were introduced: MessagePack and Protocol Buffers by Google. In 2016 BSON was released as an independent data serialization format. It originated in 2009 at MongoDB for its internal use. 
