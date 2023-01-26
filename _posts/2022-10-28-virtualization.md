---
layout: post
title: Virtual Computing
last_modified_at: 2022-10-28 22:30:00 +0300
categories: 
  - posts
tags:
  - virtualization
  - virtual machines
  - containers 
---
In the past, [physical servers](/wiki/hardware) functioned much like regular computers. The server was a physical machine on which the [operating system](/wiki/os) was installed and the applications on top of it. These types of servers are often referred to as ‘bare metal servers’, as there’s nothing in between the actual physical (metal) machine and the operating system. Usually, these servers were dedicated to one specific purpose, such as running one designated system.

While [virtualization technology](/wiki/virtualization) has existed since the 1960s, server virtualization started to take off in the early 2000s. Virtualization enables the deployment of multiple [virtual machines](/wiki/virtualization#virtual-machines), each with their own operating system, on one physical machine. This enabled significant savings and optimization for companies, and eventually led to the existence of cloud computing. For example, [AWS EC2](https://aws.amazon.com/ec2/) is a service that allows users to rent virtual machines on which they can run their own applications. EC2 that was launched in 2006 is the most popular AWS service today, and is probably the one which is most associated with public cloud. 

Without virtualization, cloud computing wouldn’t be a viable option. Virtualization allows the cloud provider to share physical machines between different customers and utilize them in an optimal manner. It means that instead of renting a full machine, each customer can use only a virtual part of the machine, which makes it financially beneficial for both the provider and the consumer. Furthermore, virtualization provides full isolation between computing environments of different customers, which makes this multi-tenant model secure. 

[Containers](/wiki/virtualization#containers) may seem like lightweight VMs, but they are not. Both of these tools provide isolation and run applications, but the underlying technologies are completely different. While the main purpose of VMs is to provide a fully isolated and secure compute environment on top of shared hardware resources, containers primarily allow fast and easy deployment of applications in the cloud. Developers can develop, run and test their application on a local machine, and then deploy it to the cloud, packaged in a container, without worrying about the dependencies in the remote machine. This is a main enabler for microservices and continuous delivery (CD). Containers simplify the deployment process and facilitate automation. With containers, a system can utilize the underlying hardware resources in a dynamic and optimal manner.

