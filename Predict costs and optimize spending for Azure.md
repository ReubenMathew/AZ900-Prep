# Predict costs and optimize spending
### Usage Meters
- when a resource is provisioned, azure creates one/multiple meter instances
- meters track usage and generate a usage record used to calculate the bill

## Cost Affecting Factors
- resource type
- services
	- usage rates and billing periods differ between enterprise, web idrect and CSPs 
- location
- billing zones

You can use the **Azure Pricing Calculator** and the example scenarios tab to figure out what a solution will cost. The Products tab will create an estimate for your custom solution

## Azure Advisor
- free service built into Azure
- provides recommendations on high availability, security, performance, operational excellence and cost
- analyzes deployed services and looks for ways to improve your environments
- cost recommendations
	- reduces cost by eliminating Azure ExpressRoute circuits
	- buy reserved instances to save money instead of pay-as-you-go
	- shutdown or scale down underutilized virtual machines

## Azure Cost Management
- free built-in tool to gain insights in where cloud money is going
- see historical breakdowns 
- set budgets, schedule reports and analyze costs
	- get notifications if costs go beyond budget with Azure Budgets


## Azure Total Cost Ownership (TCO)
Can help predict and analyze spending for new or existing services
1. open TCO calculator
2. define workloads
3. adjust assumptions
4. view report

## Saving
- azure credits
	- $50 per month for VS Professional
	- $150 per month for VS Enterprise
- spending limits
- reserved instances
	- can potentially save 70%-80% off pay-as-you-go costs
- low-cost locations
- scale down unused virtual machines
- migrate to PaaS or SaaS (both are less expensive than IaaS)
- choose OS that is cheaper
- Azure Hybrid Benefit for Windows Server
- Azure Hybrid Benefit for SQL Server