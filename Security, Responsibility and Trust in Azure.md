# Security, Responsibility and Trust
Security is a shared responsibility...

![Azure Shared Security Responsibilities](https://camo.githubusercontent.com/8028b95cecc0b4b82fbc0451692138bc890d2e7457f7daa2d9af81fd19f2e453/68747470733a2f2f646f63732e6d6963726f736f66742e636f6d2f656e2d75732f6c6561726e2f6d6f64756c65732f696e74726f2d746f2d73656375726974792d696e2d617a7572652f6d656469612f322d7368617265645f726573706f6e736962696c69746965732e706e67)

Regardless of deployment type, you will always be responsible for:
- Data
- Endpoints
- Accounts
- Access management

**Layered Security:**
![Layered Security](https://camo.githubusercontent.com/94f68313bff6d0849c95eb95686d7f2d091a6e47d4aad3740e796901d4b6199a/68747470733a2f2f646f63732e6d6963726f736f66742e636f6d2f656e2d75732f6c6561726e2f6d6f64756c65732f696e74726f2d746f2d73656375726974792d696e2d617a7572652f6d656469612f646566656e73655f696e5f64657074685f6c61796572735f736d616c6c2e706e67)

## Security Points
### Data
Attackers are almost always after the data
- stored in database
- stored on VM disks
- stored on SaaS apps such as Office 365
- stored in cloud storage

### Application
- Ensure applications are secure and free of vulnerabilities
- store secrets in a secure storage medium
- make security a design requirement for all app development

### Compute
- secure access to VMs
- implement endpoint protection
- keep system versioning up-to-date

### Networking
- limit communication between resources
- deny requests by default
- restrict inbound internet access and limit outbound requests and responses
- implement secure connectivity to on-prem network

### Perimeter
- use DDoS protection to filter large scale attacks
- use perimeter firewalls to alert against malicious attacks

### Identity and Access
- control access to infra and role change controls
- use SSO and multi-factor auth
- audit events and config changes

### Physical Security
- physical building security and control access to compute hardware within the data center

## Azure Security Center
- Free tier
	- limited to assessments and recommendation of azure resources only
- Standard
	- provides full suite of security services
		- continuous monitoring
		- threat detection
		- just in time access control for ports
		- etc.
- Azure security center has support not only for VMs but for other components like Azure SQL
- Security Center supports VMs/Servers on different environments
	- only azure
	- azure and on-prem
	- azure and other clouds
	- azure, other clouds and on-prem

Useful for incident response and recommendation to enhance security

## Identity and Access
### Authentication and Authorization
**Authentication:** establish identity of person looking to access a resource

**Authorization:** establish what level of access an authenticated person has

### Azure Active Directory
The initial domain is onmicrosoft.com 
- Authentication
	- Multi-factor authentication (MFA) requires two or more elements for full authentication (e.g. SMS as second means of authentication)
		- something you know
		- something you possess
		- something you are
		- ![Authentication Methods in Azure](https://www.whizlabs.com/learn/media/2019/10/05/ckeditor_2_22_52.png)
		- The recommended policy is **Enable Conditional Access**
- SSO
	- the more identities a user has to manage, the greater risk of a credential related security incident
	- can easily disable and enable accounts through SSO management
- Application management
- B2B identity services
- B2C identity services
- Device Management
<<<<<<< HEAD
- License user groups
=======
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe

#### Azure Active Directory Identity Protection
- User risk policy
- Azure policy
- Sign-in risk policy
- MFA registration policy

#### Azure Active Directory Identity Secure Score
- a number between 1-223 that functions as an indicator for alignment with best security practices
- the score helps to:
	- measure identity security posture
	- plan identity security improvements
	- review the success of your improvements

### Providing Identities to Services
**Service Principals:** An identity used by a service or application, can be assigned roles

**Managed identities:** when you create managed identity, you create an account on your org's Active Directory (Active Directory Tenant)

### Role-based Access Control (RBAC)
Roles are sets of permissions like "read-only" or "contributor", that users can be granted to access an Azure service instance

## Encryption
Symmetric: Same key to encrypt and decrypt

Asymmetric: Public key to encrypt and private key to decrypt

### At Rest
- data at rest is stored on physical medium
- stored in disk, database or in storage account

### In Transit
- actively moving from one location to another
- secure transfer can be handled by different layers
- e.g. TLS (Transport Layer Security -> asymmetric)

### On Azure
- **Azure Storage Service Encryption**
	- for data at rest
	- automatically encrypts data before persisting to Azure Managed Disks, Blob storage, file or Azure Queue storage
	- decrypts data before retrieval	
- **Azure Disk Encryption**
	- helps encrypt Windows and Linux IaaS VM disks
	- leverages **BitLocker** feature of windows and **dm-crypt** on linux to encrypt volumes
	- integrated with Azure Key Vault to help control and manage keys and secrets
- **Transparent Data Encryption (TDE)**
	- protects Azure SQL database and Azure Data Warehouse
	- performs real-time encryption and decryption of the database, associated backups and transaction log files at rest
	- enabled by default on all Azure SQL DB instances
- **Azure Key Vault**
	- cloud service for storing application secrets
	- helps control application secrets by keeping them in a central location
	- providing secure access, permission control and logging capabilities

## Azure Certificates
Certificates used on Azure are **x.509 v3** and can be signed by trusted certificate authority or self signed

### Types
**Service Certificates:** used for cloud services

**Management Certificates:** used for authenticating with the management API

### Using Azure Key Vault with Certificates
- store certs in Azure Key Vault like a regular secret
- gain benefits of key vault, which is beyond traditional certificate management
- automating certificate management helps reduce error prone task of manual management

## Network Protection
A layered approach provides levels of protection, if one layer is breached the others are not affected

**Azure Security Center** can be used to look for Internet Protection information

### Firewall
A service that grants server access based on IP address of each request, you can create rules to manage this

**Azure Firewall** is a managed cloud-based service that protects Azure Virtual Network resources

**Azure Application Gateway** is a load balancer that includes **WAF (web application firewall)**, designed to protect HTTP traffic

**Network Virtual Appliances (NVAs)** are options for non-HTTP services, similar to hardware firewall appliances

A firewall parent policy can be overridden with a stricter setting


### DDoS Attack Prevention
- Basic
	- automatically enabled in azure
	- always-on traffic monitoring and real-time mitigation
- Standard
	- provides additional mitigation capabilities
	- simple to enable and requires no config changes
	- protection policies are tuned with dedicated traffic monitoring and machine learning
	- applied to public IPs associated with resources deployed in virtual networks

### Traffic Control in Virtual Networks
- while in a virtual network, limit communication between resources to only what is required
- for VM communication, Network Security Groups (NSGs) are a critical to restrict unnecessary communication
- VPN connection can establish secure communication channels between networks
	- VPN is also known as a Local Network Gateway
- to get a dedicated private connection between your network and Azure, use **Azure Express Route**
	- lets you extend on-prem networks into the Azure cloud over a private connection

### Document Protection
- **Microsoft Azure Information Protection -> AIP** helps orgs classify and protect documents and emails by applying labels
	- analyze data flows 
	- detect risky behaviors
	- track document access
	- prevent data leakage or misuse
	- *Information Protection Admin and Security Admin can enable AIP access to a user*

### Azure Advanced Threat Protection (ATP)
Cloud based solution that identifies, detects and helps investigate advanced threats, compromised identifies and malicious insiders 

- **Azure ATP Portal**
	- Azure ATP has its own portal, for monitoring and response
	- allows you to create your own Azure ATP instance and view data from Azure ATP sensors
	- monitor manage and investigate threats in your network environment
- **Azure ATP sensor** (Microsoft Defender for Identity)
	- sensors are installed onto domain controllers
	- sensors monitor domain controller traffic without requiring a dedicated server or port mirroring configs
- **Azure ATP cloud service**
	- runs on Azure infrastructure
	- deployed in US, Europe and Asia
	- connected to Microsoft's intelligent security graph

Azure ATP is available as part of Enterprise Mobility + Security E5 suite (EMS E5) and as a standalone license. **Not available through Azure Portal.**



## Microsoft Security Development Lifecycle (SDL)
Introduces security and privacy consideration through all phases of development process
- provide training
- define security requirements
- define metrics and compliance reporting
- perform threat modeling
- establish design requirements
- define and use cryptography standards
- manage security risks from third-parties
- use approved tools
- perform Static Analysis Security Testing (SAST)
- perform Dynamic Analysis Security Testing (DAST)
- perform penetration testing
<<<<<<< HEAD
- establish standard incident response process



Azure Portal is used to create new Azure support requests
=======
- establish standard incident response process
>>>>>>> 9275ba257bf289e0a86e1cca386f042a13b03cbe
