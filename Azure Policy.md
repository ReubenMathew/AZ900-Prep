# Azure Policy
## Governance
You need governance when:
- multiple teams are working in azure
- multiple subscriptions in your tenant
- regulatory requirement have to be enforced
- ensure all standards are followed for IT resources

## IT Compliance with *Azure Policy*
**Azure Policy** is an Azure service used to create, assign and manage policies to stay compliant with corporate standards and service-level agreements (SLAs)

**Policy Definition:** expresses what to evaluate and what action to take (e.g. ensure all websites are secured with HTTPS, force versioning, disable certain resources)

To apply a policy use the Azure portal or in the CLI using the `Microsoft.PolicyInsights` extension 

You can also use policy to identify resources that aren't compliant with policy assignment

Once you've defined policy definitions, you need to assign them. A policy assignment is a definition that has been assigned in a scope (from full subscription to a resource group)

### Policy effects
Requests to create or update a resource through Azure Resource Manager are evaluated by Azure Policy first. Policy creates a list of all assignments that apply to the resource and then evaluates the resource against each definition.

| Policy Effect | What happens? |
| - | - |
| Deny | The resource creation/update fails due to policy. |
| Disabled | The policy rule is ignored (disabled). Often used for testing. |
| Append | Adds additional parameters/fields to the requested resource during creation or update. A common example is adding tags on resources such as Cost Center or specifying allowed IPs for a storage resource. |
| Audit, AuditIfNotExists | Creates a warning event in the activity log when evaluating a non-compliant resource, but it doesn't stop the request. |
| DeployIfNotExists | Executes a template deployment when a specific condition is met. For example, if SQL encryption is enabled on a database, then it can run a template after the DB is created to set it up a specific way.

You can delete policy requirements through the portal or through the CLI like this:
```Powershell
Remove-AzPolicyAssignment \-Name 'audit-vm-manageddisks' \-Scope '/subscriptions/<subscriptionID>/resourceGroups/<resourceGroupName>'
```

### Policy Initiatives
- initiatives simplify the process of managing and assigning definitions by grouping a set of policies into an item
- e.g. create an initiative called "Enable Monitoring" with a goal to monitor all security recommendations in **Azure Security Center**


## Enterprise Governance Management
- **Azure Management Groups** are containers for managing access, policies and compliance across multiple subscriptions
- manage subscriptions more effectively using **Azure Policy** and **Azure RBACs**
	- these provide distinct governance conditions that can apply to each group
	- the resources and subscriptions you assign to a management group inherit the conditions that you apply to that management group
- good for managing user access, use Resource Groups for resource access

## Azure Blueprint
Used for auditing, traceability, and compliance

A declarative way to orchestrate deployments of various resource templates such as:
- role assignments
- policy assignments
- Azure Resource Manager templates
- Resource groups

### Difference with Resource Manager Templates
- Azure blueprints are designed for environment setup
	- this consists of a set of resource groups, policies, role assignment and resource manager template deployments
	- A blueprint is the package that brings all of these together through a CI/CD pipeline
- They are basically the same but a Resource Manager Template doesn't exist natively in Azure
	- Resource Manager Templates are stored locally or in source control

### Difference with Azure Policy
- a blueprint is package for composing sets of standards, patterns and requirements related to Azure services implementation
- a policy is default allow and explicit-deny focused on resource properties

## Compliance Manager
- The **Microsoft Privacy Statement** explains what and how microsoft processes data
- **Microsoft Trust Center** is a website resource containing information and details on how Microsoft implements and supports security, privacy compliance and transparency in all Microsoft products/services
- **Service Trust Portal** hosts the Compliance Manager server
	- public site for publishing audit reports (downloadable)
- **Compliance Manager**
	- workflow-based risk assessment dashboard within the Service Trust Portal (STP)
	- enables tracking, assignment and verification of your org's compliance activities related to Office 365, Dynamics 365 and Azure

## Service Health Monitoring
### **Azure Monitor:**
- maximizes availability and performance or application
- Helps understand how applications are performing and identifies issues affecting them
- cannot create policy assignment from Azure monitor

#### Data Sources
- application monitoring data
- guest OS monitoring data
- Azure resource monitoring data
- Azure subscription monitoring data
- Azure tenant monitoring data

#### Diagnostic Settings
- enable guest-level monitoring
- collect performance data
- enable event logs
- enable/disable crash dumps
- send diagnostic data to other services
- configure agent settings

#### Getting more data
- application insights
- Azure monitor
- Azure monitor for VMs

#### Responding to Alert Conditions
- Alerts
	- Azure Monitor notifies you of critical conditions using alerts
	- can attempt to take corrective actions
	- based on metrics, alerts can be provided in real-time 
- Autoscale
	- ensures you have the right amount of resources running to manage application load
	- enables you to create rules that use metrics (used by **Azure Monitor**) to determine when to add resource to handle load increases
	- Can reduce costs for removing resources not being used
	- can specify a min and max number of instances

#### Visualize Monitoring Data
- dashboards
- views
- Power BI


#### Azure Service Health
- full suite that provides personalized guidance and support
- **Azure Status** provides global view of health state of Azure services
- **Service Health** provides with a customizable dashboard that tracks the state of Azure services
- **Resource Health** helps diagnose when an Azure service affects your resources