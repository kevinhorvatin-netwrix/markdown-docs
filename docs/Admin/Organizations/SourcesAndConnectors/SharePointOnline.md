# Add a Source and Connectors for SharePoint Online 

Follow the steps to add a SharePoint Online source and connector(s) to your organization. 
@Snippet:1Secure/Organization:ManagedOrgNav@ 
@Snippet:1Secure/SourcesAndConnectors:OrgSelectionStep@ 
@Snippet:1Secure/SourcesAndConnectors:StepClickAdd@ 
@Snippet:1Secure/SourcesAndConnectors:SelectDataSource@
![](../../../../Resources/Images/1Secure/AddSources_Exchange.png "Select Data Source (Step 1 of 3) pane")

Select **SharePoint Online**  and click Next.![](../../../../Resources/Images/1Secure/ConfigureSourceDetailsSharePoint.png "Configure Source Details (Step 2 of 3) pane")

On the Configure source details  (Step 2 of 3) pane, specify the following settings:

- @Snippet:1Secure/SourcesAndConnectors:SourceGroup@
- Tenant ID – @Snippet:1Secure/EntraIDApp:TenantID@
- @Snippet:1Secure/SourcesAndConnectors:CrawlSource@
- @Snippet:1Secure/SourcesAndConnectors:Credentials@

    - Client ID – @Snippet:1Secure/EntraIDApp:ClientID@
    - Client Secret – @Snippet:1Secure/EntraIDApp:ClientSecret@
    - @Snippet:1Secure/SourcesAndConnectors:DownloadCertificate@
    - @Snippet:1Secure/SourcesAndConnectors:DisplayName@

Click **Next**.![](../../../../Resources/Images/1Secure/AddSourceSharePointOnlineConnector.png "Choose New Connector (Step 3 of 3) pane")

The Choose new connector  (Step 3 of 3) pane lists two connectors for SharePoint Online. Specify the following:

- SharePoint Online Activity – Toggle the **SharePoint Online Activity** switch to ON to collect and monitor data for this connector. With this, you can generate activity reports on SharePoint Online data. See the [SharePoint Online](../../SearchAndReports/Activity.md#SharePoi)  topic for additional information.

    - Audit SharePoint Online read access – Select this checkbox to audit the files with read access in SharePoint Online
- SharePoint Online State – Toggle the **SharePoint Online State** switch to ON to collect and monitor data for this connector. With this, you can generate state-in-time reports on SharePoint Online data. See the [State In Time Risks Reports](../../SearchAndReports/StateInTime.md)  topic for additional information.

    - Collect state-in-time data for personal OneDrives – Select this checkbox to collect state-in-time data for personal OneDrives

Click **Finish**.

The SharePoint Online data source and connector(s) have been configured.