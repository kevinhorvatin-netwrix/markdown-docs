# Configure Basic Domain Audit Policies

Basic audit policies allow tracking changes to user accounts and groups and identifying originating workstations. You can configure advanced audit policies for the same purpose too. See the [Configure Advanced Audit Policies](AdvancedPolicy.md)  topic for additional information.

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to Start &gt; Windows Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012)&gt;  **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt;** &gt; **Domains** &gt;  **&lt;domain\_name&gt; &gt; Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the **Group Policy Management Editor** dialog, expand the **Computer Configuration** node on the left and navigate to **Policies &gt; Windows Settings &gt; Security Settings &gt; Local Policies &gt; Audit Policy.** 

Configure the following audit policies.

| Policy | Audit Events |
| --- | --- |
| **Audit account management**<br> | *"Success"*<br> |
| **Audit directory service access**<br> | *"Success"*<br> |
| **Audit logon events**<br> | *"Success"*<br> |![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_AD_LocalPolicy_WinServer2016.png)

The Audit logon events policy is only required to collect the information on the originating workstation, i.e., the computer from which a change was made. This functionality is optional and can be disabled. 

Navigate to **Start &gt; Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated.