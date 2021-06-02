# Azure Architecture and Service Guarantees
## Geography
- Datacenters and regions
	- A region is a geographic area containing, one or potentially multiple datacenters that are networked together in a low-latency fashion
	- Microsoft has **54 regions** worldwide
	- azure assigns and controls resources within each region to ensure balance
	- some services or VMs are only available in certain regions
	- an azure customer deploys application to the specified region, not individual datacenters
- Azure divides the world into geographies defined by geopolitical boundaries or borders
- Availability Zones
	- physically separate centers in a Azure region
	- each zone is made up of one/multiple data-centers equipped with independent power, cooling and networking
	- if one zone goes down the other continues working
	- each zone is connected through high-speed fiber optic networks
	- **only supported by certain regions**
<<<<<<< HEAD
	- The minimum number of VMs and Availability Zones for VMs in Multi-AZ mode is **One** to maintain a 99.99% SLA
=======
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe
- Region Pair
	- each azure region is paired with another region at least **300 miles away**
	- this allows for replication of resources across geography that helps reduce service interruptions

## Service Level Agreements
- SLAs describe Azure's commitment to providing azure customers with specific performance standards
- Each product/service in azure has an individual SLA
- SLAs specify what happens if a service/product fails to perform to a set standard
<<<<<<< HEAD
- Composite SLA is the product of all individual SLAs (e.g. 99.95% \* 99.99% = 99.94%)
=======
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe

**Characteristics of Azure SLAs:**
- Performance Targets
- Up-time and Connectivity Guarantees
- Service Credits

When combining SLAs across different offerings, the resultant SLA is called a **composite SLA**. The composite can provide high or lower up-time values depending on the application architecture.

### Application Reliability
By creating your own SLAs, you set performance targets to suit your Azure application, this is known as an **Application SLA**.

**Application Availability:** Overall time that a system is functional and working

#### Resiliency
- ability of a system to recover from failures
	- not avoiding failures, but responding to failures and avoiding downtime/data loss
	- return application to fully functioning state
	- High availability and disaster recovery are the two crucial components of resiliency
- When designing your application, design for resiliency
	- perform a **Failure Mode Analysis (FMA)**
		- identify possible points of failure and define how the application will respond to those failures
- Maximizing availability requires implementing things that prevent service failures
	- can be difficult and/or expensive
	- A workload that requires 99.99% uptime must depend on an >99.99% SLA


### Terminology
- resource
	- manageable item that is available through Azure
	- e.g. storage, web apps, databases, virtual networks
- resource group
	- container that holds related resources for an Azure solution
	- resource group includes resources to manage as a group
- resource provider
	- service that supplies azure resources
	- e.g. Microsoft.Compute which supplies VMs
- Resource Manager template
	- JSON file that defines resources to deploy to a group or subscription