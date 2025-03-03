# Configure the Manage Auditing and Security Log Policy

Perform this procedure only if the account selected for data collection is not a member of the Domain Admins group.

Open the **Group Policy Management** console on any domain controller in the target domain: navigate to @Snippet:Auditor:Administrative_Tools@ 
**→ Group Policy Management.**

In the left pane, navigate to **Forest: &lt;forest\_name&gt; → Domains → &lt;domain\_name&gt; → Domain Controllers**. Right-click the effective domain controllers policy (by default, it is the **Default Domain Controllers Policy**), and select **Edit** from the pop-up menu.

In the **Group Policy Management Editor** dialog, expand the **Computer Configuration** node on the left and navigate to **Policies → Windows Settings → Security Settings → Local Policies.**

On the right, double-click the **User Rights Assignment** policy.

Locate the **Manage auditing and security log** policy and double-click it.

In the **Manage auditing and security log Properties** dialog, click **Add User or Group**, specify the user that you want to define this policy for.

Navigate to **Start → Run** and type *"cmd"*. Input the `gpupdate /force` command and press **Enter**. The group policy will be updated. 

Type `repadmin /syncall` command and press Enter for replicate GPO changes to other domain controllers.

Ensure that new GPO settings applied on any audited domain controller.