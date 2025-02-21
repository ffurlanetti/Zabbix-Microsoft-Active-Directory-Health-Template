# Microsoft Active Directory Domain Services (AD DS) Monitoring Template for Zabbix

This template is designed to monitor Microsoft Active Directory Domain Services (AD DS) in environments running Zabbix 7.0. to Zabbix 7.2. It provides comprehensive insights into the health, performance, and reliability of AD DS infrastructure, including critical parameters for domain controllers, replication health, user activity, and policy management.

## Overview

The Microsoft AD DS template for Zabbix includes items, triggers, graphs, and dashboards to provide real-time monitoring of Active Directory components. By using this template, administrators can proactively identify and resolve issues with domain controllers, monitor replication status, track user activity, and enforce security policies.
![My Image](https://github.com/ffurlanetti/Zabbix-Microsoft-Active-Directory-Health-Template/blob/main/Zabbix-Problems-Example.png)
![My Image](https://github.com/ffurlanetti/Zabbix-Microsoft-Active-Directory-Health-Template/blob/main/UserBadPassword-View.png)

### Key Features

- **Active Directory Health Monitoring**: Checks the overall health status of domain controllers and AD DS services.
- **Replication Monitoring**: Monitors replication status between domain controllers to ensure consistent data across the network.
- **Audit Users, Groups, and Policies**: Tracks changes to users, groups, and GPOs to ensure proper authorization and compliance.
- **Domain Controller Performance**: Monitors the performance of domain controllers to identify bottlenecks affecting AD services.
- **Authentication and Security**: Provides insights into authentication requests, failed logins, and AD security events.
- **Customizable Thresholds**: Pre-defined triggers with customizable thresholds for alerting on critical AD DS events.

## Requirements

- **Zabbix Server**: Version 7.0 to 7.2
- **Windows Server**: The template is compatible with Microsoft Windows Server 2012 R2, 2016, 2019, and 2022.
- **Permissions**: Requires a domain user with read access to Active Directory and WMI permissions.
- **Enable Advanced Audit Configuration**: The options are available in the file **DC_Audit_GPO.htm**, it needs to be enable on Domain Controllers.
- **Active Checks**: The hostname of the server needs to be the same in the Zabbix object and the Zabbix Agent config file.

## Template Details

| Metric                  | Description                                                |
|-------------------------|------------------------------------------------------------|
| Domain Controller Status| Monitors availability and operational status of DCs         |
| Replication Status      | Checks for replication issues across domain controllers     |
| NTDS Services           | Ensures that critical AD DS services are up and running     |
| Security Events         | Tracks logon failures and other security-related events     |
| User, Group, and Policy Audits | Monitors changes to AD users, groups, and GPOs       |

## Installation

1. **Import the Template**: In Zabbix, go to _Configuration > Templates_, click _Import_, and upload the template file.
2. **Assign Template to Hosts**: Apply the template "Template App Microsoft - ADDS - Health" to the Windows hosts that are configured as Active Directory Domain Controllers.
   ![My Image](https://github.com/ffurlanetti/Zabbix-Microsoft-Active-Directory-Health-Template/blob/main/Host_Template_Link_Example.png)
4. **Set User Permissions**: Ensure that the Zabbix user running the checks has adequate permissions for WMI and AD data access.
5. **Configure `zabbix_agent2.conf`**: Merge the contents of the current `zabbix_agent2.conf` with the settings provided in `example.zabbix_agent2_conf.txt` to ensure proper agent configuration.
6. **Configure Macros**: Adjust any macros for specific thresholds, domain names, or performance parameters as needed.

## Support and Compatibility

This template is actively maintained to support the latest versions of Zabbix and Microsoft Windows Server. Compatibility is tested with Zabbix 6.4 and 7.0, and Microsoft Windows Server 2012 R2, 2016, 2019, and 2022.

If you encounter any issues, feel free to contribute or report bugs in the project repository.

---

### License

This project is licensed as OpenSource.

---

### Author

**Fabio Furlanetti**  
Email: [fabiofurlanetti@hotmail.com](mailto:fabiofurlanetti@hotmail.com)

This README provides an overview of the AD DS template, steps for installation, and details on how to configure and use it within your Zabbix environment.
