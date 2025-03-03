# Configure Active Directory Domain for Monitoring

For AD domain monitoring with {{ MyVariables.ProductName_Overlord }}, the domain should be configured as explained below.

## Domain Audit Policy Settings

Effective domain controllers policy settings must be configured as listed in the table below.

| Policy | Audit type |
| --- | --- |
| Audit account management<br> | *"Success"*<br> |
| Audit directory service access<br> | *"Success"* |
| Audit logon events<br> | *"Success"* |

You can configure either **Basic domain audit policies**, or **Advanced domain audit policies**.

- To configure these settings automatically using {{ MyVariables.ProductName_Overlord }}, refer to [Active Directory: automatic configuration](/Configuration/AD/Auto.md)  section.
- To configure them manually, refer to [Configure Advanced Audit Policies](/Configuration/AD/DomainAuditPolicies.md)  section.

## Audit Settings for AD Partitions

Required object-level audit settings for the Active Directory partition must be configured as described in the next sections. 

### Domain Partition

Object-level audit settings for the Domain partition must be configured to audit for *Success* of all access operations except the following: *Full Control*, *List Contents*, *Read All Properties* and *Read Permissions*.

These settings must be configured for **Everyone** security principal and applied to **This object and all descendant objects**. 

- You can configure these settings automatically using {{ MyVariables.ProductName_Overlord }}, as described in [Configure Domain for Monitoring Active Directory](/Configuration/AD/ADManual.md)  section.
- To configure them manually, refer to [Configure Object-Level Auditing](/Configuration/AD/ObjectLevel.md)  section.

### Configuration and Schema Partitions

Object-level audit settings for the Configuration and **Schema** partitions must be configured to audit for *Success* of all access operations except the following: *Full Control*, *List Contents*, *Read All Properties* and *Read Permissions*

These settings must be configured for **Everyone** security principal and applied to **This object and its descendant objects**.

- You can configure these settings automatically using {{ MyVariables.ProductName_Overlord }}, as described in [Active Directory: automatic configuration](/Configuration/AD/Auto.md)  section.
- To configure them manually, refer to [Configure Object-Level Auditing](/Configuration/AD/ObjectLevel.md)  section.

## Security Event Log Settings

**Security event log** settings for the domain controllers should be configured as follows:

| Setting | Value |
| --- | --- |
| Max event log size | 4 GB |
| Retention method | *Overwrite events as needed* |
| Auto-archiving | Enabled |

- You can configure these settings automatically using {{ MyVariables.ProductName_Overlord }}, as described in [Active Directory: automatic configuration](/Configuration/AD/Auto.md)  section.
- To configure them manually, refer to [Adjust Security Event Log Size and Retention Settings](/Configuration/AD/SecurityLogSize.md)  section.