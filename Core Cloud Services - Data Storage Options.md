# Data Storage Options
## Benefits to Azure Data Storage
- Automated backup and recovery
- Global database replication
- Support for data analytics
- Encryption capabilities
- Multiple supported data types
- Data stroage in virtual disks
- Data Storage tiers

### Data Types
- Structured data
	- Data that adheres to a scheme so all data has the same fields/properties
- Semi-structured data
	- doesn't fit neatly into tables, rows and columns.
	- instead uses tags or keys that provide hierarchy, also known as non-relational/NoSQL data
- Unstructured data
	- A blob can hold a pdf, jpg, json, video file, etc.

## Azure Data Products
- Azure SQL Database
	- relational DaaS (Database as a Service) based on Microsoft SQL Server
- Azure Cosmos DB
	- globally distributed database
	- supports schema-less data
		- good for highly responsive and Always On application with constantly changing data
- Azure Blob Storage
	- unstructured data,  no restrictions on data types
	- Azure Storage Account
	- useful for video storage
- Azure Data Lake Storage
	- the data lake feature allows analytics reporting and data usage reports 
	- data lake -> repository that stores structured and unstructured data
- Azure Files
	- managed file shares in cloud, accessible through SMB (server message block) protocol
- Azure Queue
	- service for storing large numbers of messages that can be accessed globally
- Disk Storage
	- provides disks for virtual machines and other services to access what they need, similar to on-prem scenarios
- Azure HDInsight
	- analyze streaming or historical data
	- use Hadoop, spark, give, LLAP, Kafka, Apache Storm, Microsoft machine learning server


### Storage Tiers
- Hot Storage
	- optimized for heavy database read workloads
- Cool Storage
	- optimized for data that is not frequently accessed and stored for at least **30 days**
- Archive Storage
	- data that is rarely accessed, stored for **180 days** with flexible latency options
	- to access data in archive storage you must change the tier to Hot or Cool, this is known as re-hydration

### Encryption
- Azure Storage Service Encryption (SSE)
- Client-side Encryption

### Replication
- A replication type is set up when a storage account is created
- replication ensures availability and durability
- azure has regional and geographic replications to protect data from natural disasters

## Azure Data Storage vs. On-Premises
- Cost
	- on-prem solutions require dedicated hardware and personnel for maintenance
	- Azure has a pay-as-you-go model
- Reliability
	- on-prem requires data backup, load balancing, and disaster recovery strategies
	- azure provides: backup, load balancing, recovery and replication services to ensure safety and availability
- Type Handling
	- azure provides a variety of different storage options including distributed access and tiered storage
- Agility
	- on-prem provisioning and deployment of new servers and infrastructure is expensive and time consuming
	- a new service on Azure can be created in minutes


For VMs that need a lot of storage, create a new Data Disk (32 TB limit)

## Azure Synapse (aka SQL DW)
- analytics service that brings together enterprise data warehousing and Big Data analytics
- query data on your terms, using serverless, on-demand or provisioned resources at scale
- Contains four components:
	- SQL Analytics
		- SQL pool
		- SQL on-demand
	- Spark (Preview)
	- Data Integration (Preview)
	- Studio (Preview)
- Azure Synapse is scalable