# Adjust Security Event Log Size and Retention Settings

Defining the Security event log size is essential for change auditing. If the log size is insufficient, overwrites may occur before data is written to the Long-Term Archive and the Audit Database, and some audit data may be lost. 

To prevent overwrites, you can increase the maximum size of the Security event log and set retention method for this log to “*Overwrite events as needed*”. 

To adjust your Security event log size and retention method, follow the procedure described below.

To read about event log settings recommended by Microsoft, refer to this [article](https://support.microsoft.com/en-us/help/957662/recommended-settings-for-event-log-sizes-in-windows).

Follow the steps to increase the maximum size of the Security event log and set its retention method.

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to Start &gt; Windows Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) &gt;  **Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt;** &gt; **Domains** &gt; **&lt;domain\_name&gt;** &gt; **Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

Navigate to **Computer Configuration** &gt;  **Policies** &gt;  **Windows Settings &gt; Security Settings** &gt; **Event Log** and double-click the **Maximum security log size** policy.![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_GroupPolicyMaxSecuritySizeWinServer2016.png)

In the **Maximum security log size Properties** dialog, select **Define this policy setting** and set maximum security log size to*"4194240"* kilobytes (4GB).

Select the **Retention method for security log** policy. In the **Retention method for security log Properties** dialog, check  **Define this policy** and select **Overwrite events as needed**.

Navigate to **Start &gt; Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated. 

If "Overwrite" option is not enough to meet your data retention requirements, you can use *auto-archiving*
		option for Security event log to preserve historical event data in the archive files. With that option enabled, you may want to adjust the retention settings for log archives
		(backups). Related procedures are described in [this Knowledge Base article](https://kb.netwrix.com/5856).