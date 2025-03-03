# Add a Source and Connectors for Exchange Online

Follow the steps to add an Exchange Online data source and connector(s) to your organization. @Snippet:1Secure/Organization:ManagedOrgNav@ @Snippet:1Secure/SourcesAndConnectors:OrgSelectionStep@ @Snippet:1Secure/SourcesAndConnectors:StepClickAdd@ @Snippet:1Secure/SourcesAndConnectors:SelectDataSource@![](../../../../Resources/Images/1Secure/AddSources_Exchange.png "Select Data Source (Step 1 of 3) pane")

Select **Exchange Online** and click **Next**.![](../../../../Resources/Images/1Secure/ExchangeOnline_ConfigSourceDetails.png "Configure Source Details (Step 2 of 3) pane")

On the Configure source details  (Step 2 of 3) pane, specify the following settings:

- @Snippet:1Secure/SourcesAndConnectors:SourceGroup@
- Tenant ID – @Snippet:1Secure/EntraIDApp:TenantID@
- @Snippet:1Secure/SourcesAndConnectors:CrawlSource@
- @Snippet:1Secure/SourcesAndConnectors:Credentials@

    - Client ID – @Snippet:1Secure/EntraIDApp:ClientID@
    - Client Secret – @Snippet:1Secure/EntraIDApp:ClientSecret@
    - @Snippet:1Secure/SourcesAndConnectors:DownloadCertificate@
    - @Snippet:1Secure/SourcesAndConnectors:DisplayName@

Click **Next**.![](../../../../Resources/Images/1Secure/AddSources_Exchange3.png "Choose new connector (Step 3 of 3) pane")

The Choose new connector pane  (Step 3 of 3) lists one connector for Exchange Online. Specify the following:

- Exchange Online Activity – Toggle the **Exchange Online Activity** switch to ON to collect and monitor data for this connector. With this, you can generate activity reports on Exchange Online data. See the [Exchange Online](../../SearchAndReports/Activity.md#Exchange)  topic for additional information.

    - Collect non-owner mailbox audit data – Select this checkbox to collect data for the All Exchange Online Non-Owner Mailbox Access Events report. See the [Exchange Online](../../SearchAndReports/Activity.md#Exchange)  topic for additional information.

        To collect the data for this report, you need to set up non-owner mailbox access auditing. See the [Settings for Non-Owner Mailbox Access Audit: Using Application](../../../Configuration/ExchangeOnlineNonOwner.md)  topic for additional information.

Click **Finish**.

The Exchange Online data source and connector have been configured.