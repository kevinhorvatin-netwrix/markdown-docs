# 
            <madcap:keyword term="Data collecting account;Service accounts:Data collecting account;EMC Isilon:Rights and permissions"></madcap:keyword> Data Collecting Account

The data collecting account  is a service account that {{ MyVariables.ProductName_Overlord }} uses to collect audit data from the monitored items (domains, OUs, servers, etc.). {{ Netwrix.Company }} recommends creating a dedicated service account for that purpose. Depending on the data source and connector, the account must meet the corresponding  requirements (see the table below).

You can use  group Managed Service Account (gMSA) as data collecting account. See the [Using Group Managed Service Account (gMSA)](../GMSA/GMSA.md)  topic for additional information.

 Currently, the following data sources are supported: 

| Data source | Provided connectors | Required rights and permissions: |
| --- | --- | --- |
| Active Directory | Active Directory Activity<br>
<br>                        <br>Active Directory Logons | <br> [Active Directory Auditing](../ActiveDirectory/ActiveDirectoryAuditing.md) <br>                        <br>
<br>                        <br><br>                            <madcap:xref href="../LogonActivity/Overview.htm" target="_parent" title="Logon Activity Auditing" alt="Logon Activity Auditing">Logon Activity Auditing
<br>        </madcap:xref><![CDATA[
<br>]]> |
| Azure AD | Azure AD Activity<br>
<br>                        <br>Azure AD Logons | <br> [Microsoft Entra ID Auditing](../EntraID.md) <br> |
| Computer | File Server Activity | <br> [Computer Auditing](../Computer/README.md) <br> |
| SharePoint Online | SharePoint Online Activity | <br> [SharePoint Online Auditing](../SharePointOnline.md) <br> |
| Exchange Online | Exchange Online Activity | <br> [Exchange Online Auditing](../ExchangeOnline.md) <br> |