# Configure Domain for Monitoring Active Directory

You can configure your Active Directory domain for monitoring in one of the following ways:

- Automatically when creating an organization

    This method is recommended for evaluation purposes in test environments. If any conflicts are detected with your current audit settings, automatic audit configuration will not be performed.For a full list of audit settings required for {{ MyVariables.ProductName_Overlord }} to collect comprehensive audit data and instructions on how to configure them, refer to [Configure IT Infrastructure for Auditing and Monitoring](../ConfigureITInfrastructure.md) .

    If you select to automatically configure audit in the target environment, your current audit settings will be checked on each data collection and adjusted if necessary.
- Manually.

Also, perform the following procedures:

- [Configure Basic Domain Audit Policies](/Configuration/AD/DomainAuditPolicies.md)  
		or [Configure Advanced Audit Policies](/Configuration/AD/AdvancedPolicy.md) . Either local or advanced audit policies must be configured to track changes to accounts and groups, and to identify workstations where changes were made.
- [Configure Object-Level Auditing](/Configuration/AD/ObjectLevel.md) 
- [Adjust Security Event Log Size and Retention Settings](/Configuration/AD/SecurityLogSize.md) 
- [Enable Secondary Logon Service](/Configuration/AD/SecondaryLogonService.md) 