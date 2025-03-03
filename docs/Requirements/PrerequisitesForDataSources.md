# Prerequisites for Data Sources

This section lists platforms and systems that can be monitored with {{ MyVariables.ProductName_Overlord }}.

- Active Directory

- {{ MyVariables.Azure_AD app }} (formerly Azure AD)

- Computer (Windows File Share)
- SharePoint Online
- Exchange Online

| Data source | Supported Versions |
| --- | --- |
| Active Directory <br>
<br>                        <br>(including  Logon Activity) | Domain Controller OS versions:<br><ul>
<br>                            <li>Windows Server 2022</li>
<br>                            <li>Windows Server 2019</li>
<br>                            <li>Windows Server 2016</li>
<br>                            <li>Windows Server 2012 R2</li>
<br>                        </ul> |
| {{ MyVariables.Azure_AD app }}<br> | {{ MyVariables.Azure_AD app }} version provided within Microsoft Office 365<br>
<br>                        <br>You may need to take some preparatory steps, depending on the authentication method you want to use for collecting Azure AD and Office 365 data. See the [App Registration and Configuration in Microsoft Entra ID](../Configuration/EntraID/RegisterConfig.md)  topic for additional information. |
| Computer (Windows File Server) | <ul>
<br>                            <li>Windows Server OS:<ul><li>Windows Server 2022</li><li>Windows Server 2019</li><li>Windows Server 2016</li><li>Windows Server 2012 R2</li></ul></li>
<br>                            <li>Windows Desktop OS  (32 and 64-bit):<ul><li>Windows 10</li><li>Windows 8.1</li><li>Windows 7</li></ul></li>
<br>                        </ul>
<br>                        <br>Consider the following:<br><ul>
<br>                            <li>To collect data from 32-bit operating systems, network traffic compression must be disabled. </li>
<br>                            <li>To collect data from Windows Failover Cluster, network traffic compression must be enabled. </li>
<br>                            <li>Scale-Out File Server (SOFS) cluster is not supported.</li>
<br>                        </ul> |
| SharePoint Online | Azure Active Directory version provided within Microsoft Office 365<br>
<br>                        <br>You may need to take some preparatory steps, depending on the authentication method you want to use for collecting SharePoint Online and One Drive for Business. See the [App Registration and Configuration in Microsoft Entra ID](../Configuration/EntraID/RegisterConfig.md)  topic for additional information. |
| Exchange Online | Azure Active Directory version provided within Microsoft Office 365<br>
<br>                        <br>You may need to take some preparatory steps, depending on the authentication method you want to use for collecting Exchange Online. See the [App Registration and Configuration in Microsoft Entra ID](../Configuration/EntraID/RegisterConfig.md)  topic for additional information. |