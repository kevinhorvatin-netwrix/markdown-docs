# Add a Source and Connectors for Active Directory

Follow the steps to add an Active Directory data source and connector(s) to your organization. @Snippet:1Secure/Organization:ManagedOrgNav@ @Snippet:1Secure/SourcesAndConnectors:OrgSelectionStep@ @Snippet:1Secure/SourcesAndConnectors:StepClickAdd@ @Snippet:1Secure/SourcesAndConnectors:SelectDataSource@![](../../../../Resources/Images/1Secure/AddSources_Exchange.png "Select Data Source (Step 1 of 3) pane")

Select **Active Directory** and click **Next**.![](../../../../Resources/Images/1Secure/ConfigureSourceDetails(Step2-3).png "Configure Source Details (Step 2 of 3) pane") @Snippet:1Secure/SourcesAndConnectors:SiteSelectStep@

- @Snippet:1Secure/SourcesAndConnectors:NewSiteBullet@
- @Snippet:1Secure/SourcesAndConnectors:ExisSiteBullet@

    - @Snippet:1Secure/SourcesAndConnectors:NewSiteBullet2@
    - If the agent has already been configured for the site, the system will proceed with the Active Directory source and connector settings when you click *Next*.

Click **Next**.![](../../../../Resources/Images/1Secure/AD_ConfigSourceDetails(step2of3).png "Configure Source Details (Step 2 of 3) pane")

Specify the following settings:

- @Snippet:1Secure/SourcesAndConnectors:SourceGroup@
- Domain Name – Specify the fully qualified domain name of the Active Directory domain you want to create a source for.
- @Snippet:1Secure/SourcesAndConnectors:CrawlSource@.
- Service Account OUs – Specify organizational units (OUs) to exclude their service accounts from billable domain accounts so that they are not audited. To specify an organizational unit (OU), enter its name and click the Add icon. To specify multiple organizational units, add them one by one.
- @Snippet:1Secure/SourcesAndConnectors:Credentials@

    - <madcap:annotation madcap:createdate="2025-02-19T13:05:16.6971402+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="We should also document the minimum permissions this account should have." madcap:editor="AyeshaAzeem" madcap:editdate="2025-02-19T13:05:31.8109656+05:00">Username </madcap:annotation>– The username of an Active Directory account in Domain\Username format
    - Password – The password of the Active Directory account
    - @Snippet:1Secure/SourcesAndConnectors:DisplayName@

 Click **Next**.![](../../../../Resources/Images/1Secure/AD_ChooseNewConnector.png "Choose New Connector (Step 3 of 3) pane")

The Choose new connector (Step 3 of 3) pane lists three connectors for Active Directory. Specufy the following:

- Active Directory Activity – Toggle the **Active Directory Activity** switch to ON to collect and monitor data for this connector. With this, you can generate activity reports on Active Directory data. See the [Active Directory](../../SearchAndReports/Activity.md#Active)  topic for additional information.
- Activity Directory Logons – Toggle the **Active Directory Logons** switch to ON to collect and monitor data for this connector. With this, you can generate logon reports on Active Directory data. See the [Active Directory](../../SearchAndReports/Activity.md#Active)  topic for additional information.
- Activity Directory State – Toggle the **Active Directory State** switch to ON to collect and monitor data for this connector. With this, you can generate state-in-time reports on Active Directory data. See the [State In Time Risks Reports](../../SearchAndReports/StateInTime.md)  topic for additional information.

Optionally, select the following for each <madcap:annotation madcap:createdate="2025-02-19T13:14:49.6114364+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="In the caution below, add a link to info that explains how the service can be enabled/disabled." madcap:editor="HassaanKhan" madcap:editdate="2025-02-19T16:38:18.7367412+05:00">connector</madcap:annotation>:

- @Snippet:1Secure/SourcesAndConnectors:TrafficNetCompression@ @Snippet:1Secure/SourcesAndConnectors:SameDomainProducts@

- @Snippet:1Secure/SourcesAndConnectors:AdjustAutoAudit@

            <madcap:annotation madcap:createdate="2025-02-19T11:54:34.3716386+05:00" madcap:creator="HassaanKhan" madcap:initials="HA" madcap:comment="Need to work on finding the kind of automatic audit settings " madcap:editor="AyeshaAzeem" madcap:editdate="2025-02-19T13:19:30.6777656+05:00">C</madcap:annotation>lick **Finish**.

The Active Directory data source and connector(s) have been configured.