# Configure IT Infrastructure for Auditing and Monitoring

You can configure your IT Infrastructure for monitoring in one of the following ways:

- Automatically when creating an organization. This is a recommended method.
- Manually. The table below lists the native audit settings that must be adjusted manually to ensure collecting comprehensive and reliable audit data. You can enable {{ MyVariables.ProductName_Overlord }} to continually enforce the relevant audit policies or configure them manually.

| Data source | Provided connectors | Required configuration |
| --- | --- | --- |
| Active Directory | Active Directory Activity | In the audited environment:<br>
<br>                        <br>See [Configure Active Directory Domain for Monitoring](AD/ADManual.md)  for related settings and procedures.<br>
<br>                        <br>On the computer where Netwrix Cloud Agent is installed:<br><ul>
<br>                            <li>
<br>                                <p style="text-align: left;">If you have enabled automatic log backup for the Security log of your domain controller, you can instruct {{ MyVariables.ProductName_Overlord }} to clear the old backups automatically. For that, use the <b>CleanAutoBackupLogs</b> registry key</p>
<br>                                <p class="Note">It is recommended that you adjust retention period for the backup files accordingly (default is <b>50</b> hours). </p>
<br>                            </li>
<br>                            <li>To provide for event data collection, the <span class="semibold">Secondary Logon</span> service must be up and running . Open <b>Administrative Tools</b><span style="font-family: 'Times New Roman'">→</span><b>Services</b>, right-click the <b>Secondary Logon</b> service and on the <b>General</b> tab make sure that <b>Startup type</b> for this service is other than <i>Disabled</i>.</li>
<br>                        </ul> |
| Active Directory | Active Directory Logons<br> | In the audited environment:<br><ul>
<br>                            <li>
<br>                                <p>The following policies must be set to  <i>"Success"</i> and <i>"Failure"</i> for the effective domain controllers policy:</p><ul>
<br>                                    <li><span class="semibold">Audit Logon Events</span>
<br>                                    </li>
<br>                                    <li><span class="semibold">Audit Account Logon Events</span>
<br>                                    </li>
<br>                                </ul>
<br>                            </li>
<br>                            <li>The <span class="semibold">Audit system events</span> policy must be set to <i>"Success"</i> for the effective domain controllers policy.</li>
<br>                            <li>The Advanced audit policy settings can be configured instead of basic.</li>
<br>                            <li>
<br>                                <p>The <span class="semibold">Maximum Security event log</span> size  must be set to  4GB. The retention method of the <span class="semibold">Security event log</span> must be set to <i>“Overwrite events as needed”</i> or <i>"Archive the log when full"</i>.</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>The following Windows Firewall inbound rules must be enabled:</p><ul>
<br>                                    <li>Remote Event Log Management (NP-In)</li>
<br>                                    <li>Remote Event Log Management (RPC)</li>
<br>                                    <li>Remote Event Log Management (RPC-EPMAP)</li>
<br>                                </ul>
<br>                            </li>
<br>                        </ul> |
| Azure AD | Azure AD Activity
<br>                        <br>Azure AD Logons<br> | No special settings are required. Remember to do the following:<br>
<br>                        <br>Configure Azure AD app  as described in [App Registration and Configuration in Microsoft Entra ID](EntraID/RegisterConfig.md)  section. |
| Computer | File Server Activity | **In the audited environment**<br>                        <br><ul>
<br>                            <li>
<br>                                <p style="text-align: justify;">For a security principal (e.g., <span class="semibold">Everyone</span>), the following options must be configured in the <span class="semibold">Advanced Security <span style="font-family: 'Open Sans'">→</span> Auditing</span> settings for the audited shared folders:</p>
<br>                                <table style="width: 100%;margin-left: auto;margin-right: auto;mc-table-style: url('../../Resources/TableStyles/Sb Table 1.css');" class="TableStyle-Sb_Table_1" cellspacing="21">
<br>                                    <col style="width: 259px;" class="TableStyle-Sb_Table_1-Column-Column1">
<br>                                    <col class="TableStyle-Sb_Table_1-Column-Column1">
<br>                                    <tbody>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body1" style="font-family: Calibri;">	List Folder / Read Data (Files only)</td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2" style="font-family: Calibri;">List Folder / Read Data (This folder, subfolders and files)</td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Fail"</i>
<br>                                            </td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body1" style="font-family: Calibri;">Create Files / Write Data*</td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2" style="font-family: Calibri;">Create Folders / Append Data*</td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body1" style="font-family: Calibri;">
<br>                                                <p>Write Extended Attributes*</p>
<br>                                            </td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2" style="font-family: Calibri;">
<br>                                                <p>Delete Subfolders and Files*</p>
<br>                                            </td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body1" style="font-family: Calibri;">
<br>                                                <p>	Delete*</p>
<br>                                            </td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2" style="font-family: Calibri;">
<br>                                                <p>Change Permissions*</p>
<br>                                            </td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                        <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                            <td class="TableStyle-Sb_Table_1-BodyB-Column1-Body1" style="font-family: Calibri;">
<br>                                                <p>Take Ownership*</p>
<br>                                            </td>
<br>                                            <td class="TableStyle-Sb_Table_1-BodyA-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Fail"</i></td>
<br>                                        </tr>
<br>                                    </tbody>
<br>                                </table>
<br>                                <p class="Note">Select <i>"Fail</i>" only if you want to track failure events, it is not required for success events monitoring. </p>
<br>                                <p class="Note_continue">If you want to get only state-in-time snapshots of your system configuration, limit your settings to the permissions marked with * and set it to <i>"Success"</i> (Apply onto: This folder, subfolders and files).</p>
<br>                            </li>
<br>                            <li style="text-align: left;">
<br>                                <p>The following <span class="semibold">Advanced audit policy</span> settings must be configured:</p><ul>
<br>                                    <li>
<br>                                        <p>The <span class="semibold">Audit: Force audit policy subcategory settings (Windows 7 or later)</span> security option must be enabled.</p>
<br>                                    </li>
<br>                                    <li>
<br>                                        <p>Depending on your OS version, configure the categories as follows:</p>
<br>                                        <table style="margin-left: 0;margin-right: auto;width: 450px;mc-table-style: url('../../Resources/TableStyles/Sb Table 1.css');" class="TableStyle-Sb_Table_1" cellspacing="21">
<br>                                            <col style="width: 250px;" class="TableStyle-Sb_Table_1-Column-Column1">
<br>                                            <col style="width: 200px;" class="TableStyle-Sb_Table_1-Column-Column1">
<br>                                            <tbody>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td colspan="2" style="text-align: center;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1"><span class="semibold">Windows Server 2008</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr style="height: 25px;" class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: center;font-family: Calibri;" colspan="2" class="TableStyle-Sb_Table_1-BodyD-Column1-Body2"><span class="semibold">Object Access</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body1"><span style="font-family: 'Open Sans';">Audit File Share</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body2"><span style="font-family: 'Open Sans';">Audit File System</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i> and <i>"Failure"</i></td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body1"><span style="font-family: 'Open Sans';">Audit Handle Manipulation</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Failure"</i></td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: center;font-family: Calibri;" colspan="2" class="TableStyle-Sb_Table_1-BodyD-Column1-Body2"><span class="semibold">Logon/Logoff</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body1" style="font-family: Calibri;">Logon</td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2" style="font-family: Calibri;">Logoff</td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td colspan="2" style="text-align: center;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1"><span class="semibold">Policy Change</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2" style="font-family: Calibri;">Audit Audit Policy Change</td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td colspan="2" style="text-align: center;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1"><span class="semibold">System</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body2"><span style="font-family: 'Open Sans';">Security State Change</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td colspan="2" style="text-align: center;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1"><span class="semibold">Windows Server 2008 R2 / Windows 7 and above</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: center;font-family: Calibri;" colspan="2" class="TableStyle-Sb_Table_1-BodyD-Column1-Body2"><span class="semibold">Object Access</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body1"><span style="font-family: 'Open Sans';">Audit File Share</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body2"><span style="font-family: 'Open Sans';">Audit File System</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i> and <i>"Failure"</i></td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body1"><span style="font-family: 'Open Sans';">Audit Handle Manipulation</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i> and <i>"Failure"</i></td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body2"><span class="semibold">Audit Detailed file share</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Failure"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="text-align: center;font-family: Calibri;" colspan="2" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1"><span class="semibold">Logon/Logoff</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body2">Logon</td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body1">Logoff</td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: center;font-family: Calibri;" colspan="2" class="TableStyle-Sb_Table_1-BodyD-Column1-Body2"><span class="semibold">Policy Change</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyE-Column1-Body1">Audit Audit Policy Change</td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td style="text-align: center;font-family: Calibri;" colspan="2" class="TableStyle-Sb_Table_1-BodyD-Column1-Body2"><span class="semibold">System</span>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td style="text-align: left;font-family: Calibri;" class="TableStyle-Sb_Table_1-BodyB-Column1-Body1"><span style="font-family: 'Open Sans';">Security State Change</span>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyA-Column1-Body1" style="font-family: Calibri;"><i>"Success"</i>
<br>                                                    </td>
<br>                                                </tr>
<br>                                            </tbody>
<br>                                        </table>
<br>                                        <p>If you want to get only state-in-time snapshots of your system configuration, limit your audit settings to the following  policies:</p>
<br>                                        <table style="margin-left: 0;margin-right: auto;mc-table-style: url('../../Resources/TableStyles/Sb Table 1.css');" class="TableStyle-Sb_Table_1" cellspacing="21">
<br>                                            <col style="width: 250px;" class="TableStyle-Sb_Table_1-Column-Column1">
<br>                                            <col style="width: 200px;" class="TableStyle-Sb_Table_1-Column-Column1">
<br>                                            <tbody>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td colspan="2" style="text-align: center;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1">
<br>                                                        <p colspan="2" style="text-align: center;"><span class="semibold">Object Access</span>
<br>                                                        </p>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2">
<br>                                                        <p>Audit File System</p>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyD-Column1-Body2">
<br>                                                        <p><i>"Success"</i>
<br>                                                        </p>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body1">
<br>                                                        <p>Audit Handle Manipulation</p>
<br>                                                    </td>
<br>                                                    <td style="font-style: italic;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1">"Success"</td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyE-Column1-Body2">
<br>                                                        <p>Audit File Share</p>
<br>                                                    </td>
<br>                                                    <td style="font-style: italic;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body2">"Success"</td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body1">
<br>                                                    <td colspan="2" style="text-align: center;" class="TableStyle-Sb_Table_1-BodyD-Column1-Body1">
<br>                                                        <p colspan="2" style="text-align: center;"><span class="semibold">Policy Change</span>
<br>                                                        </p>
<br>                                                    </td>
<br>                                                </tr>
<br>                                                <tr class="TableStyle-Sb_Table_1-Body-Body2">
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyB-Column1-Body2">
<br>                                                        <p>Audit Audit Policy Change</p>
<br>                                                    </td>
<br>                                                    <td class="TableStyle-Sb_Table_1-BodyA-Column1-Body2">
<br>                                                        <p style="font-style: italic;">"Success"</p>
<br>                                                    </td>
<br>                                                </tr>
<br>                                            </tbody>
<br>                                        </table>
<br>                                    </li>
<br>                                </ul>
<br>                            </li>
<br>                            <li>
<br>                                <p>The following legacy policies can be configured instead of advanced:</p><ul>
<br>                                    <li style="text-align: left;"><span class="semibold">Audit object access</span> policy  must set to <i>"Success"</i> and <i>"Failure"</i>.</li>
<br>                                    <li>
<br>                                        <p><span class="semibold">Audit logon events</span> policy must be set to <i>"Success"</i>.</p>
<br>                                    </li>
<br>                                    <li>
<br>                                        <p><span class="semibold">Audit system events</span> policy must be set to <i>"Success"</i>.</p>
<br>                                    </li>
<br>                                    <li style="text-align: left;"><span class="semibold">Audit policy change</span> must be set to <i>"Success"</i>.</li>
<br>                                </ul>
<br>                            </li>
<br>                            <li>
<br>                                <p>The <span class="semibold"> Security event log maximum size</span>  must be set to 4GB. The retention method of the <span class="semibold">Security event log</span> must be set to <i>“Overwrite events as needed”</i>.</p>
<br>                            </li>
<br>                            <li style="text-align: left;">The <span class="semibold">Remote Registry</span> service must be started.</li>
<br>                            <li style="text-align: left;">The following inbound Firewall rules must be enabled:<ul><li>Remote Event Log Management (NP-In)*</li><li>Remote Event Log Management (RPC)*</li><li>Remote Event Log Management (RPC-EPMAP)*</li><li>Windows Management Instrumentation (ASync-In)</li><li>Windows Management Instrumentation (DCOM-In)</li><li>Windows Management Instrumentation (WMI-In)</li><li><p>Network Discovery (NB-Name-In)</p></li><li>File and Printer Sharing (NB-Name-In)</li><li><p>File and Printer Sharing (Echo Request - ICMPv4-In)</p></li><li><p>File and Printer Sharing (Echo Request - ICMPv6-In)</p><p class="Note">The rules marked with * are required only if you do not want to use network traffic compression for auditing.</p><p class="Note">If you plan to audit Windows Server 2019 or Windows 10 Update 1803 without network compression service, make sure the following inbound connection rules are enabled:</p><ul><li class="Note">Remote Scheduled Tasks Management (RPC)</li><li class="Note">Remote Scheduled Tasks Management (RPC-EMAP)</li></ul></li></ul></li>
<br>                        </ul> |
| SharePoint Online | SharePoint Online Activity | No special settings are required. Remember to do the following:<br>
<br>                        <br>Configure Azure AD app  as described in [App Registration and Configuration in Microsoft Entra ID](EntraID/RegisterConfig.md) . |