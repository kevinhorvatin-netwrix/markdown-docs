# 
            <madcap:keyword term="Data collecting account:Registry key">
            </madcap:keyword>Assigning Permission To Read the Registry Key

This permission is required only if the account selected for data collection is not a member of  the Domain Admins group. 

This permission should be assigned on each domain controller in the audited domain, so if your domain contains multiple domain controllers, it is recommended to  assign permissions through Group Policy.

To assign permissions manually, use the Registry Editor snap-in or the Group Policy Management console. 

## To assign permission via the Registry Editor snap-in

On your target server, open Registry Editor: navigate to Start → Run and type "regedit".

In the left pane, navigate to *HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControl Set\Services\EventLog\Security*. 

Right-click the **Security** node and select **Permissions** from the pop-up menu.

Click **Add** and enter the name of the user that you want to grant permissions to.

Check **Allow** next to the **Read** permission.

For auditing Logon Activity, you also need to assign the Read permission to the *HKEY\_LOCAL\_MACHINE\SECURITY\Policy\PolAdtEv* registry key.

## To assign permission using the Group Policy Management console

Open the Group Policy Management console on any domain controller in the target domain: navigate to Start → Windows Administrative Tools (Windows Server 2016/2019) or Administrative Tools (Windows 2012 R2 and below) → Group Policy Management.

In the left pane, navigate to Forest: &lt;forest name&gt; → Domains → &lt;domain name&gt; → Domain Controllers. Right-click the effective domain controllers policy (by default, it is the *Default Domain Controllers Policy*), and select Edit .

In the Group Policy Management Editor dialog, expand the Computer Configuration node on the left and navigate to Policies → Windows Settings → Security Settings → Registry.

Right-click in the pane and select Add Key.

Navigate to `HKEY_LOCAL_MACHINE\SECURITY\Policy\PolAdtEv` and click OK.

Click Add and enter the name of the user that you want to grant permissions to and press Enter.

Check Allow next to the *"Read"* permission and click OK.

In the pop-up window, select Propagate inheritable permissions to all subkeys and click OK.

Repeat the steps 4-8 for keys below:

- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurePipeServers\winreg`;
- `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\EventLog\Security`.

Close Group Policy Management console.

Navigate to Start → Run and type "*cmd*". Input the `gpupdate /force` command and press Enter. The group policy will be updated.

Type `repadmin /syncall` command and press Enter for replicate GPO changes to other domain controllers.

Ensure that new GPO settings were applied to the  domain controllers.