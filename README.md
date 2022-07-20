# Cloud Roles and Operations Management

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/list.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/list.png)

## What is a well-managed cloud?

A well-managed cloud is one that where the items in the below list are considered and managed. This list represent an expansion of the 5 pillars of the [**Microsoft Azure Well-Architected Framework**](https://docs.microsoft.com/azure/architecture/framework/?WT.mc_id=Portal-fx), and are suggested as a framework for managing Azure environments.

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

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/compliant.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/compliant.png)

### Observable (WAF: Operational Excellence)

Services that can be used to manage observability in Azure include:
- Azure Monitor
- Log Analytics
- Microsoft Sentinel
- Defender for Cloud
- AAD Audit and Sign-in
- Activity Log
- Network Watcher

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/observable.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/observable.png)

### Recoverable (WAF: Reliability)

Services that can be used to manage recovery in Azure include:
- Azure Backup
- Azure Site Recovery
- Devops Redeploy

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/recoverable.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/recoverable.png)

### Reliable (WAF: Reliability)

Services that can be used to manage reliability in Azure include:
- Azure Advisor
- Azure Chaos Studio
- Azure Monitor
- Log Analytics
- Workbooks
- Alerts that prevent downtime or reduce MTTR

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/reliable.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/reliable.png)

### Performant (WAF: Performance)

Services that can be used to manage performance in Azure include:
- Azure Advisor
- Azure Monitor
- Log Analytics
- Microsoft Sentinel
- Metrics
- Workbooks
- Network Watcher

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/performant.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/performant.png)

### Updateable (WAF: Reliability)

Services that can be used to manage updates in Azure include:
- Azure Advisor
- Customer managed via UM and LAWS
- Planned maintenance (Service Health)
- Devops Update

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/updateable.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/updateable.png)

### Cost Managed (WAF: Cost Management)

Services that can be used to manage cost in Azure include:
- Azure Advisor
- Cost Management & Billing
- EA Portal (Account hierarchy, credit balance, cost for each department, account, and subscription)

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/cost.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/cost.png)

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

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/secure.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/secure.png)

### Inventoried (WAF: Operational Excellence)

Services that can be used to manage inventory in Azure include:
- Azure Resource graph
- Defender for Cloud (Inventory)
- Automation (Change Tracking & Inventory)

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/inventory.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/inventory.png)

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

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/operationalexcellence.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/operationalexcellence.png)

Activities, alerts and policies for managing services, platform resources, application resources and solutions are presented for these items in this project.

### Example 1: Azure Virtual Desktop

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/avd.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/avd.png)

### Example 2: ExpressRoute

[![](https://github.com/Azure/cloud-rolesandops/blob/main/images/exr.png)](https://github.com/Azure/cloud-rolesandops/blob/main/images/exr.png)

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