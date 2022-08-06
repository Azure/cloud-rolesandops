# Cloud Roles and Operations Management

Prescriptive guidance for cloud roles, tasks, and initiatives for targeted operations. It is intended as input to a cloud [operating model](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/operating-model) and operations plan.

[![](/images/list.png)](/images/list.png)

Why do we need an [operating model](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/operating-model/) and operations plan for the cloud?
- _"Delivering on a cloud strategy requires solid planning, readiness, and adoption. But it's the ongoing operation of the digital assets that delivers tangible business outcomes."_ - [CAF](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/manage/)
- Operating a cloud is a [shared responsibility](https://docs.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility).
- Architecture decisions during the adoption phase need to be reviewed over time to keep up with evolving technology and business requirements. Enhancements that deliver better security, reliability and performance are examples that necessitate active operations.
- Architecture tradeoffs often need to be mitigated by sound operations. An example is to execute a well-understood, practiced system recovery within an RTO, where cost constraints may have resulted in an architecture without highly available components. 
- Typical Architecture tradeoffs:
    - [Security vs Reliability](https://docs.microsoft.com/en-us/azure/architecture/framework/security/security-tradeoffs#security-vs-reliability)
    - [Security vs Cost Optimization](https://docs.microsoft.com/en-us/azure/architecture/framework/security/security-tradeoffs#security-vs-cost-optimization)
    - [Security vs Operational Excellence](https://docs.microsoft.com/en-us/azure/architecture/framework/security/security-tradeoffs#security-vs-operational-excellence)
    - [Cost vs Reliability](https://docs.microsoft.com/en-us/azure/architecture/framework/cost/tradeoffs#cost-vs-reliability)
    - [Cost vs Performance Efficiency](https://docs.microsoft.com/en-us/azure/architecture/framework/cost/tradeoffs#cost-vs-performance-efficiency)
    - [Cost vs Operational Excellence](https://docs.microsoft.com/en-us/azure/architecture/framework/cost/tradeoffs#cost-vs-operational-excellence)
    - [Performance Efficiency vs Operational Excellence](https://docs.microsoft.com/en-us/azure/architecture/framework/scalability/tradeoffs#performance-efficiency-vs-operational-excellence)
    - [Performance Efficiency vs Reliability](https://docs.microsoft.com/en-us/azure/architecture/framework/scalability/tradeoffs#performance-efficiency-vs-reliability)
    - [Performance Efficiency vs Security](https://docs.microsoft.com/en-us/azure/architecture/framework/scalability/tradeoffs#performance-efficiency-vs-security)
- Important questions like _'did I architect my solution cost efficiently, when the expected system load was still an unknown, or did I over-provision?'_ need to be answered once services go fully into production.
- A [well-managed cloud](#what-is-a-well-managed-cloud) needs an operating model with an aligned operations plan, and modern tools to focus our management efforts.

## Artifacts

- [Excel spreadsheet](https://github.com/Azure/cloud-rolesandops/releases/download/v0.91b/cromv09.xlsx)
    - Use as-as, or import to Devops (e.g, [Azure Devops work items](https://docs.microsoft.com/en-us/azure/devops/boards/queries/import-work-items-from-csv?view=azure-devops) or [Github issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/creating-an-issue)) or an ITSM tool
    - Includes recommended tasks, RACI, frequency, links and notes
- [Basic Azure portal workbook](https://github.com/Azure/cloud-rolesandops/releases/download/v0.91b/Planning.Guide.for.Cloud.Roles.and.Operations.Management.v0.91b.workbook)
    - Environment information along with task and initiative direction in the Azure portal
    - Also includes service management information, suggested documentation and a a 'management score' (based on key indicators of management practices in the environment)
    - Documentation templates
    [![](/images/wbdocs.png)](/images/wbdocs.png)
    - Task definitions
    [![](/images/wbtasks.png)](/images/wbtasks.png)
    - Initiative definitions
    [![](/images/wbinitiatives.png)](/images/wbinitiatives.png)
    - Environment
    [![](/images/wbenv.png)](/images/wbenv.png)
    - Management score
    [![](/images/wbscore.png)](/images/wbscore.png)
    - [How to import a workbook](/updateable%20workbook/ImportWorkbook.md)
- [Updateable Azure portal workbook](/updateable%20workbook)
    - Updateable version of the workbook (allows simple excel updates that flow through to Azure)
    - Requires Excel on the web, an office script, an Azure Logic App, and an Azure Log Analytics Workspace

## Table of included guidance

| Category  | Technology  | Version  | Tasks  |
| ------------ | ------------ | ------------ | ------------ |
| Foundation  | Generic  | Pilot  | 60 |
| Platform  | Azure Bastion  | Pilot  | 11 |
| Platform  | Azure Firewall  | Pilot  | 48 |
| Platform  | Azure Key Vault  | Pilot  | 33 |
| Platform  | Azure Storage  | Pilot  | 33 |
| Platform  | Azure Virtual Network  | Pilot  | 53 |
| Platform  | ExpressRoute  | Pilot  | 43 |
| Service  | Active Directory Domain Services | Pilot  | 21 |
| Service  | Azure Active Directory | Pilot  | 44 |
| Service  | Azure Advisor | Pilot  | 15 |
| Service  | Azure Backup | Pilot  | 49 |
| Service  | Azure Monitor | Pilot  | 75 |
| Service  | Azure Site Recovery | Pilot  | 30 |
| Service  | Azure Update Management | Pilot  | 29 |
| Service  | Defender for Cloud  | Pilot  | 33 |
| Service  | Microsoft Sentinel  | Pilot  | 48 |
| Application  | Application Gateway  | Pilot  | 48 |
| Application  | Azure App Service | Pilot  | 46 |
| Application  | Application Gateway  | Pilot  | 48 |
| Application  | Azure Data Factory  | Pilot  | 42 |
| Application  | Azure Databricks  | Pilot  | 34 |
| Application  | Azure SQL  | Pilot  | 96 |
| Application  | Azure Virtual Machines  | Pilot  | 53 |
| Solution  | Azure Virtual Desktop  | Pilot  | 59 |
| Solution  | SAP on Azure  | Pilot  | 46 |

## What is a well-managed cloud?

A well-managed cloud is one that is compliant, observable, recoverable, reliable, performant, updateable, cost managed, secured, inventoried and operationally excellent. This list represent an expansion of the 5 pillars of the [**Microsoft Azure Well-Architected Framework**](https://docs.microsoft.com/azure/architecture/framework/?WT.mc_id=Portal-fx), and is suggested as a framework for managing Azure environments.

### Compliant (WAF: Security)

Services that can be used to manage compliance in Azure include:
- Azure Devops Services
- Github
- Azure Policy
- Defender for Cloud
- Azure Monitor
- Azure Resource Graph
- In-guest VM Policy
- Desired State Configuration

[![](/images/compliant.png)](/images/compliant.png)

### Observable (WAF: Operational Excellence)

Services that can be used to manage observability in Azure include:
- Azure Monitor
- Log Analytics
- Microsoft Sentinel
- Defender for Cloud
- AAD Audit and Sign-in
- Activity Log
- Network Watcher

[![](/images/observable.png)](/images/observable.png)

### Recoverable (WAF: Reliability)

Services that can be used to manage recovery in Azure include:
- Azure Backup
- Azure Site Recovery
- Devops Redeploy

[![](/images/recoverable.png)](/images/recoverable.png)

### Reliable (WAF: Reliability)

Services that can be used to manage reliability in Azure include:
- Azure Advisor
- Azure Chaos Studio
- Azure Monitor
- Log Analytics
- Workbooks
- Alerts that prevent downtime or reduce MTTR

[![](/images/reliable.png)](/images/reliable.png)

### Performant (WAF: Performance)

Services that can be used to manage performance in Azure include:
- Azure Advisor
- Azure Monitor
- Log Analytics
- Microsoft Sentinel
- Metrics
- Workbooks
- Network Watcher

[![](/images/performant.png)](/images/performant.png)

### Updateable (WAF: Reliability)

Services that can be used to manage updates in Azure include:
- Azure Advisor
- Customer managed via UM and LAWS
- Planned maintenance (Service Health)
- Devops Update

[![](/images/updateable.png)](/images/updateable.png)

### Cost Managed (WAF: Cost Management)

Services that can be used to manage cost in Azure include:
- Azure Advisor
- Cost Management & Billing
- EA Portal (Account hierarchy, credit balance, cost for each department, account, and subscription)

[![](/images/cost.png)](/images/cost.png)

### Secured (WAF: Security)

Services that can be used to manage security in Azure include:
- Azure Advisor
- AAD
- MFA
- CA
- PIM
- Role Entitlement
- Policy
- In-Guest Policy
- Network Watcher
- Defender for Cloud
- Microsoft Sentinel
- Key Vault
- DDoS
- NSG

[![](/images/secure.png)](/images/secure.png)

### Inventoried (WAF: Operational Excellence)

Services that can be used to manage inventory in Azure include:
- Azure Resource graph
- Defender for Cloud (Inventory)
- Automation (Change Tracking & Inventory)

[![](/images/inventory.png)](/images/inventory.png)

### Operational Excellence (WAF: Operational Excellence)

Services that can be used to provide operational excellence in Azure include:
- Azure Advisor
- People
- Process
- RACI
- Dashboards
- Reports
- Reviews
- Automation (AA, LA, Functions)

[![](/images/operationalexcellence.png)](/images/operationalexcellence.png)

## Examples

Activities, alerts and policies for Azure services, platform resources, application resources and solutions are presented for each of the critical areas of management in this project.

### Example 1: Azure Virtual Desktop

[![](/images/avd.png)](/images/avd.png)

### Example 2: ExpressRoute

[![](/images/exr.png)](/images/exr.png)

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.