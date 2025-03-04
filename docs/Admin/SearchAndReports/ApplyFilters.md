# Apply Filters

Filters are used to narrow your search results. You can create your own filters or select one of the reports with the predefined filters. To create a unique set of filters, you can: 

- Add different filters to your search. Search results will be sorted by all selected filters since they  work as a logical conjunction (e.g., Who*: Administrator* <u>AND</u> Action*: Added*).
- Specify several values in the same filter to search for any of them (e.g.,    Action*: Modified* <u>OR </u>Action*: Removed*). To do this, select a filter again and specify a new value.
- Spaces do not separate values,  so the whole expression will be included in your search as a single value. For example, if you want to search for any of three names, do not enter  *Anna Mark Bill* but instead create a separate filter entry for each name.![](../../../Resources/Images/1Secure/ReportsMain.png "Activity Reports pane")

All reports on the **Reports** &gt; **Activity** tab are associated with the respective alerts. Click the **Alerts Timeline Dashboard** in the upper left corner of the page to view the alerts for your organization. See the [Alerts](../Alerts/Alerts.md)  topic for additional information. 

| Icon | Description |
| --- | --- |
| <br>![](../../../Resources/Images/1Secure/Search_Icon.png)<br> | Info Icon. Click the Info Icon to view the activity records details. |

Follow the steps to apply filters to your search.

Select the **Reports**&gt; **Activity** tab.![](../../../Resources/Images/1Secure/Search_Filters.png "Activity reports")

You can also access the **Reports** &gt; **Activity** page from your organization's page. On your Home screen, click **Configure** &gt; **Reports** in the right upper corner of the page.![](../../../Resources/Images/1Secure/ReportsReportAccess.png "Organization data sources list")

 Select a filter from the Filter drop-down menu. See the [Filter Descriptions](#Filter))  topic for additional information. 

You must specify three columns: Filter, Operator, and Value. You may also select more than one filter. To review the Operator filter options, see the [Filter Values](FilterOperators.md))  topic for additional information.

If required, specify the property change filters. 

{{ MyVariables.ProductName_Overlord }} comes with the advanced filtering options.  Not all the activity records have the property changes, but only those with the property change on that record. For example, if the permission on the Active Directory has been added or resource ID in AzureAD has been removed.![](../../../Resources/Images/1Secure/ReportsPropertyChanges.png "Filter property")

The drop-down list in the **Property** field shows all the properties retrieved in your records' list below the Search bar. It varies depending on the displayed records.  You can filter the required Property, Action, Value operator, and Value within the list. The property changes are dynamic and are not related to a given report directly but the activity records. If the query changes, the shown property changes may also change.![](../../../Resources/Images/1Secure/Search_Search Function.png "Filters list")

Click Search to find and view your reports. The reports are displayed with the predefined filters. Your search results will display in the table.![](../../../Resources/Images/1Secure/Search_SearchResults.png "Filter results")

Click the required activity record from the grid view  the activity record details. You can see who, when, or where was the activity made.![](../../../Resources/Images/1Secure/ActivityRecordDetails.png "Activity record details")

Navigate from one report to another by selecting **Prev** or **Next**. This will directly upload the details of the selected report. 

You can also create your own reports with custom filters. See the [Custom Reports](CustomReports.md))  topic for additional information.

## Filter Descriptions

This table provides a list of filters and descriptions.

| Filter | Description |
| --- | --- |
| Action<br> | Select an action type from the list (Added, Removed, Modified, Read). |
| Type<br> | Limits your search to objects of a specific type only. <br>
<br>                        <br>Specify an type from the Value list or type it yourself. <br>
<br>                        <br>For example, if the type is "computer" the filter shall display all the actions with the computer in the system. <br>
<br>                        <br>In case you set the name of the computer in  the What filter, you shall see the actions with the specific names of the computer. |
| What<br> | Specify an object name (e.g., *Policy*) to find all entries containing it (e.g., *HiSecPolicy*, *\\FileSserver\Share\NewFolder\NewPolicy.docx*, *http://sharepoint/sites/collection1/Lists/Policy*).<br>
<br>                        <br>{{ MyVariables.ProductName_Overlord }}searches across all audited systems. |
| Where<br> | Specify a resource name (e.g., *Enterprise*) to find all entries containing it (e.g., *Enterprise-SQL*, *FileStorage.enterprise.local*). The resource name can be an  Active Directory domain.<br>
<br>                        <br>{{ MyVariables.ProductName_Overlord }}searches across all audited systems. |
| Who<br> | Specify an account name (e.g., *John*) to find all entries containing it (e.g., *Domain1\John*, *Domain1\Johnson*, *Domain2\Johnny*). |
| When<br> | Specify a timeframe or provide a custom date range. {{ MyVariables.ProductName_Overlord }}allows you to see changes that occurred today, yesterday, in the last 7 or 30 days, or within the specified date range. |
| Connector<br> | Specify name of the file system for audit. <br>
<br>                        <br>The available options are:<br><ul>
<br>                            <li>
<br>                                <p>Active Directory
<br>Activity</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Active Directory Logons</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>AD Logon Activity
<br></p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Self Audit</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Azure AD Logons</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Azure AD Activity</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>File Server Activity</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Exchange Online Activity </p>
<br>                            </li>
<br>                            <li>
<br>                                <p>SharePoint Online Activity</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Active Directory State</p>
<br>                            </li>
<br>                        </ul> |
| Source Type<br> | Specify the source type:<br><ul>
<br>                            <li>
<br>                                <p>computer</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>contact</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>controlAccessRight</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>crossRef</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>crossRefContainer</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>domainDNS</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>foreignSecurityPrincipal</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>group</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>groupPolicyContainer</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>inetOrgPerson</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>msDS-ManagedServiceAccount</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>organizationalUnit</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>user</p>
<br>                            </li>
<br>                        </ul> |
| Source<br> | Specify the value of the item, namely the name of the computer, or the IP-address. |
| Succeeded<br> | Whether you specify False or True in the Value column, you will see successful (True) or non-succesful (False) actions in the system. |
| Tags<br> | Narrow your search to specific tags. For example, if you have the linked tags "Account Disabled", "User Account Status Change", the search system will look into the activities with these tags,<br>
<br>                        <br>The tags are linked to the {{ MyVariables.ProductName_Overlord }} by default. |
| Time of Day | Limits your search to specific time period by hours. For example, you can narrow your search to a period less than 12:00 AM. |