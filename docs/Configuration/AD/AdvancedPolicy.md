# Configure Advanced Audit Policies

You can configure advanced audit policies instead of basic domain policies to collect Active Directory changes with more granularity. Either basic or advanced audit policies must be configured to track changes to accounts and groups, and to identify workstations where changes were made. 

## To configure security options

Using both basic and advanced audit policies settings may lead to incorrect audit reporting. To force basic audit policies to be ignored and prevent conflicts, enable the Audit: Force audit policy subcategory settings  to override audit policy category settings option. 

Follow the steps:

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to Start &gt; Windows Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) &gt;  **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt; → Domains → &lt;domain\_name&gt; → Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the Group Policy Management Editor dialog, expand the Computer Configuration node on the left and navigate to Policies  &gt; Windows Settings  &gt; Security Settings → Local Policies → Security Options. 

Locate the Audit: Force audit policy subcategory settings to override audit policy category settings and make sure that policy setting is set to *"Enabled"*.![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_AD_NLA_Audit_Force_WinServer2016.png)

Navigate to **Start → Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated. 

## To configure advanced audit policies

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to Start &gt; Windows Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) &gt;  **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt;** &gt; **Domains** &gt; **&lt;domain\_name&gt;** &gt; **Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the Group Policy Management Editor dialog, expand the Computer Configuration node on the left and navigate to Policies  &gt; Windows Settings  &gt; Security Settings &gt; Advanced Audit Policy Configuration &gt; Audit Policies.

Configure the following audit policies.

| Policy Subnode | Policy Name | Audit Events |
| --- | --- | --- |
| Account Management<br> | <ul>
<br>                            <li>
<br>                                <p><span class="semibold">Audit Computer Account Management</span>
<br>                                </p>
<br>                            </li>
<br>                            <li>
<br>                                <p><span class="semibold">Audit Distribution Group Management</span>
<br>                                </p>
<br>                            </li>
<br>                            <li>
<br>                                <p><span class="semibold">Audit Security Group Management</span>
<br>                                </p>
<br>                            </li>
<br>                            <li>
<br>                                <p><span class="semibold">Audit User Account Management</span>
<br>                                </p>
<br>                            </li>
<br>                        </ul> | *"Success"*<br> |
| DS Access<br> | Audit Directory Service Access<br> | *"Success"*<br> |
| Logon/Logoff<br> | <ul>
<br>                            <li><span class="semibold">Audit Logoff</span>
<br>                            </li>
<br>                            <li><span class="semibold">Audit Logon</span>
<br>                            </li>
<br>                        </ul>
<br>                        <br>These policies are only required to collect the information on the originating workstation, i.e., the computer from which a change was made. | *"Success"*<br> |![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_AD_AdvPol_WinServer2016.png)

Navigate to **Start &gt; Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated.