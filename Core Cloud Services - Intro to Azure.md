# Core Cloud Services - Intro to Azure
## Azure Services
- compute
	- scale compute capabilities (VMs, App services for mobile)
- networking
	- connect infrastructure (VPNs, Load Balancing)
- storage
	- disk, file, BLOB (Object), archival
	- security
- mobile
	- build, deploy cross-platform mobile apps
- databases
- web
	- build, deploy and manage web apps
	- publish APIs, azure maps (geolocation data)
- IoT (Internet of Things)
	- analyze sensor data
<<<<<<< HEAD
	- IoT Edge -> analyze data on End-user devices
	- IoT Hub -> bi-directional communication between IoT application and devices
=======
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe
- Big Data
	- open source cluster services
- AI
	- machine learning, training and deployment
- devops
	- automate software delivery
	- build and release pipelines (CI -> Continuous Integration, CD -> Continuous Delivery)

![Azure Services](https://camo.githubusercontent.com/3801bd8157d64ef6c8be5f3f2bf8b9ad57664dd642475ec230a9b07cc1848f66/68747470733a2f2f646f63732e6d6963726f736f66742e636f6d2f656e2d75732f6c6561726e2f6d6f64756c65732f77656c636f6d652d746f2d617a7572652f6d656469612f332d617a7572652d73657276696365732e706e67)

### Azure App Service
Azure App Service is an HTTP-based service that enables you to host web-based applications without managing infrastructure. This is a service that can be scaled up/down. 

You can use **Azure Advisor** or **Azure Cost Management** to optimize cloud spending. 

**Azure Cost Management** can get reports of "Costs incurred by resource"

Azure App Service can be accessed using **Azure Cloud Shell**, which is a Bash/Powershell command-line interface that can be used to control and monitor Azure resources.
- **Azure Powershell on linux needs to be version 7.x or higher**

**Resource Group:** Allows the administration of all services, disks, network interfaces and other elements

To compare costs for moving workloads to Azure, use **Azure TCO Calculator**