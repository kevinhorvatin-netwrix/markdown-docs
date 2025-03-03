# Add a Source and Connectors for SQL Server

Follow the steps to add a SQL Server data source and connector to your organization. 
@Snippet:1Secure/Organization:ManagedOrgNav@ 
@Snippet:1Secure/SourcesAndConnectors:OrgSelectionStep@ 
@Snippet:1Secure/SourcesAndConnectors:StepClickAdd@ 
@Snippet:1Secure/SourcesAndConnectors:SelectDataSource@
![](../../../../Resources/Images/1Secure/AddSources_Exchange.png "Select Data Source (Step 1 of 3) pane")

Select **SQL Server** and click **Next**.![](../../../../Resources/Images/1Secure/ConfigureSourceDetails(Step2-3).png "Configure Source Details (Step 2 of 3) pane") @Snippet:1Secure/SourcesAndConnectors:SiteSelectStep@

- @Snippet:1Secure/SourcesAndConnectors:NewSiteBullet@
- @Snippet:1Secure/SourcesAndConnectors:ExisSiteBullet@

    - @Snippet:1Secure/SourcesAndConnectors:NewSiteBullet2@
    - If the agent has already been configured for the site, the system will proceed with the SQL Server source and connector settings when you click *Next*.

            <madcap:change madcap:changes="untracked">Click </madcap:change>**Next**
            <madcap:change madcap:changes="untracked">.</madcap:change>![](../../../../Resources/Images/1Secure/ConfigureSourceDetails(Step2-3)a.png "Configure Source Details (Step 2 of 3) pane")

Specify the following settings:

- @Snippet:1Secure/SourcesAndConnectors:SourceGroup@
- SQL Server Name – Specify the name of the SQL Server instance, for example, StationDB\SQLExpress or StationSQL
- @Snippet:1Secure/SourcesAndConnectors:CrawlSource@
- @Snippet:1Secure/SourcesAndConnectors:Credentials@

    - Username – The username of <madcap:annotation madcap:createdate="2025-02-19T14:33:24.2538205+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="Or the username of an account to connect to SQL server?\r\n\r\nWhat permissions should the account have?" madcap:editor="AyeshaAzeem" madcap:editdate="2025-02-19T14:34:00.2814555+05:00">the SQL Server account</madcap:annotation>
    - Password – The password of the account

        The newly added credentials are also displayed in the drop-down menu.

Click **Next**.![](../../../../Resources/Images/1Secure/ChooseNewConnector(Step3of3).png "Choose New Connector (Step 3 of 3) pane")

The Choose new connector  (Step 3 of 3) pane lists one connector for SQL Server. Toggle the **SQL Logons** switch to ON to collect and monitor data for this connector. With this, you can generate logon reports on SQL Server data. See the [SQL Database](../../SearchAndReports/Activity.md#SQL)  topic for additional information.

Choose one option from the following:

- Audit all accounts – Select this option to audit all accounts within the connector
- Audit specific accounts – Select this option to audit only the specific account(s) within the connector. After selecting this option, specify the account(s) to be audited in the field below.  
To specify an account, enter its name and click the Add icon. To audit multiple accounts, add them one by one.

    To include all accounts in a domain, use the format: *MYDOMAIN\\**.
- Audit all accounts except – Select this option to audit all accounts within the connector, except for specific ones you want to exclude. After selecting this option, specify the accounts to be excluded in the field below.  
To specify an account, enter its name and click the Add icon. To exclude multiple accounts, add them one by one.

    To exclude all accounts in a domain, use the format: *MYDOMAIN\\**.

Click **Finish**.

The SQL Server data source and connector have been configured.