---
layout: post
title: Virtualization
last_modified_at: 2022-10-28 22:30:00 +0300
categories: 
  - posts
tags:
  - virtualization
  - virtual machines
  - containers 
---
[AWS EC2](https://aws.amazon.com/ec2/) was the first public cloud service that I used about ten years ago. It is a service that allows users to rent virtual machines on which they can run their own applications. EC2 that was launched in 2006 is the most popular AWS service today, and is probably the one which is most associated with public cloud. 

[Virtualization](/virtualization) is the fundamental technology that powers cloud computing. Without virtualization, cloud computing wouldn’t be a viable option. Virtualization allows the cloud provider to share physical machines between different customers and utilize them in an optimal manner. It means that instead of renting a full machine, each customer can use only a virtual part of the machine, which makes it financially beneficial for both the provider and the consumer. Furthermore, virtualization provides full isolation between computing environments of different customers, which makes this multi-tenant model secure. 

[Containers](/virtualization#containers) may seem like lightweight VMs, but they are not. Both of these tools provide isolation and run applications, but the underlying technologies are completely different. While the main purpose of VMs is to provide a fully isolated and secure compute environment on top of shared hardware resources, containers primarily allow fast and easy deployment of applications in the cloud. Developers can develop, run and test their application on a local machine, and then deploy it to the cloud, packaged in a container, without worrying about the dependencies in the remote machine. This is a main enabler for microservices and continuous delivery (CD). Containers simplify the deployment process and facilitate automation. With containers, a system can utilize the underlying hardware resources in a dynamic and optimal manner.

