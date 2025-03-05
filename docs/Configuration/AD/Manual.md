# Configure Domain for Monitoring Group Policy

You can configure your domain for monitoring Group Policy in one of the following ways:

- Automatically when creating an organization. This method is recommended for evaluation purposes in test environments. If any conflicts are detected with your current audit settings, automatic audit configuration will not be performed.For a full list of audit settings required for {{ MyVariables.ProductName_Overlord }} to collect comprehensive audit data and instructions on how to configure them, refer to [Configure IT Infrastructure for Auditing and Monitoring](../ConfigureITInfrastructure.md) . If you select to automatically configure audit in the target environment, your current audit settings will be checked on each data collection and adjusted if necessary.

- Manually. You need to adjust the same audit settings as those required for monitoring Active Directory. [Configure Domain for Monitoring Active Directory](ADManual.md) 