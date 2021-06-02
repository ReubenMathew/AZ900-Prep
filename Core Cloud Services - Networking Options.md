# Azure Networking Options
**Azure Region:** A region is one or more Azure data centers within a specific location

**Virtual Network:** Logically isolated network on Azure, can be segmented into subnets

**Network Security Group:** Allows or denies inbound network traffic to Azure resources, (like a cloud-level firewall for your network). Good for placing restrictions and traffic filtering.

## Azure Load Balancer
**Resiliency:** A system's ability to stay operational during abnormal conditions, including:
- natural disasters
- system maintenance, software updates/patches
- spikes in traffic
- threads made by malicious parties (DDoS attacks)

**Load Balancer:** Distributes traffic evenly among each system in a pool, achieves availability and resiliency

### Azure Load Balancer
- load balancer service provided and managed by microsoft
- supports inbound and outbound scenarios
- low latency and high throughput
- scales up to million of flow for TCP and UDP applications
![Azure Load Balancer Example Architecture Diagram](https://camo.githubusercontent.com/ec3eaba5cf0d0b75b5a77da702405d5b084d60f5b67991c1410a7a8257015991/68747470733a2f2f646f63732e6d6963726f736f66742e636f6d2f656e2d75732f6c6561726e2f6d6f64756c65732f696e74726f2d746f2d617a7572652d6e6574776f726b696e672f6d656469612f332d617a7572652d6c6f61642d62616c616e6365722e706e67)

### Azure Application Gateway
- if all traffic is HTTP, a better option is Azure Application Gateway
- Azure Application Gateway is a load balancer designed for web-apps
- Uses Azure Load Balancer at TCP level and applies URL-based routing rules to support advanced scenarios
- Benefits over a simple load balancer
	- Cookie affinity (for maintaining user sessions)
	- SSL termination
	- Web application firewall
	- URL rule based routes
	- Rewrite HTTP headers

## CDN (Content Delivery Networks)
- distributed network of servers that deliver web content to users
- a way to get content to users in their region while minimizing latency
- CDN can be hosted on Azure or any other location
- Cache content strategically and place it geographically to optimize performance

**DNS (Domain Name System):** A way to map user-friendly names to IP-addresses (e.g. 192.23.2.41.23. -> google.com)


## Azure Traffic Manager
**Network Latency:** Latency is the time it takes data to travel over the network, measured in milliseconds 

One way of reducing latency is to provide copies of your service in more than one region so that your user always has a low latency server to provide them with data

**Azure Traffic Manager:** Uses the DNS server nearest to user to direct user traffic to a globally-distributed endpoint

Traffic Manager **doesn't see the traffic** passed between client --> server, it only directs the client to a preferred endpoint

### Load Balancer vs. Traffic Manager
- load balancer distributes traffic within the same region to make services more available and resilient
- traffic manager works at DNS level and directs client to an endpoint
- both help make your services become more resilient, in different ways
- if load balancer detects unresponsive VM, it redirects traffic to another VM in pool
- if traffic manager finds unresponsive endpoint, it directs traffic to a responsive endpoint

## User Defined Routes (UDR)
- You can create custom routes that override Azure's default system routes
- In Azure, create a route table the associate the route table to 0...n virtual network subnets
	- each subnet can have zero or more routing tables associated to it
- Azure Limits define the max number of routes to a routing table and max number of routes per Azure subscription
- UDRs can be created without creating a subnet