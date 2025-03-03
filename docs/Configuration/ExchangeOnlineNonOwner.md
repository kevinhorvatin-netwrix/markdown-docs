# Settings for Non-Owner Mailbox Access Audit: Using Application

To prepare for non-owner mailbox access auditing in the Exchange Online organization, you will need to take several configuration steps, creating a {{ MyVariables.Azure_AD app }} app with the required permissions and instructing this app to automatically apply the necessary audit settings. 

These settings shall provide configuration for the All Exchange Online Non-Owner Mailbox Access Events report. See the [Filters](../Admin/SearchAndReports/FilterValues.md)  topic for additional information. 

To start auditing the data for the report, you need to select the **Collect non-owner mailbox audit data**  check box when adding the Exchange Online source. See the [Add an Exchange Online Source and Connectors](../Admin/Organizations/SourcesAndConnectors/ExchangeOnline.md) topic for additional information. @Snippet:1Secure/Configuration:UnifiedAuditLog@

## Grant Permissions  to the Application

Follow the steps to grant permissions to the {{ MyVariables.Azure_AD app }} application. @Snippet:Config/EntraID:AdminCenterNote@
        
In the {{ MyVariables.Azure_AD admin center }}, create and register a {{ MyVariables.Azure_AD app }} app. See the 

After you created an app, select the newly-created, registered application. If you left the Overview page, it will be listed in the **Identity** &gt; **Applications** &gt; **App registrations** &gt; **All applications** list. @Snippet:Config/EntraID/GrantPermissions:APIPermissions@ @Snippet:Config/EntraID/GrantPermissions:AddPermission@

On the Request API permissions blade, click the **APIs my organization uses** tab and search for *Office 365 Exchange Online*. 

Click on the *Office 365 Exchange Online* entry in the list of apps found.

                Proceed with adding the permissions for this app: select **Application permissions** and then select **Exchange.ManageAsApp**. @Snippet:Config/EntraID/GrantPermissions:GrantAdminConsent@

The application is granted the required API permissions. 

## Grant Required Roles

Follow the steps to grant roles to the registered application. @Snippet:Config/EntraID:AdminCenterNote@ @Snippet:Config/EntraID/GrantRoles:RolesAndAdmins@ @Snippet:Config/EntraID/GrantRoles:SearchRoles@ @Snippet:Config/EntraID/GrantRoles:AssignmentsPage@ @Snippet:Config/EntraID/GrantRoles:AddAssignments@

The application is granted the required roles. 

## Set Up an Environment

Follow the steps to set up your environment using PowerShell. 

Install the Exchange Online PowerShell V2 module.

Make sure you are using the version specified in the [related Microsoft article](https://docs.microsoft.com/en-us/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps).

Download the PowerShell script for certificate creation, as provided in the [Microsoft instruction](https://docs.microsoft.com/en-us/powershell/exchange/app-only-auth-powershell-v2?view=exchange-ps#step-3-generate-a-self-signed-certificate). 

To create a self-signed certificate to be used by the app, run the following command in Powershell:

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">.\Create-SelfSignedCertificate.ps1 -CommonName "MyCompanyName" -StartDate 2020-04-01 -EndDate 2022-04-01</madcap:codesnippetbody>
        </madcap:codesnippet>
        
where:

- `CommonName` — specify *"Netwrix 1Secure"*
- `StartDate` — set to current date
- `EndDate` — set to 2 years from now

When prompted to specify a password, click **Enter**.

Go to **Identity** &gt; **Applications** &gt; **App registrations** &gt; "your app" &gt;   **Certificates & secrets**. 

Click **Upload certificate** and upload the*.crt* file you have just created.

To create Exchange Online connection session, you can provide certificate file path or thumbprint. If you want to use a file path, run the following command in Powershell:   

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">Connect-ExchangeOnline -CertificateFilePath "full_path_to_certificate" -AppID "yourAppId" -Organization "Office365_tenant_name"</madcap:codesnippetbody>
        </madcap:codesnippet>
        
Application (client ID) can be found in the **Overview** page.

 For example:

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">Connect-ExchangeOnline -CertificateFilePath "C:\Path\MyCompanyName1.pfx" -AppId "402b12a2-fb2b-4222-8f54-5596def1" -Organization "myorganization123.onmicrosoft.com"</madcap:codesnippetbody>
        </madcap:codesnippet>
        
You can use certificate thumbprint instead of file path. For that, import the certificate to the local certificate store, using the following command in Powershell:

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">Import-PfxCertificate -FilePath "path_to_pfx_certificate" -CertStoreLocation Cert:\CurrentUser\My</madcap:codesnippetbody>
        </madcap:codesnippet>
        
Then run the command in Powershell like following: 

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">Connect-ExchangeOnline -CertificateThumbprint 6AEА5A82911ААА3F76FEE149B7B52А70DDFD88 -AppId a14a 822d-f228-412b-9222-281de23 -Organization myorganization123.onmicrosoft.com</madcap:codesnippetbody>
        </madcap:codesnippet>
        
To set up the audit, run the following command in Powershell: 

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">Get-ExoMailbox -PropertySets Minimum -RecipientTypeDetails UserMailbox,SharedMailbox,EquipmentMailbox,LinkedMailbox,RoomMailbox | Set-Mailbox -AuditEnabled $true –AuditAdmin Update,Copy,Move,MoveToDeletedItems,SoftDelete,HardDelete,FolderBind,SendAs,SendOnBehalf,Create –AuditDelegate Update,Move,MoveToDeletedItems,SoftDelete,HardDelete,FolderBind,SendAs,SendOnBehalf,Create</madcap:codesnippetbody>
        </madcap:codesnippet>
        
Finally, run the following command in Powershell to end the session:   

        <madcap:codesnippet>
            <madcap:codesnippetbody madcap:uselinenumbers="False" madcap:linenumberstart="1" madcap:continue="False" xml:space="preserve" style="mc-code-lang: PowerShell;">Disconnect-ExchangeOnline -Confim:$False</madcap:codesnippetbody>
        </madcap:codesnippet>
        
To automate steps 8-9, you can create a script comprising the corresponding commands and schedule its launch.