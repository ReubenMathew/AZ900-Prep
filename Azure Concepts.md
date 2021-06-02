# Azure Concepts
Azure is a cloud computing platform
	- services range from simple web services to running virtual machines
	- provides: remote storage, database hosting, centralized account management, AI and Internet of Things (IoT)
	
## Cloud Computing
- Delivery of computing services over the internet
	- services include:
		- servers
		- storage
		- databases
		- networking
		- software
		- analytics and intelligence
- The advantage is in faster innovation, flexible resources and scalability
- Cloud computing uses **pay-as-you-go** pricing model
	- Lowers operating costs
	- run infrastructure more efficiently
	- scale business as needs change (on-demand)
- AKA rent compute power and storage from someone else's data center
- Instead of maintaining hardware (cpu, storage, memory) you rent them and the cloud provider manages the underlying infrastructure
- Advantages of Cloud Computing
	- limitless pool of compute, storage and networking resources
	- AI/ML services
	- analytics services from software and IoT devices

### Benefits
- cost-effective
- scalable
- elastic (dynamic scaling)
- reliable (fault tolerance)
- global (multiple datacenter locations globally)
- current (maintained by provider)
- secure (standardized policies and controls)

### [Compliance terms and requirements](https://docs.microsoft.com/en-us/learn/modules/principles-cloud-computing/3a-compliance)

#### Compliance Offerings

-   Criminal Justice Information Services (CJIS)
-   Cloud Security Alliance (CSA) STAR Certification
-   General Data Protection Regulation (GDPR) EU Model Clauses
<<<<<<< HEAD
	-   European data privacy and data protection
-   Health Insurance Portability and Accountability Act (HIPAA)
-   International Organization for Standardization (ISO)
	-   defines international standards across all industries
-   Multi-Tier Cloud Security (MTCS) Singapore
-   Service Organization Controls (SOC) 1, 2, and 3
-   National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF)
	-   organization that defines standards used by the US government
=======
-   Health Insurance Portability and Accountability Act (HIPAA)
-   International Organization for Standardization (ISO)
-   Multi-Tier Cloud Security (MTCS) Singapore
-   Service Organization Controls (SOC) 1, 2, and 3
-   National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF)
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe
-   UK Government G-Cloud
### Cloud Deployment Models
- Public Cloud
	- no local hardware changes to manage, everything runs on cloud provider hardware
- Private Cloud
	- you create cloud environment in your own datacenter and self-service access to compute resources 
- Hybrid Cloud
	- combine public and private clouds allowing the applications to run in the appropriate location

### Economics
**Economies of Scale:** Ability to do things more efficiently at a lower-cost per unit when operating at a larger scale

#### Capital Expenditure (CapEx)
Spending money on physical infrastructure and deducting that expense from your taxes over time. It is an upfront cost that generally reduces over time and has no recurring cost. (Example: deploying your own data center or using Azure Reserved VM instances).

*\*Even though Azure VM is stopped you still pay for storage costs*

Allows you to plan expenses at the start of project with a fixed cost/budget. 
##### Computing Costs
- server
- storage
- backup and archiving
- organization continuity / disaster recovery
- datacenter infrastructure costs
- technical personnel (operations experts)
#### Operational Expenditure (OpEx)
Expenses to run day-to-day business, like services and consumables. You deduct this expense from your tax bill in the same year. No upfront cost but there is recurring costs (pay-as-you-go pricing).

Growth can be unpredictable and outpace expectations and increase costs greatly.
##### Computing Costs
- leasing software and customized features
	- requires actively managing subscriptions to ensure users don't misuse services
- scaling charges based on usage instead of fixed hardware/capacity
- billing at user or organization level
	- organization is billed for services used on a recurring basis and is subject to scaling, customization and provisioning

### Types of Cloud Services
#### On-premises (On-Prem)
- You manage all hardware provisioning and maintenance
- You manage
	- Applications
	- Data
	- Runtime
	- Middleware
	- OS
	- Virtualization
	- Servers
	- Storage
	- Networking
#### Infrastructure as a Service (IaaS)
- gives the most control over provider hardware
- instead of buying hardware you rent it
- **You Manage:**
	- Applications
	- Data
	- Runtime
	- Middleware
	- OS
- **They Manage:**
	- Virtualization
	- Servers
	- Storage
	- Networking
#### Platform as a Service (PaaS)
- environment for building, testing and deployment
- create an application quickly without managing underlying hardware
- no need to install OS, web servers or system updates
- e.g. Databases are a PaaS
- **You Manage:**
	- Applications
	- Data
- **They Manage:**
	- Runtime
	- Middleware
	- OS
	- Virtualization
	- Servers
	- Storage
	- Networking
#### Software as a Service (SaaS)
- software that is hosted and managed for the end customer
- one version of the application is used for all customers
	- licensed through a subscription usually
- **They Manage:**
	- Applications
	- Data
	- Runtime
	- Middleware
	- OS
	- Virtualization
	- Servers
	- Storage
	- Networking
## What is Azure?
### Azure Portal
- Web based console (alternative to CLIs)
	- manage azure subscription
	- build, manage, monitor all your infrastructure
	- create dashboard for your resources
	- accessibility options

### Azure Marketpalce
- connects users with microsoft partners, independent vendors and startups

