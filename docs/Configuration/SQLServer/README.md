# SQL Server

{{ MyVariables.ProductName_Overlord }} relies on native logs for collecting audit data. Therefore, successful change and access auditing requires a certain configuration of native audit settings in the audited environment and on the {{ MyVariables.ProductName_Overlord }} console computer. It is recommended to configure the IT infrastructure for automatic monitoring; however, you can also configure it manually if <madcap:annotation madcap:createdate="2024-11-22T17:01:32.4650197+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="Provide a link to topics that discuss auto and manual configuration of the infrastructure.\r\n\r\nFor auto, there should be info as to what is configured\r\nFor manual configuration, we need to provide the steps." madcap:editor="AyeshaAzeem" madcap:editdate="2024-11-22T17:03:26.0494636+05:00">needed</madcap:annotation>. You may also need to enable certain built-in Windows services, etc. 

 Your current audit settings will be checked on each data collection and <madcap:annotation madcap:createdate="2024-11-14T18:12:47.8287943+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="how? Also what if customer has a configuration that is changed every time on data collection?" madcap:editor="AyeshaAzeem" madcap:editdate="2024-11-22T17:04:24.8319176+05:00">adjusted if necessary</madcap:annotation>. Proper audit configuration is required to ensure audit data integrity, otherwise your change reports may contain warnings, errors, or incomplete audit data.

## SQL Server Monitoring Scope @Snippet:_CrossProduct/1Secure/SQLServerConf:SQLSeverMonitoringScope@

## Next Steps

Remember to do the following:

- Configure a Data Collecting Account as described in the [Permissions for SQL Server Auditing](Permissions.md))  topic.
- Configure ports as described in the [SQL Server Ports](Ports.md))  topic.