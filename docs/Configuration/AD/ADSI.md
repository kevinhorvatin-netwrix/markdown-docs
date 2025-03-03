# Install ADSI Edit

The ADSI Edit utility is used to view and manage objects and attributes in an Active Directory forest.  ADSI Edit is required to manually configure audit settings in the target domain. It must be installed on any domain controller in the domain you want to start auditing.

To install ADSI Edit on Windows Server 2003 and Windows XP

1. [Download](http://www.microsoft.com/en-us/download/details.aspx?id=15326 "Download") and install Windows Server Support Tools that include ADSI Edit.

To install ADSI Edit on Windows Server 2008 and Windows Server 2008 R2

1. Navigate to **Start** &gt; **Control Panel** &gt; **Programs** &gt; **Programs and Features** &gt; **Turn Windows features on or off**.
2. In the **Server Manager** dialog, select **Features** in the left pane, and then click **Add Features**.
3. Navigate to **Remote Server Administration Tools**  &gt; **Role Administration Tools** and select **AD DS and AD LDS Tools** .
4. Click **Next** to proceed to the confirmation page.
5. Click **Install** to enable it.

To install ADSI Edit on Windows Server 2012 and above

1. Navigate to **Start** &gt;  **Control Panel &gt; Programs** &gt;  **Programs and Features** &gt;  **Turn Windows features on or off**.
2. In the **Add Roles and Features Wizard** dialog that opens, proceed to the **Features** in the left pane.
3. Navigate to **Remote Server Administration Tools → Role Administration Tools** and select **AD DS and AD LDS Tools**.
4. Click **Next** to proceed to the confirmation page.
5. Click **Install** to enable it.