---
layout: post
title: Asynchronous Messaging
last_modified_at: 2023-06-28 11:30:00 +0300
categories: 
  - posts
tags:
  - message broker
  - event streaming platform
---

In the real world, asynchronous messaging is a communication method where participants on both sides of the conversation have the freedom to start, pause, and resume conversational messaging on their own terms, eliminating the need to wait for a direct live connection (aka synchronous messages).

In the realm of software systems, [Asynchronous Messaging](/wiki/messaging) is a communication pattern where messages are exchanged between components or services without requiring immediate responses. Instead of synchronous, tightly-coupled interactions (such as [Web Services](/wiki/web-services)), asynchronous messaging introduces a level of indirection, allowing the sending and receiving entities to operate independently and at their own pace. By decoupling sender and receiver, asynchronous messaging brings numerous benefits to complex software architectures, such as scalability, resilience and integration flexibility. 

A message broker is a middleware component that enables the exchange of messages between different systems or components. It acts as a centralized hub that receives messages from senders and routes them to the appropriate receivers based on predefined rules.

An event streaming platform is a more specialized and feature-rich system designed for handling high-volume, real-time event streams. It goes beyond the basic messaging capabilities of a message broker and provides additional functionalities specifically tailored for event-driven architectures. 
