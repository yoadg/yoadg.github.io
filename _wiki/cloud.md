---
layout: page
title: Cloud Computing
permalink: /wiki/cloud/
date: 2023-01-01
categories: 
  - cloud
---
Cloud computing is a model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (e.g., [networks](/wiki/network), [servers](/wiki/hardware), [data storage](/wiki/storage), development tools, applications and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction. The resources are hosted at a remote data center managed by a *cloud service provider* (CSP) and are accessible as services over the [network](/wiki/network). It eliminates the need for companies to procure, configure, or manage resources themselves, and they only pay for what they use.

The term ‘cloud computing’ also refers to the technology that makes the cloud work. This includes some form of [virtualized](/wiki/virtualization) IT infrastructure – [servers](/wiki/hardware), [operating systems](/wiki/os), [networking](/wiki/network), and other infrastructure that’s abstracted, using special software, so that it can be pooled and divided irrespective of physical [hardware](/wiki/hardware) boundaries. For example, a single hardware server can be divided into multiple [virtual machines](/wiki/virtualization#virtual-machines).

The main characteristics of cloud computing are:
- **Resource pooling** – Computing resources in a cloud infrastructure platform are dynamically divided and allocated on demand. Since a cloud host’s physical machines are dynamically provisioned and shared between multiple clients (“tenants”), cloud hardware is thoroughly optimized for maximum usage.
- **On-demand self service** – Cloud computing providers offer APIs that users access to requisition new resources or scale existing resources whenever needed. It enables the client to constantly monitor the server uptime, abilities, and allotted network storage.
- **Rapid elasticity and scalability** – Cloud infrastructures can grow and shrink dynamically, allowing users to request that their computational resources auto-scale with traffic demands. It enables the cost-effective running of workloads that require a vast number of servers but only for a short period. 
- **Resilience and availability** – A cloud’s resilience is measured by how fast its [servers](/wiki/hardware), [databases](/wiki/databases), and [network](/wiki/network) system restarts and recover from any harm or damage. Availability is another major characteristic of cloud computing. Since cloud services can be accessed remotely, there is no geographic restriction or limitation when it comes to utilizing cloud resources.
- **Measured service** – Cloud infrastructure providers give detailed usage metrics that are used to communicate usage costs. Cloud service providers generally take a utility style pay-as-you-go billing model that is measured and delivered, so customers are charged for the exact amount of computing resources used.

## Cloud Service Models
The three cloud service models are: Infrastructure as a Service (IaaS), Platform as a Service (PaaS) and Software as a Service (SaaS). These models offer increasing abstraction and they are often portrayed as layers in a stack: infrastructure-, platform- and software-as-a-service. The models are based on the concept of sharing on-demand computing resources, software, and information over a network – ideally a high broadband communication link, such as the Internet. 

'As a service' refers to the way IT assets are consumed in these offerings, and to the essential difference between cloud computing and traditional IT. In traditional IT, an organization consumes IT assets – hardware, system software, development tools, applications – by purchasing them, installing them, managing them and maintaining them in its own on-premises data center. In public cloud computing, the cloud service provider owns, manages and maintains the assets; the customer consumes them via an Internet connection, and usually pays for them on a subscription or pay-as-you-go basis. 

![Cloud computing](/assets/images/cloud.png)

*Cloud computing*

### IaaS
IaaS provides on-demand access to cloud-hosted physical and virtual servers, storage and networking – the backend IT infrastructure for running applications and workloads in the cloud. IaaS enables end-users to scale and shrink resources on an as-needed basis, reducing the need for high, up-front capital expenditures or unnecessary on-premises or ‘owned’ infrastructure and for overbuying resources to accommodate periodic spikes in usage. 

Typically IaaS customers can choose between virtual machines (VMs) hosted on shared physical hardware (the CSP manages virtualization) or bare metal servers on dedicated (unshared) physical hardware. IaaS is a self-service environment that allows customers to provision, configure and operate the servers and infrastructure resources via a graphical dashboard (console), or programmatically through APIs. 

### PaaS
PaaS provides on-demand access to a complete, ready-to-use, cloud-hosted platform for developing, running, maintaining and managing applications. It provides the underlying infrastructure (compute, network, storage), as well as programming-language runtime execution environment, middleware (e.g., identity, messaging, etc.) and [database management systems](/wiki/databases). PaaS delivers development tools and a framework that allow developers to create customized applications. PaaS customers can simply upload an artifact of their application code that is automatically deployed to the platform, which automatically handles scaling and monitoring of the infrastructure to grow or shrink resources with observed traffic loads.

Today, PaaS is often built around [containers](/wiki/virtualization#containers) that are deployed on top of a container orchestration platform such as Kubernetes. The orchestration platform and other tools in the container ecosystem enable a CSP to deliver a highly productive PaaS that addresses many of the infrastructure- and operations-related tasks and issues around cloud-native application development.

### SaaS
SaaS provides on-demand access to ready-to-use, cloud-hosted application software. The application and all of the infrastructure required to deliver it, such as servers, storage, networking, middleware, application software and data storage are hosted and managed by the SaaS vendor. The vendor also manages all upgrades and patches to the software, usually invisibly to customers. In most cases, SaaS users pay a monthly or annual subscription fee, but some vendors may offer ‘pay-as-you-go’ pricing based on your actual usage. SaaS is the primary delivery model for most commercial software today. There are hundreds of thousands of SaaS applications available.


## Cloud Deployment Models
There are several types of cloud deployment models: public cloud, private cloud, hybrid cloud and multi-cloud.  

### Public Cloud
Public cloud is a type of cloud computing in which a CSP makes computing resources – anything from SaaS applications, through individual virtual machines (VMs), to bare metal computing hardware, to complete enterprise-grade infrastructures and development platforms – available to users over the public internet. These resources might be accessible for free, or access might be sold according to subscription-based or pay-per-usage pricing models.

The public cloud provider owns, manages, and assumes all responsibility for the data centers, hardware, and infrastructure on which its customers’ workloads run, and it typically provides high-bandwidth network connectivity to ensure high performance and rapid access to applications and data. 

The three most popular public cloud services are:
1. [Amazon Web Services](https://aws.amazon.com/) (AWS)
2. [Microsoft Azure](https://azure.microsoft.com/en-us/)
3. [Google Cloud](https://cloud.google.com/) (formerly known as GCP)

### Private Cloud
Private cloud is a cloud environment in which all cloud infrastructure and computing resources are dedicated to, and accessible by, one customer only. Private cloud combines many of the benefits of cloud computing, including elasticity, scalability, and ease of service delivery, with the access control, security, and resource customization of on-premises infrastructure.

A private cloud is typically hosted on-premises in the customer's own data center (“on-prem”). But a private cloud can also be hosted on an independent cloud provider’s infrastructure or built on rented infrastructure housed in an offsite data center.

### Hybrid Cloud
Hybrid cloud is a combination of public and private cloud environments. Specifically, and ideally, a hybrid cloud connects an organization's private cloud services and public clouds into a single, flexible infrastructure for running the organization’s applications and workloads.

The goal of hybrid cloud is to establish a mix of public and private cloud resources, and with a level of orchestration between them that gives an organization the flexibility to choose the optimal cloud for each application or workload and to move workloads freely between the two clouds as circumstances change. This enables the organization to meet its technical and business objectives more effectively and cost-efficiently than it could with public or private cloud alone.

### Multi-cloud and Hybrid Multi-cloud
Multicloud is the use of two or more clouds from two or more different cloud providers. Having a multi-cloud environment can be as simple as using email SaaS from one vendor and image editing SaaS from another. But when enterprises talk about multicloud, they typically refer to using multiple cloud services, including SaaS, PaaS, and IaaS services from two or more of the leading public cloud providers.Hybrid multi-cloud is the use of two or more public clouds together with a private cloud environment. 



