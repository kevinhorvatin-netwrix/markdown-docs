# Configure Basic Domain Audit Policies

Basic local audit policies allow tracking changes to user accounts and groups and identifying originating workstations. You can configure advanced audit policies for the same purpose too. See [Configure Advanced Audit Policies](AdvancedAudit.md)) 

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to Start &gt; Windows Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) &gt;  **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt;** &gt; **Domains &gt; &lt;domain\_name&gt; &gt; Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the **Group Policy Management Editor** dialog, expand the **Computer Configuration** node on the left and navigate to **Policies** &gt; **Windows Settings** &gt; **Security Settings** &gt; **Local Policies &gt; Audit Policy.** 

Configure the following audit policies.

| Policy | Audit Events |
| --- | --- |
| Audit logon events<br> | *"Success"* and *"Failure"* |
| Audit account logon events<br> | *"Success"* and *"Failure"* |
| Audit system events<br> | *"Success"*<br> |![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_NLA_AuditPolicies2016.png)

Set the Audit Logon Events and the Audit Account Logon Events policy to **Success** and **Failure**.

Set the Audit system events policy to **Success**. 

Navigate to **Start** &gt; **Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated.