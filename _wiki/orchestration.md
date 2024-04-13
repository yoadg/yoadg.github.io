---
layout: page
title: Container Orchestration
permalink: /wiki/orchestration/
date: 2024-04-13
categories: 
  - compute
tags:
  - containers
  - kubernetes
  - docker
---

Container orchestration tools manage and automate the complete lifecycle of [containers](/wiki/virtualization#containers), including provisioning, deployment, networking, scaling and availability. In small numbers, containers are easy enough to deploy and manage manually. But in large scale systems the number of containerized services is growing rapidly, and managing them at scale is impossible without automation. Container orchestrators typically apply their own methodologies and offer varying capabilities, but they all enable organizations to automatically coordinate, manage, and monitor containerized applications. They make it easier to deploy and run containerized applications and microservices at scale, especially as part of a continuous integration/continuous delivery (CI/CD) or DevOps pipeline.

Most container orchestration tools use declarative programming that defines the desired output instead of describing the steps needed to make it happen. Developers write a configuration file  (in [YAML](/wiki/serialization#yaml) or [JSON](/wiki/serialization#json) format, depending on the tool) that typically:
- Defines which container images make up the application, and where they are located (in what registry);
- Defines how to establish and secure the network between containers;
- Provisions container storage and other resources;
- Specifies versioning (for phased or canary rollouts).

Container orchestration tools use this file to achieve the desired configuration state automatically. When a new container is deployed, the orchestration tool automatically schedules the container and finds the most appropriate host for it based on the predetermined constraints or requirements defined in the configuration file, such as [CPU](/wiki/hardware#central-processing-unit), [memory](/wiki/hardware#main-memory), proximity to other hosts, or even metadata. 

Once the containers are running, container orchestration tools automate life cycle management and operational tasks based on the container definition file, including:
- Provisioning and deployment;
- Scaling containers up or down and load balancing;
- Allocating resources between containers;
- Moving containers to another host to ensure availability if there’s a shortage of resources or an unexpected outage;
- Allocating resources between containers;
- Service discovery;
- Collecting and storing log data and other telemetry used to monitor the health and performance of the application.

Container orchestration platforms can be self-built or managed. Self-built container orchestrators give developers complete control over customization and are typically built from scratch or leveraging an open source platform. They can be installed in a private (on-premises) or a public cloud. The down side is the burden of managing and maintaining the platform. 

The most common open source container orchestration platform for cloud-native development is [Kubernetes](https://kubernetes.io/) (K8s). It is an open source container orchestration system originally developed by Google. While there are other options for container orchestration, such as [Apache Mesos](https://mesos.apache.org/){:target="_blank"} or [Docker Swarm](https://docs.docker.com/engine/swarm/){:target="_blank"}, Kubernetes has become the de-facto industry standard. There are also commercial products which are based on K8s such as [Red Hat OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift){:target="_blank"}. 

The other option is to use a managed platform or a Containers as a Service (CaaS) offering from a cloud provider, such as Amazon, Google or Microsoft. With managed container orchestration platforms or CaaS, the cloud provider is responsible for managing installation and operations. As a result, developers simply consume the capabilities and focus on running their containerized applications. Some of these services are based on K8s such as [Amazon Elastic Kubernetes Service (EKS)](https://aws.amazon.com/eks/){:target="_blank"}, [Google Kubernetes Engine (GKE)](https://cloud.google.com/kubernetes-engine){:target="_blank"}, [Azure Kubernetes Service (AKS)](https://www.ibm.com/products/openshift){:target="_blank"} and [Red Hat OpenShift on IBM Cloud](https://www.ibm.com/products/openshift){:target="_blank"}. Amazon also offers a proprietary container orchestration managed service called [Elastic Container Service (ECS)](https://aws.amazon.com/ecs/){:target="_blank"}. 

## Kubernetes
As noted above, Kubernetes is the most popular container orchestration platform. Originally created by Google, it is now maintained by the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/){:target="_blank"}. Together with other tools in the container ecosystem, Kubernetes enables a company to deliver a highly productive [Platform-as-a-Service (PaaS)](/wiki/cloud#paas) that addresses many of the infrastructure and operations related tasks and issues around cloud-native application development, so that development teams can focus exclusively on coding and innovation.

Kubernetes’ advantages over other orchestration solutions are largely a result of its more comprehensive and sophisticated functionality in several areas, including:
- **Container deployment** - K8s deploys a specified number of containers to a specified host and keeps them running in a desired state.
- **Automatic bin packing** - K8s is deployed over a cluster of nodes that it can use to run containerized applications. Based on the amount of CPU and RAM that each container needs, K8s fits them onto the available nodes to make the best use of system resources. 
- **Automated Rollouts and Rollbacks** - A rollout is a change to a deployment. Users can describe the desired state for their deployed containers and K8s ensures that this state will be enrolled at a controlled rate.
- **Service discovery** - K8s can automatically expose a container to the internet or to other containers using a DNS name or IP address.
- **Storage provisioning** - Developers can set K8s to mount persistent local or cloud storage for your containers as needed.
- **Load balancing and scalability**- When traffic to a container spikes, K8s can employ load balancing and scaling to distribute it across the network to ensure stability and performance. (It also saves developers the work of setting up a load balancer.)
- **Self-healing for high availability** - When a container fails, K8s can restart or replace it automatically. It can also take down containers that don’t meet your health-check requirements.
- **Secret and configuration management** - K8s lets users store and manage sensitive information, such as passwords, OAuth tokens and SSH keys. 
- **Support and portability across multiple cloud providers** - K8s enjoys broad support across all leading cloud providers. This is especially important for organizations deploying applications to a hybrid cloud or hybrid multi-cloud environment.
- **Growing ecosystem of open-source tools** - K8s also has an ever-expanding stable of usability and networking tools to enhance its capabilities via the K8s API. These include [Knative](https://knative.dev/docs/){:target="_blank"}, which enables containers to run as serverless workloads; and [Istio](https://istio.io/){:target="_blank"}, an open source service mesh. 

At its core, Kubernetes follows a client-server architecture. There are two core pieces in a K8s cluster: control plane and worker nodes. 

The control plane is responsible for managing the state of the cluster. In production environments, the control plane usually runs on multiple nodes that span across several data center zones. In other words, the control plane manages worker nodes and the containers running on them.

The containerized applications run in a *Pod*. Pods are the smallest deployable units in K8s. A pod hosts one or more (tightly related) containers and provides shared storage and networking for those containers. Pods are created and managed by the K8s control plane. They are the basic building blocks of K8s applications.

![Kubernetes Architecture](/assets/images/k8s.png)

*Kubernetes Architecture*

## Docker Swarm
Docker Swarm, offered by Docker, is an open source container orchestration tool and Docker’s native clustering engine. It enables the effective management of multiple containers deployed on numerous machines by converting a pool of Docker instances and hosts into a single virtual host.

Docker Swarm offers decentralized access, making it easy for distributed teams to work on and manage the environment effectively. 

## Apache Mesos
Apache Mesos is another open source cluster management service. It works between the application layer and the OS, making deploying and managing applications in large-clustered environments more straightforward and efficient.

Mesos is the first open source cluster management service to handle a workload in a distributed environment using dynamic resource sharing and isolation, the segregation of a program from other running processes. Mesos provides applications with the available resources on all machines in the cluster and frequently updates to include resources that completed applications have freed up. This lets applications make the best decision about which task to execute on which machine.

## HashiCorp Nomad
First released by HashiCorp in 2015, Nomad was initially designed to be a general orchestrator. Now, Nomad is a container orchestration tool that provides flexible cluster management and the scheduling and deploying of tasks among the worker nodes in a cluster. Worker nodes within the Kubernetes cluster perform actions facilitated by the Kubernetes API. They can be used to run containerized applications and can also handle networking between applications with and outside the cluster.

Nomad deploys and manages containers and non-containerized applications on various infrastructures at scale in on-site or cloud environments. Beyond containers, Nomad handles the orchestration of any application and offers bin packing to enable effective space management and job scheduling.

## SUSE Rancher
SUSE Rancher is a service built for the easy management, organization, and administration of thousands of Kubernetes clusters on any infrastructure.

Rancher allows developers to create Kubernetes clusters with the Rancher Kubernetes Engine (RKE) or with other cloud Kubernetes services, such as GKE and EKS. With SUSE Rancher, developers can import and manage existing Kubernetes clusters from any Kubernetes distribution.
