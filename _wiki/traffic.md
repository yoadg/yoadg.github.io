---
layout: page
title: Traffic Management
permalink: /wiki/traffic/
date: 2024-06-25
categories: 
  - network
  - communication
tags:
  - load balancer
  - reverse proxy
  - api gateway
---

Modern cloud applications can be built with different architectures and technologies, but in general they expose services that can be consumed by various clients, such as Web, Mobile, Desktop and Embedded applications. Cloud services that are open to the Internet can be accessed by a large number of clients and therefore incoming network traffic must be managed and controlled to ensure high availability, scalability, and performance. Some of the clients that try to access these services can be unauthorized or even malicious. In order to protect the services against such attempts, access control and security measures must be applied. 
 
Application traffic management (ATM) refers to techniques for intercepting, analyzing, decoding, and directing web traffic to the optimum resources based on specific policies. Also called network traffic management, it allows network administrators to significantly increase overall network application performance by routing and filtering packets based on content in their payloads or headers. By applying these standards for security, scalability, availability, and performance to any IP-based application users can save costs and improve efficiency.

An Application Delivery Controller (ADC) is a type of server that provides a variety of services designed to optimize the distribution of load being handled by backend application servers. An ADC directs web request traffic to optimal data sources in order to remove unnecessary load from web servers. 

Features commonly found in ADCs include:
- Load balancing
- Traffic shaping (throttling) 
- SSL/TLS offloading
- Web Application Firewall
- DNS
- Reverse Proxy
- API Gateway
- HTTP content redirection
- Server health monitoring
- Payload compression/decompression
- A/B testing
- Authorization & Access Control 

ADC has evolved into 3 distinct products:

-  A **load balancer** acts as a traffic distributor, evenly distributing incoming requests across multiple backend servers or instances to optimize resource utilization, improve availability, and enhance performance. It helps achieve scalability, fault tolerance, and improved performance by using various algorithms to determine which server should handle each request, considering factors like server health, available resources, and session persistence.
-  A **reverse proxy**, also known as an application-level gateway, sits between clients and servers and handles requests on behalf of the servers. It acts as an intermediary for client requests, forwarding them to the appropriate server and returning the server's response to the client. Reverse proxies provide benefits such as caching, SSL termination, and improved security by shielding servers from direct exposure to the internet.
- An **API gateway** acts as an API front-end. Its primary function is to facilitate communication, security and management of APIs. It provides a single point of entry, abstracting the underlying architecture and providing a unified interface for clients. API gateways offer various functionalities like request routing, protocol translation, authentication, and rate limiting. They enable organizations to manage and secure their APIs effectively.

![Application Traffic Management](/assets/images/traffic.png)

*Application Traffic Management*

## Load Balancer 
A load balancer is a specialized network appliance or software application designed to optimize the distribution of incoming network traffic across multiple servers or resources. Its primary role is to enhance the performance, availability, and reliability of distributed applications and services by preventing any single server from becoming a bottleneck. Load balancers achieve this by employing various algorithms to route incoming requests to the most appropriate server intelligently.

Load balancers can be configured to perform health checks on the registered backend servers. These health checks act as tests to verify the availability of the backend servers. If a server is not responding or unhealthy, the load balancer redirects traffic to other active servers. When a new server joins the group, the load balancer automatically starts routing requests to it.

The role of a load balancer is not limited to just distributing traffic between clients and servers. Load balancers can also be used within a data center to balance traffic between different components of an application, such as microservices. They can even be deployed to distribute workloads across multiple databases, cache servers, or other backend services. This makes them versatile tools in various network architectures beyond the traditional client-server model.

The key aspects of load balancers are:

- Traffic Distribution – Distribute incoming traffic across multiple backend servers or service instances based on predefined algorithms such as round-robin, least connections, or weighted distribution. This ensures efficient utilization of resources and prevents overloading of individual servers.
- High Availability – Enhance the availability of services by intelligently routing traffic away from unhealthy or overloaded servers. They perform health checks to monitor the status of backend instances and dynamically adjust traffic routing accordingly.
- Session Persistence – In scenarios where maintaining session state is crucial, load balancers support session persistence or sticky sessions, ensuring that subsequent requests from the same client are directed to the same backend server. This ensures consistency and avoids session-related issues.
- SSL Termination – Load balancers can offload SSL/TLS encryption and decryption, relieving backend servers from the computational overhead associated with SSL processing. This improves performance and simplifies management of SSL certificates.

### Load Balancer Types
There are different types of load balancers, each with its own characteristics and use cases:

- **Hardware Load Balancers** – These are dedicated appliances designed specifically for load balancing. They offer high performance, low latency, and advanced features like SSL/TLS offloading. However, they tend to be more expensive and less flexible than software solutions.
- **Software Load Balancers** – These are software-based solutions that run on servers or virtual machines. They are cost-effective, flexible and can be deployed on virtual machines or containers. 
- **Cloud-based Load Balancers** – Major cloud providers like AWS, Azure, and Google Cloud offer managed load-balancing services. These services are highly scalable, reliable, and easy to set up, but they may have limited customization options and can be more expensive for high-traffic workloads as they are generally charged by the volume of data processed.


Load balancers can also be classified based on the Open Systems Interconnection (OSI) layer at which they operate:

- A **Network Load Balancer** functions at Layer 4, dealing primarily with TCP and UDP packets. It distributes traffic at the transport layer, making routing decisions based on network variables such as IP addresses and destination ports. This load balancer focuses solely on network layer information when directing traffic.
- An **Application Load Balancer** / Layer 7 (L7) operates at Layer 7 of the OSI model. It distributes the load based on parameters at the application level. This enables more intelligent routing decisions based on the URL, HTTP headers, cookies, content type or application-specific data. 

Popular load balancers like [HAProxy](https://www.haproxy.org/){:target="_blank"} and [Nginx](https://nginx.org/en/){:target="_blank"} can be configured to run in layer 4 or layer 7. [AWS Elastic Load Balancing](https://aws.amazon.com/elasticloadbalancing/){:target="_blank"} service provides [Application Load Balancer (ALB)](https://aws.amazon.com/elasticloadbalancing/application-load-balancer/){:target="_blank"} in layer 7 and [Network Load Balancer (NLB)](https://aws.amazon.com/elasticloadbalancing/network-load-balancer/){:target="_blank"} in layer 4.

The main benefit of an L4 load balancer is that it’s quite simple. It’s just using the IP address and port to make its decision and so it can handle a very high rate of requests per second. The downside is that it has no ability to make smarter load balancing decisions. Doing things like caching requests is also not possible.

On the other hand, layer 7 load balancers can be a lot smarter and forward requests based on rules set up around the HTTP headers and the URL parameters. Additionally, they can cache responses for GET requests for a certain URL to reduce load on Web servers. The downside of L7 load balancers is that they can be more complex and computationally expensive to run. 

However, CPU and memory are now sufficiently fast and cheap enough that the performance advantage for L4 load balancers has become pretty negligible in most situations. Therefore, most general purpose load balancers operate at layer 7.

### Traffic Distribution Algorithms
Load balances use various algorithms to achieve the best possible distribution of traffic. The choice of a load-balancing algorithm depends on the specific needs and objectives of the application or service being balanced. Different algorithms offer various advantages and trade-offs, making them more or less suitable for particular scenarios.

**Static Algorithms:**
- Round robin — Client requests are sequentially sent to different service instances in a cyclic order, ensuring a fair distribution of the workload. Typically, statelessness is required for the services. 
- Sticky round-robin — An enhanced version of the round-robin algorithm where subsequent requests from a client go to the same service instance that handled the initial request.
- Weighted round-robin — The administrator can assign weights to each service, determining the proportion of requests each service handles.
- Hashing — This algorithm applies a hash function to the IP or URL of incoming requests. The instances to which requests are routed depend on the hash function’s result. Requests with the same hash will always go to the same service instance, assuming the number of instances is constant.
- Consistent hashing – A distributed hashing scheme that operates independently of the number of service instances in a distributed hash table by assigning them a position on an abstract circle, or hash ring. This scheme ensures that requests are distributed evenly across all instances while maintaining the same server for each request.

**Dynamic Algorithms:**
- Least connections — New requests are directed to the service instance with the fewest active connections. If the servers are not equal, this algorithm may also consider the capacity of each server, so that servers with more capacity receive more requests (weighted least connections).
- Least response time — New requests are sent to the service instance with the lowest average response time.

## Reverse Proxy
A reverse proxy functions as a mediator between clients and servers, like a Load Balancer. Reverse proxies are typically used to increase security, speed, and dependability. Unlike a traditional forward proxy, which mediates requests from clients to other servers, the reverse proxy handles requests from clients on behalf of the target servers. Clients interact solely with the reverse proxy to reach backend servers, as the proxy forwards requests to the relevant server. This mechanism conceals the implementation specifics of individual servers within the internal network. The proxy returns server responses to the client, giving the impression that the first proxy server handled the request. The proxy ensures that users don't access the origin server directly, giving the web server's anonymity. Reverse proxies function at Layer 7 (application layer) of the OSI model, where they manage requests and responses at the HTTP level.

The key aspects of reverse proxies are:

- Load balancing – Evenly distributes incoming client requests among multiple backend servers (similar to load balancers but only in the application layer). 
- Caching — For repeated requests, it can independently respond, either in part or in full. Frequently accessed content is stored in the proxy cache, reducing the need to fetch data from the backend and providing clients with quicker responses.
- Enhanced Security — A reverse proxy can act as a shield, filtering incoming requests and protecting backend servers from malicious traffic. Furthermore, it can be equipped with security features such as Web Application Firewalls (WAFs) and Intrusion Detection Systems (IDS), which proactively monitor and filter incoming traffic.
- DDoS Mitigation – Many reverse proxies have built-in features to shield backend servers from distributed denial-of-service (DDoS) attacks, such as IP deny listing and client connection rate limiting.
- SSL termination (offloading)  — It can be set up to decrypt incoming requests and encrypt outgoing responses, thereby freeing up valuable backend resources.
- Backend Anonymity – Backend servers remain hidden from the external network, protecting against potential vulnerabilities.
- Data Compression – Reduces the size of server responses for faster data transfer.
Direct Serving of Static Content – Manages the delivery of static files like HTML, CSS, JavaScript, images, and videos directly to the client.
-  URL/Content Rewriting: Modifies the URL or content before forwarding requests to the backend servers. This is simplifying complex URLs and enhancing SEO.

Examples of reverse proxy products are: Nginx, [Envoy](https://www.envoyproxy.io/){:target="_blank"}, [Apache HTTP Server](https://httpd.apache.org/){:target="_blank"}, [Microsoft IIS](https://www.iis.net/){:target="_blank"} and [Azure Application Gateway](https://azure.microsoft.com/en-us/products/application-gateway){:target="_blank"}.

## API Gateway
An API gateway acts as a middleware component that sits between clients and backend services. It can be seen as a superset of a Reverse Proxy, but its primary function is to facilitate communication, security, and management of APIs. The API GW provides a centralized and unified entry point for accessing various endpoints and functionalities, while abstracting the underlying architecture and decoupling the client interface from the backend. This ensures clients can communicate with applications consistently even as internal implementations change.

API gateways are a key component of modern microservices architecture. In a microservices application, numerous services within the application communicate with each other via APIs, and might also serve external clients and users. In this context, the role of API gateway is to provide a single point of communication for a group of microservices, with the ability to enforce policies and determine availability and behavior across all microservices.

The key aspects of API gateways are:

- Security — Incorporate features such as authentication and authorization, ensuring that only authorized clients can access backend services. This includes verification of API keys, tokens, or other forms of identification.
- Routing – Receive requests from clients and routes them to the appropriate service. This enables clients to access the various services through a single entry point.
-  Rate limiting – Manage the volume of requests a client can make to an API within a defined time (throttling). This can help prevent denial of service attacks and other types of malicious behavior.
- Caching – API GWs may choose to cache responses for recurring requests, enhancing overall responsiveness by reducing the number of requests that need to be forwarded to the services.
- Transformation – API GWs can translate between protocols such as REST and SOAP and convert between data formats like JSON and XML. This capability enhances interoperability in heterogeneous environments, allowing clients to communicate with backend services using different protocols or message formats.
- Request and response validation – API GWs can be used to validate the requests and responses from services to ensure that they conform to the expected format and structure. It can help to prevent errors and ensure that the services are functioning properly.
- Service discovery – API GWs can be used to discover the available services and their locations. This mechanism makes it easier to add new services or make changes to the existing ones without impacting the clients.
- Analytics and Monitoring — API GWs can collect metrics and other data about requests and responses, providing valuable insights into the performance and behavior of services. It can help to identify and diagnose problems, and improve the overall reliability and resilience of the system.

Popular API GW products and services: [Kong](https://konghq.com/products/kong-gateway){:target="_blank"}, [Amazon API Gateway](https://aws.amazon.com/api-gateway/){:target="_blank"}, [Apigee](https://cloud.google.com/apigee){:target="_blank"}, [Tyk](https://tyk.io/){:target="_blank"}, [Apache APISIX](https://apisix.apache.org/){:target="_blank"}









