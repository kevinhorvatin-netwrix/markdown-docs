#  Microsoft 365 Required Permissions

This page lists the permissions required for an application you registered in {{ MyVariables.Azure_AD app }} to audit the following Microsoft 365 data sources: 

- Microsoft Entra ID
- SharePoint Online
- Exchange Online

## Permissions to Audit Microsoft Entra ID

The registered application must be assigned to the Global Administrator or Exchange Administrator role for {{ MyVariables.Azure_AD app }} state collection.

| API | Permissions |
| --- | --- |
| Microsoft Graph | Directory<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:DirectoryReadAll@
<br>                                </p>
<br>                            </li>
<br>                        </ul>
<br>                        <br>AuditLog<br><ul>
<br>                            <li>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:AuditLogReadAll@
<br>                            </li>
<br>                        </ul>
<br>                        <br>Policy<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:PolicyReadAll@. @Snippet:1Secure/EntraIDApp:StatePerm@</p>
<br>                            </li>
<br>                        </ul> |
| Office 365 Management APIs | ActivityFeed<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/Office365Management:ActivityFeedRead@
<br>                                </p>
<br>                            </li>
<br>                        </ul> |
| Office 365 Exchange Online | Exchange<br><ul>
<br>                            <li>
<br> @Snippet:Config/EntraID/GrantPermissions/Office365ExchangeOnline:ExchangeManageAsApp@
<br> @Snippet:1Secure/EntraIDApp:StatePerm@
<br>                            </li>
<br>                        </ul> |

To access the Office 365 Exchange Online API, click the **APIs my organization uses** tab on the Request API Permissions pane and search this API by entering its name in the search box.

## Permissions to Audit SharePoint Online

| API | Permissions |
| --- | --- |
| Microsoft Graph | Sites<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:SitesReadAll@
<br>                                </p>
<br>                            </li>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:SitesReadWriteAll@
<br>                                </p>
<br>                            </li>
<br>                        </ul>
<br>                        <br>Directory<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:DirectoryReadAll@
<br>                                </p>
<br>                            </li>
<br>                        </ul> |
| SharePoint | Sites<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/SharePoint:SitesFullControlAll@. @Snippet:1Secure/EntraIDApp:StatePerm@</p>
<br>                            </li>
<br>                        </ul> |
| Office 365 Management APIs | ActivityFeed<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/Office365Management:ActivityFeedRead@
<br>                                </p>
<br>                            </li>
<br>                        </ul> |

## Permissions to Audit Exchange Online

| API | Permissions |
| --- | --- |
| Microsoft Graph | Policy<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/GraphAPIApplication:PolicyReadAll@. @Snippet:1Secure/EntraIDApp:StatePerm@</p>
<br>                            </li>
<br>                        </ul> |
| Office 365 Management APIs | ActivityFeed<br><ul>
<br>                            <li>
<br>                                <p>
<br> @Snippet:Config/EntraID/GrantPermissions/Office365Management:ActivityFeedRead@
<br>                                </p>
<br>                            </li>
<br>                        </ul> |