# Configure Security Event Log Size and Retention Settings

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to Start&gt;Windows Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012)**&gt; Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt;** &gt; **Domains** &gt; **&lt;domain\_name&gt; → Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

Navigate to **Computer Configuration** &gt; **Policies** &gt; **Windows Settings &gt; Security Settings** &gt;  **Event Log** and double-click the **Maximum security log size** policy.![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_GroupPolicyMaxSecuritySizeWinServer2016.png)

In the **Maximum security log size Properties** dialog, select **Define this policy setting** and set maximum security log size to*"4194240"* kilobytes (4GB).

Select the **Retention method for security log** policy. In the **Retention method for security log Properties** dialog, check  **Define this policy** and select **Overwrite events as needed**.

Navigate to **Start** &gt; **Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated.