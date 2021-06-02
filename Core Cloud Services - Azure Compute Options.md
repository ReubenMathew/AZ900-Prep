# Azure Compute Options
## Compute Concepts
Azure compute is an on-demand computing service 

Four common ways of performing compute on Azure:
- Virtual Machines
- Containers
- Azure App Service
- Serverless Computing

### Virtual Machines
Azure Virtual Machines allow you to create and use virtual machines in the cloud. This is a IaaS in a virtualized server form

**Availability Sets:** Logical grouping of two or more VMs that keep your application available during planned or unplanned maintenance.

**Scale Sets:** Lets you create and manage a grou of identical, load balanced VMs

**Azure Batch:** Large scale job scheduling and compute management with large scaling ability

<<<<<<< HEAD
The storage service used to store hard drive files in a VM is BLOB (Page) storage

=======
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe
### Containers
A modified runtime environment built on top of host OS. Doesn't use virtualization so it doesn't simulate virtual hardware with an OS. Typically more lightweight than VMs.

**Azure Container Instances (ACI):** Fastest way to run container in Azure. No VM management or config. This is a PaaS, upload containers and execute with elastic scale.

<<<<<<< HEAD
**Azure Kubernetes Service (AKS):** Automates, manages and interacts with a large number of containers (orchestration). Complete orchestration service for containers with distributed architectures. This is a PaaS.
=======
**Azure Kubernetes Service (AKS):** Automates, manages and interacts with a large number of containers (orchestration). Complete orchestration service for containers with distributed architectures.
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe

Containers are often used for microservice architecture. Meaning when solutions are broken in smaller independent pieces. 

### Azure App Service
- Costs
	- pay for azure compute resources while your app processes requests based on the plan you choose.
	- the app service plan determines the type and quantity of hardware devoted to your app -> theres even a free tier
- web apps
	- includes full support for web apps using .NET Core, Java, Ruby, Node.js, PHP or Python
- API apps
	- includes swagger support and ability to package and publish API in Azure Marketplace
- web jobs
	- allows to run a program in the same context as a web app
	- can be scheduled or triggered 
- Mobile app back-ends
	- quickily build back-end for iOS and Android apps

### Serverless
- serverless abstracts the servers you run your application on.
- no server instance reservation
- each function execution run on a different compute instance
- simply deploy your code, then it runs with high availability
- Event-driven scale
	- serverless is perfect for incoming events
		- timing triggers, HTTP (webhooks), queues
- Micro-billing: pay for the time that code is run, if no active execution then there is no charge
- Best for rapidly changing scaling needs

