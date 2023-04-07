---
layout: page
title: Data Serialization
permalink: /wiki/serialization/
date: 2023-04-07
categories: 
  - data
tags:
  - xml
  - json
  - yaml
---

Data which is used by computer programs can reside in three primary states: 
- **Data in use** – Active data under constant change, which is stored in a non-persistent digital state typically in computer [RAM](/wiki/hardware#main-memory), [CPU caches](/wiki/hardware#cache) or CPU registers.
- **Data in transit or motion** – Data that is being transferred from one location to another typically over a [computer network](/wiki/network).
- **Data at rest** – Inactive data which is stored physically on [computer data storage](/wiki/storage) (databases, files, object stores, etc.) in any digital form (structured or unstructured). 

The transformation of structured data in use to data in transit or at rest, is based on *data serialization*. It is the process of translating a data structure or object state into a standard data interchange format that can be stored or transmitted and reconstructed later (possibly in a different computer environment). The data in the serialized format can be stored in a file or database, or transmitted to another application or service over a network. When the resulting series of bits is reread according to the serialization format, it can be used to create a semantically identical clone of the original object. The reverse process of constructing a data structure or object from a series of bytes is called *deserialization*.

Serialization can be used for:
- Transferring data through the network (messaging);
- Remote Procedure Calls (RPC);
- Storing data in databases or files; 
- Distributing objects, especially in component-based software engineering such as COM, CORBA, etc.

The choice of data serialization format for an application depends on factors such as data complexity, need for human readability, speed and storage space constraints. Serializing the data structure in an architecture-independent format prevents the problems of byte ordering, memory layout, or simply different ways of representing data structures in different programming languages. Storing and exchanging data between varying environments requires a platform-and-language-neutral data format that all systems understand.

Serialization can be based on textual or binary formats. Text-based data formats such as XML, JSON and YAML can be easily viewed and edited in a text editor. It makes them ideal for human readability, but the downside is larger payload and slower processing. Binary data formats such as Protobuf, Avro and BSON are preferable for machine to machine (M2M) communication as they consume less space and are faster to process. It also leads to faster transmission times, especially over slower networks or when dealing with large amounts of data.

## Textual Data Serialization Formats
### CSV
A **Comma-Separated Values (CSV)** file is a delimited text file that uses a comma to separate values. Each line of the file is a flat data record. Each record consists of one or more fields, separated by commas. The use of the comma as a field separator is the source of the name for this file format, although other separators can be used as well. A CSV file typically stores tabular data (numbers and text) in plain text, in which case each line will have the same number of fields. It is ideal for exporting and importing data from/to database tables with a fixed schema. 

```
Abbreviation,Full Name,Type,Year
CSV,Comma Separated Values,Textual,1972
XML,Extensible Markup Language,Textual,1998
JSON,JavaScript Object Notation,Textual,2001
YAML,YAML Ain't Markup Language,Textual,2004
Protobuf,Protocol Buffers,Binary,2008
MessagePack,MessagePack,Binary,2008
Avro,Apache Avro,Binary,Binary,2009
BSON,Binary JSON,Binary,2016
```
*CSV example*

### XML
**Extensible Markup Language (XML)** is a hierarchical markup language and file format for storing, transmitting, and reconstructing arbitrary data. It defines a set of rules for encoding documents in a format that is both human-readable and machine-readable. The XML format is based on a set of symbols that can be placed in a document's text to organize it and label the different parts. It uses opening and closing tags to define data. Moreover, XML is extensible because the developer can freely create self-descriptive tags or languages. 

XML is known for being strict. An XML schema is a language that describes some rules and constraints on the structure of XML documents. XML schemas enforce consistency in how different software applications create and use XML files. Some industries implement XML schemas that are specific to their operations to reduce complexity in writing XML code for interbusiness data transfer. For example, Scalable Vector Graphics (SVG) is a standard XML specification for describing computer graphics-related data. Software developers write XML files so that they meet such industry specifications.

When a computer program reads data from an XML document, it usually parsers the data into a native data structure in memory. An XML parser is a software component that can process or read XML documents to extract the data within them (deserialization). XML parsers also check the syntax or rules of the XML file and can validate it against a particular XML schema. Because XML is a strict markup language, the parsers will not process the file if there are any validation or syntax errors. XML Parsers use the concept of a Document Object Model (DOM) to represent XML data. The DOM places XML data into a sort of "family tree" structure, starting from the root element and including each tag.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<serializationFormats>
  <textualFormats>
    <format abbreviation="CSV" year="1972">Comma Separated Values</format>
    <format abbreviation="XML" year="1998">Extensible Markup Language</format>
    <format abbreviation="JSON" year="2001">JavaScript Object Notation</format>
    <format abbreviation="YAML" year="2004">YAML Ain't Markup Language</format>
  </textualFormats>
  <binaryFormats>
    <format abbreviation="Protobuf" year="2008">Protocol Buffers</format>
    <format abbreviation="MessagePack" year="2008">MessagePack</format>
    <format abbreviation="Avro" year="2009">Apache Avro</format>
    <format abbreviation="BSON" year="2016">Binary JSON</format>
  </binaryFormats>
</serializationFormats>  
```
*XML example*

### JSON
**JavaScript Object Notation (JSON)** is a lightweight, text-based open standard of a human-readable data interchange format, which is used to store and transmit data objects consisting of name–value pairs. JSON is a common data format with diverse uses in electronic data interchange, including that of web applications with servers. RESTful web services use JSON extensively as the format for the data inside requests and responses.

JSON is a language-independent data sharing format. It was derived from JavaScript, but many modern programming languages include code to generate and parse JSON-format data. JSON offers a much more readable, human-friendly, compact and simple syntax which is faster to process, compared to XML. A JSON object is a collection of name–value pairs, where the value can be a string, a number, boolean (true/false) or a nested JSON object. It can also be an array of values with any number of elements (ordered list). 

```json
{
	"textualFromats": [{
		"abbreviation": "csv",
		"fullName": "Comma Separated Values",
		"year": 1972
	}, {
		"abbreviation": "xml",
		"fullName": "Extensible Markup Language",
		"year": 1998
	}, {
		"abbreviation": "json",
		"fullName": "JavaScript Object Notation",
		"year": 2001
	}, {
		"abbreviation": "yaml",
		"fullName": "YAML Ain't Markup Language",
		"year": 2004
	}],
	"binaryFormats": [{
		"abbreviation": "Protobuf",
		"fullName": "Protocol Buffers",
		"year": 2008
	}, {
		"abbreviation": "MessagePack",
		"fullName": "MessagePack",
		"year": 2008
	}, {
		"abbreviation": "Avro",
		"fullName": "Apache Avro",
		"year": 2009
	}, {
		"abbreviation": "BSON",
		"fullName": "Binary JSON",
		"year": 2016
	}]
}
```
*JSON example*

### YAML 
**YAML Ain't Markup Language (YAML)** is a human-readable data serialization format. It is commonly used for configuration files but can also be used as a format for data exchange between different programming languages. YAML targets many of the same communications applications as XML. It has a minimal syntax which is a strict superset of JSON, although it looks different. YAML has broad language support and maps easily into native data structures. It uses indentation to indicate hierarchy, which is similar to Python code indentation style. 

YAML supports a wide range of data types, including scalars (such as strings, numbers, and booleans), sequences (lists and arrays), and mappings (key-value pairs). It also supports comments, which can help make the code more readable and understandable for humans.

```yaml
---
textualFromats:
- abbreviation: csv
  fullName: Comma Separated Values
  year: 1972
- abbreviation: xml
  fullName: Extensible Markup Language
  year: 1998
- abbreviation: json
  fullName: JavaScript Object Notation
  year: 2001
- abbreviation: yaml
  fullName: YAML Ain't Markup Language
  year: 2004
binaryFormats:
- abbreviation: Protobuf
  fullName: Protocol Buffers
  year: 2008
- abbreviation: MessagePack
  fullName: MessagePack
  year: 2008
- abbreviation: Avro
  fullName: Apache Avro
  year: 2009
- abbreviation: BSON
  fullName: Binary JSON
  year: 2016
```
*YAML example*

## Binary Data Serialization Formats
### Protocol Buffers
**Protocol Buffers (Protobuf)** is a cross-platform, language-neutral and extensible data format used to serialize structured data. It is useful in developing programs to communicate with each other over a network or for storing data. Protocol buffers were designed to be faster than JSON and XML by removing many responsibilities performed by these formats and focusing solely on the ability to serialize and deserialize data as fast as possible. The method involves an Interface Description Language (IDL) that describes the structure of some data and a program that generates source code from that description for generating or parsing a stream of bytes that represents the structured data.

Protocol buffers allow to define the structure of data models once and then use generated source code to easily write and read structured data to/from a variety of data streams using a variety of languages. The structure of data models is defined in a protobuf IDL (.proto file) and compiled with protoc command which generates source code that can be invoked by a sender or recipient of these model structures. Each generated class contains simple accessors for each field and methods to serialize and parse the whole structure to and from raw bytes. The actual data is transmitted as binary. This improves the speed of transmission more than raw string because it consumes less space and bandwidth.

### Avro
**Avro** is a row-oriented data serialization framework developed within Apache's Hadoop project. It uses JSON for defining data types and serializes data in a compact binary format. Avro uses a schema to structure the data that is being encoded. It stores the data definition in JSON format making it easy to read and interpret; the data itself is stored in binary format making it compact and efficient. When Avro data is read, the schema used when writing it is always present. This permits each datum to be written with no per-value overheads, making serialization both fast and small. When Avro data is stored in a file, its schema is stored with it, so that files may be processed later by any program.

A key feature of Avro is robust support for data schemas that change over time – often called schema evolution. Avro handles schema changes like missing fields, added fields and changed fields; as a result, old programs can read new data and new programs can read old data.

### BSON
**Binary JSON (BSON)** is a lightweight, traversable and efficient data interchange format, which was created and internally used by MongoDB. It is a binary form for representing simple or complex data structures including associative arrays (also known as name-value pairs), integer indexed arrays, and a suite of fundamental scalar types. BSON also con­tains ex­ten­sions that al­low rep­res­ent­a­tion of data types that are not part of the JSON spec. BSON’s binary structure encodes type and length information, which allows it to be traversed much more quickly compared to JSON. 

### MessagePack
**MessagePack** is a binary data interchange format that is designed for data to be transparently converted from/to JSON. It supports a variety of data types, including integers, floats, booleans, strings, arrays, and maps. It also provides extensibility features that allow developers to define custom data types and encoding rules. MessagePack aims to be as fast, compact and simple as possible. It enables stream deserializer that can start deserializing the buffered data before all the data is received. Additionally, MessagePack is designed to be highly portable, meaning that it can be used across a wide range of programming languages and platforms.
