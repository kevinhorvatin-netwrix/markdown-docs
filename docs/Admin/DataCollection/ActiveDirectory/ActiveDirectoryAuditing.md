# Active Directory Auditing

To collect data from Active Directory, you need an account with specific permissions. The following options are available:

## Use Domain Admin Account

You can use an account from the Domain Admins group. This account inherently has all necessary permissions for data collection.

## Use Non-Domain Admin Account

If using a Non-Domain Admin account, set up the account with specific permissions depending on the following aspects:

| In the target domain | Account Permission Required |
| --- | --- |
| Do you plan to use [Network Traffic Compression](../../../Configuration/NetworkTrafficCompression.md)  for data processing?<br> | If **YES**, account must belong to Domain Admin group. <br>
<br>                        <br>If **NO**, add an account to 'Manage auditing and security log' policy. See [Configuring 'Manage Auditing and Security Log' Policy](ManageAuditingSecurityLog.md)  for more information. |
| Do you plan to use AD Deleted Objects container for data processing? | If **YES**, account requires Read permission on the read container. See [Granting Permissions for 'Deleted Objects' Container](PermissionsADContainer.md)  topic for more information. |
| Is  auto-backup *enabled* for the domain controller event logs? <br> | If **YES**, account needs the following:<br>                        <br>
<br>                        <ul>
<br>                            <li>
<br>                                <p>Access to specific registry key on the domain controllers. See [Assigning Permission To Read the Registry Key](PermissionsRegistryKeys.md) <span style="font-family: Calibri;"> for additional information.</span></p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Membership in either Administrators, Print Operators, or Server Operators group. </p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Read/Write and Full Control permissions on the logs back up folder. </p>
<br>                            </li>
<br>                        </ul> |
| Is there an on-premises Exchange server in your Active Directory domain? | If **YES**, account needs the following:<br>                        <br>
<br>                        <ul>
<br>                            <li>
<br>                                <p>Membership in the <b>Organization Management</b> or <b>Records Management</b> group or having Audit Logs management role. See [Assigning Management Roles](AuditLogsRole.md)  topic for additional information.</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Adjustment of the Exchange Administrator Audit Logging settings. See [Configure Exchange Administrator Audit Logging Settings](AuditLogging.md)   topic for additional information.</p>
<br>                            </li>
<br>                        </ul> |

## Use GMSA

You can use group Managed Service Accounts (gMSA) as data collecting accounts. It should also meet the same requirements. 

If you are using gMSA for data collection, consider that AAL event data collection from your on-premise Exchange server will not be possible. Thus, changes made to your Active Directory domain via that Exchange server will be reported with *domain\Exchange\_server\_name$* instead of the initiator (user) name in the "*Who*" field of reports, search results and activity summaries.

For more information on gMSA, refer to [Using Group Managed Service Account (gMSA)](../GMSA/GMSA.md)  and to [Microsoft documentation](https://docs.microsoft.com/en-us/windows-server/security/group-managed-service-accounts/group-managed-service-accounts-overview "Microsoft documentation").