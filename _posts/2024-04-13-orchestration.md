---
layout: post
title: Kubernetes and other container orchestration tools  
last_modified_at: 2024-04-13 19:15:00 +0300
categories: 
  - posts
tags:
  - containers
  - Kubernetes
---

[Containers](/wiki/virtualization#containers) – and more specifically, containerized microservices or serverless functions – have become the de-facto compute standard of modern cloud-native applications. Containers are a method of packaging and isolating applications into standardized units that can be easily moved between environments. Unlike traditional [virtual machines (VMs)](/wiki/virtualization#virtual-machines) which virtualize an entire operating system, containers only virtualize the application layer, making them more lightweight, portable and efficient. Containers work hand in hand with modern cloud native development practices by making applications more portable, efficient, and scalable. 

In small numbers, containers are easy enough to deploy and manage manually. But as application architectures become more complex and the number of containers needed to maintain stability across a distributed system grows, managing them at scale is impossible without automation. The more containers you have, the harder it is to operate and manage them. This is where [container orchestration](/wiki/orchestration) comes into play. Container orchestration tools automates the deployment, management, scaling, and networking of containers.

In 2014, Google open-sourced a container orchestration system based on its learnings from its internal system - Borg, which managed the deployment of thousands of applications within Google. Since then, it is known as Kubernetes (K8s), a Greek word that means “helmsman” or “pilot”. K8s as an abbreviation results from counting the eight letters between the "K" and the "s". It is an open-source container orchestration platform that provides automated deployment, scaling, and management of containerized applications. The release of K8s marked the beginning of a revolutionary journey in the world of container orchestration.
