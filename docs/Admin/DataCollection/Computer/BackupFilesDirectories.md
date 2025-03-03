# Configure the Back up Files and Directories Policy

Configure this Back up Files and Directories policy via the **Local Security Policy Snap-in** or using the **Group Policy Management Console**.

Follow the steps to configure the Back up Files and Directories' policy via the **Local Security Policy Snap-in**.

On any domain controller in the target domain, open  the **Local Security Policy** snap-in:  navigate to Start &gt; Administrative Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) &gt; Local Security Policy.

Navigate to Security Settings &gt; Local Policies &gt; User Right Assignment.

Locate the **Back up files and directories** policy and double-click it.

In the **Back up files and directories Properties** dialog, click **Add User or Group**, specify the user that you want to define this policy for.

The policy is now configured.

Follow the steps to configure the Back up Files and Directories' policy using the **Group Policy Management Console**.

Perform this procedure only if the account selected for data collection is not a member of the Domain Admins group.

Open the Group Policy Management console on any domain controller in the target domain: navigate to Start &gt; Windows Administrative Tools (Windows Server 2016/2019) or Administrative Tools (Windows 2012 R2 and below) &gt; Group Policy Management.

In the left pane, navigate to Forest: &lt;forest name&gt; &gt; Domains &gt; &lt;domain name&gt; &gt; Domain Controllers. Right-click the effective domain controllers policy (by default, it is the *Default Domain Controllers Policy*), and select Edit .

In the Group Policy Management Editor dialog, expand the Computer Configuration node on the left and navigate to Policies &gt; Windows Settings &gt; Security Settings &gt; Local Policies.

On the right, double-click the User Rights Assignment policy.

Locate the Back up files and directories policy and double-click it.

In the Back up files and directories Properties dialog, click Add User or Group and specify the user that you want to define this policy for.

Navigate to Start &gt; Run and type "*cmd*". Input the `gpupdate /force` command and press Enter. The group policy will be updated.

Type `repadmin /syncall` command and press Enter for replicate GPO changes to other domain controllers.

Ensure that new GPO settings applied on any audited domain controller.

The policy is now configured.