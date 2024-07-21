---
layout: post
title: Relational vs. NoSQL Databases 
last_modified_at: 2022-12-31 21:00:00 +0300
categories: 
  - posts
tags:
  - database
  - nosql
---

Most applications need to store and retrieve data. While [file systems](/wiki/storage#file-system) enable basic [data storage](/wiki/storage), they lack the ability to efficiently find, retrieve and update specific data items within files. The first [Database](/wiki/databases) was invented in 1961 at GE and included a data model, description language, and manipulation language (store, retrieve, modify, delete). In 1968 flat-file-based databases were introduced. Then the Hierarchical Database came into existence when IBM introduced its first database, IMS (Information Management System). In a hierarchical database, data is organized in a tree-like structure, with each parent node having multiple child nodes. This type of database was popular in the early days of computing, but it has since been largely replaced by more flexible and powerful database systems.

Relational databases were first commercialized in the late 1970s and early 1980s, with companies like Oracle and IBM being two of the early leaders in the space. A relational database is a type of database that stores data in the form of tables, with each table having a unique key that can be used to link it to other tables. This allows for more complex relationships between data to be represented and queried. A standard query language (SQL) has been developed to access relational databases. 

In recent years, there has been a rise in the use of *NoSQL* databases. NoSQL stands for "not only SQL” and these databases are designed to handle a wide variety of data types and structures, including large volumes of unstructured data. NoSQL databases do not use the traditional SQL language for querying data, and they are often more scalable and flexible than relational databases.

Some examples of NoSQL databases include MongoDB, Cassandra, and Redis. These databases are often used in situations where the data being stored does not fit neatly into a traditional relational database structure, or where the database needs to be able to handle a high volume of read and write operations.

*This post was written with the assistance of [CharGPT](https://chat.openai.com/)*