# 
            <madcap:keyword term="Configure audit:Logon Activity;Logon Activity:Audit settings:Advanced audit policies"></madcap:keyword>Configure Advanced Audit Policies

You can configure advanced audit policies instead of basic domain policies to collect Logon Activity changes with more granularity.

Follow the steps to configure security options.  

Using both basic and advanced audit policies settings may lead to incorrect audit reporting. To force basic audit policies to be ignored and prevent conflicts, enable the Audit: Force audit policy subcategory settings  to override audit policy category settings option. 

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to @Snippet:Auditor:Administrative_Tools@ **** &gt; **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt; &gt; Domains &gt; &lt;domain\_name&gt; &gt; Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the Group Policy Management Editor dialog, expand the Computer Configuration node on the left and navigate to Policies  &gt; Windows Settings  &gt; Security Settings &gt; Local Policies &gt; Security Options. 

Locate the Audit: Force audit policy subcategory settings to override audit policy category settings and make sure that policy setting is set to *"Enabled"*.![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_AD_NLA_Audit_Force_WinServer2016.png)

Navigate to **Start** &gt; **Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated. 

Follow the steps to configure advanced audit policies.

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to @Snippet:Auditor:Administrative_Tools@&gt; **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt;** &gt; **Domains** &gt; **&lt;domain\_name&gt;** &gt; **Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the Group Policy Management Editor dialog, expand the Computer Configuration node on the left and navigate to Policies  &gt; Windows Settings  &gt; Security Settings &gt; Advanced Audit Policy Configuration &gt; Audit Policies <madcap:conditionaltext madcap:conditions="Auditor/2_Output.Hidden">&gt; <span class="semibold">Account Logon.</span></madcap:conditionaltext>.

Configure the following audit policies.

| Policy Subnode | Policy Name | Audit Events |
| --- | --- | --- |
| Account Logon<br> | <ul>
<br>                            <li><span class="semibold">Audit Kerberos Service Ticket Operations</span>
<br>                            </li>
<br>                            <li><span class="semibold">Audit Kerberos Authentication Service</span>
<br>                            </li>
<br>                            <li><span class="semibold">Audit Credential Validation</span>
<br>                            </li>
<br>                        </ul> | *"Success"* and *"Failure"* |
| <ul>
<br>                            <li><span class="semibold">Audit Other Account Logon Events</span>
<br>                            </li>
<br>                        </ul>
<br>                        <br>Required if at least one domain controller in the monitored domain runs Windows Server 2012 R2<madcap:conditionaltext madcap:conditions="Auditor/2_Output.Hidden"> with KB4012216 installed</madcap:conditionaltext>. | *"Success"* and *"Failure"* |
| Logon/Logoff<br> | <ul>
<br>                            <li><span class="semibold">Audit Logoff</span>
<br>                            </li>
<br>                            <li><span class="semibold">Audit Other Logon/Logoff Events</span>
<br>                            </li>
<br>                        </ul> | *"Success"*<br> |
| <ul>
<br>                            <li><span class="semibold">Audit Logon</span>
<br>                            </li>
<br>                        </ul> | *"Success"* and *"Failure"* |
| System<br> | <ul>
<br>                            <li><span class="semibold">Audit Security State Change</span>
<br>                            </li>
<br>                        </ul> | *"Success"*<br> |![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_NLA_AdvPol2016.png)

Set the	following advanced audit policies to  *"Success"* and *"Failure"*:

- Audit Kerberos Service Ticket Operations
- Audit Kerberos Authentication Service
- Audit Credential Validation

Set the Audit Security State Change advanced audit policy to "*Success*".

Navigate to **Start** &gt; **Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated.