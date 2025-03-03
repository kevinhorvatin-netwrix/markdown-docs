# Add a Source and Connectors for Microsoft Entra ID

Follow the steps to add a {{ MyVariables.Azure_AD_app }} data source and connector(s) to your organization. @Snippet:1Secure/Organization:ManagedOrgNav@ 
@Snippet:1Secure/SourcesAndConnectors:OrgSelectionStep@ 
@Snippet:1Secure/SourcesAndConnectors:StepClickAdd@ 
@Snippet:1Secure/SourcesAndConnectors:SelectDataSource@
![](../../../../Resources/Images/1Secure/AddSources_Exchange.png "Select Data Source (Step 1 of 3) pane")

Select **Entra ID** and click **Next**.![](../../../../Resources/Images/1Secure/Entra_ConfigSourceDetails(Step2of3).png "Configure Source Details (Step 2 of 3) pane")

On the Configure source details  (Step 2 of 3) pane, specify the following settings:

- @Snippet:1Secure/SourcesAndConnectors:SourceGroup@
- Tenant ID – @Snippet:1Secure/EntraIDApp:TenantID@
- @Snippet:1Secure/SourcesAndConnectors:CrawlSource@
- Service Account Entra ID Groups – Specify {{ MyVariables.Azure_AD_app }} groups to exclude their service accounts from billable domain accounts so that they are not audited. To specify a {{ MyVariables.Azure_AD_app }} group, enter its name and click the **Add** icon. To specify multiple {{ MyVariables.Azure_AD_app }} groups, add them one by one.
- @Snippet:1Secure/SourcesAndConnectors:Credentials@

    - Client ID – @Snippet:1Secure/EntraIDApp:ClientID@
    - Client Secret – @Snippet:1Secure/EntraIDApp:ClientSecret@
    - @Snippet:1Secure/SourcesAndConnectors:DownloadCertificate@
    - @Snippet:1Secure/SourcesAndConnectors:DisplayName@

Click **Next**.![](../../../../Resources/Images/1Secure/Entra_Connector(Step3of3).png "Choose New Connector (Step 3 of 3) pane")

The Choose new connector  (Step 3 of 3) pane lists three connectors for {{ MyVariables.Azure_AD_app }}. Specify the following:

- Entra ID Activity – Toggle the **Entra ID Activity** switch to ON to collect and monitor data for this connector. With this, you can generate activity reports on {{ MyVariables.Azure_AD_app }} data. See the [Microsoft Entra ID](../../SearchAndReports/Activity.md#Microsof)  topic for additional information.
- Entra ID Logons – Toggle the **Entra ID Logons** switch to ON to collect and monitor data for this connector. With this, you can generate logon reports on {{ MyVariables.Azure_AD_app }} data. See the [Microsoft Entra ID](../../SearchAndReports/Activity.md#Microsof)  topic for additional information.

    - <madcap:annotation madcap:createdate="2025-02-19T13:40:25.2287573+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="What will the system do when none of the checkboxes is selected?" madcap:editor="AyeshaAzeem" madcap:editdate="2025-02-19T13:40:38.6900106+05:00">Collect </madcap:annotation>Failed Logons – Select this checkbox to collect the failed logon data for {{ MyVariables.Azure_AD_app }} logon reports.
    - Collect Successful Logons – Select this checkbox to collect the successful logon data for {{ MyVariables.Azure_AD_app }} logon reports.

- Entra ID State – Toggle the **Entra ID State** switch to ON to collect and monitor data for this connector. With this, you can generate state-in-time reports on {{ MyVariables.Azure_AD_app }} data. See the [State In Time Risks Reports](../../SearchAndReports/StateInTime.md)  topic for additional information.

Click **Finish**.

The {{ MyVariables.Azure_AD_app }} data source and connector(s) have been configured.