# Add Organizations

Follow the steps to  add an organization.

On the {{ MyVariables.Website }}, on the **Home** page, select the Add organization icon to add an organization.![](../../../Resources/Images/1Secure/Organization_Adding.png)

On the Add Organization (Step 1 of 4) window, specify the following:

- Name – Specify a name for the organization
- Timezone – Select a timezone for the organization
- Country – Select a country for the organization
- Tags – Select tag(s) for the organization. Tags provide a way of adding metadata to the tenancies being managed. To specify multiple tags, select them one by one from the dropdown menu.
- Alert profile – Select an alert profile for the organization. Alert profiles enable you to group alert configurations and delivery notification settings together.
- Risk Profile – Select a risk profile for the organization. Risk profiles enable you to group thresholds together.
- Groups – Select a group for the organization. To assign an organization to multiple groups, select the groups one by one from the drop-down menu.

 Click **Next**.![](../../../Resources/Images/1Secure/AddOrganizationsSelectDataSource.png)

On the Select Data Source (Step 2 of 4) window, add a preferred data source to your organization:

- Active Directory
- Azure AD (now Microsoft Entra ID)
- Computer
- Exchange Online
- SharePoint Online

 See the [Sources and Connectors](SourcesAndConnectors/README.md)  topic for detailed information.![](../../../Resources/Images/1Secure/AddOrganizationsSites.png)

On the Configure source details (Step 3 of 4) window, add a site for your organization. Sites are used to signify physical groupings within the organization. Click **Next**. 

This step is displayed only when adding Active Directory and Computer sources. 

See the [Add Sites to Organization](AddSites.md)  topic for additional information.![](../../../Resources/Images/1Secure/AddOrganizationsAgent.png)

On the Configure source details (Step 3 of 4) window, follow the instructions to install  the agent. Please go to the [Install Agent](../../Install/InstallAgent.md) topic of the online help. Click **Next**.

Install the agent only for on-prem sources - Active Directory and Computer. This step is displayed only when adding these sources.![](../../../Resources/Images/1Secure/AddOrganizationsSourceDetails.png)

On the Configure source details (Step 3 of 4) window, specify your source settings. See the [Sources and Connectors](SourcesAndConnectors/README.md)  topic for additional information.![](../../../Resources/Images/1Secure/AddOrganizationsSourcesAndConnectors.png)

On the Choose new connector (Step 4 of 4) window, add the connectors for your sources on. See the [Sources and Connectors](SourcesAndConnectors/README.md)  topic for additional information. 

Click **Finish** or **Save & Add another source** to add a source for your organization. 

 The organization is now added.