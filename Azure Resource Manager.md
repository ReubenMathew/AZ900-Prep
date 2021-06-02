# Azure Resource Manager
## Resource Groups
A resource group is a logical container for resources deployed on Azure
- Define dependencies between resources, so that the correct deployment order is followed
- Logical Grouping -> resource groups exist to manage and organize
- Life cycle -> if you delete a resource group, all resources within are deleted
- Authorization
	- resource groups are a scope for applying RBAC permissions
	- by applying RBAC permissions, you can ease administration, and limit access

To create a resource group:
- Azure Portal
- Azure PowerShell
- Azure CLI
- Templates
- Azure SDKs

*Resource groups cannot be nested*
### Organization
- For authorization
	-  organize resources by who needs to administer them using RBACs
-  For life cycle
	-  if you delete a resource group, all resources are deleted
-  For billing
	-  easy way to group for usage in billing reports

## Tagging
Tags are name/value pairs of text data that can be applied to resources and resource groups

You can retrieve all resources in a subscriptions with a specific tag

Cannot be applied to all resources

## RBAC
- allow one user to manage VMs in a subscription while another to manage virtual networks
- allow database admins to manage SQL databases in a subscription
- allow user to manage all resources in a resource group
- allow application to access all resources in a resource group

Uses an **allow-model** for access, RBAC allows you to perform specific actions

### Best Practices
- separate duties within the team, allow only specific actions at a particular scope
- grant users the lowest privilege level possible to do their work
- use **Resource Locks** to ensure critical resources aren't modified

#### Resource Lock
Can be set to either Delete or Read-only

Can be applied to subscriptions, resource groups and to resources -> inherited at higher levels