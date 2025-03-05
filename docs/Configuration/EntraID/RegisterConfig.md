# App Registration and Configuration in Microsoft Entra ID

This topic explains how to configure an app in {{ MyVariables.Azure_AD_app }} (formerly Azure AD) to audit Microsoft 365 data sources (SharePoint Online, {{ MyVariables.Azure_AD_app }}, and Exchange Online) in {{ MyVariables.ProductName_Overlord }} using modern authentication. This app enables secure access to the {{ MyVariables.ProductName_Overlord }} cloud-based infrastructure via Microsoft Graph and other modern APIs. 

You have to  configure the app in {{ MyVariables.Azure_AD_app }} once, as it can be used to audit multiple Microsoft 365 data sources, including SharePoint Online, {{ MyVariables.Azure_AD_app }}, and Exchange Online.

It is recommended to register a dedicated app in {{ MyVariables.Azure_AD_app }} for each data source that you want to audit in {{ MyVariables.ProductName_Overlord }}. While sharing a single app across multiple data sources is allowed, it may lead to issues such as throttling. For example, if there are too many connections to Microsoft Graph, some connections may be temporarily stopped. Additionally, different data sources may require different permissions and you might not grant all permissions to a single app.

To begin auditing Microsoft 365 data sources, manually register the app for {{ MyVariables.ProductName_Overlord }} in {{ MyVariables.Azure_AD_app }} and provide its settings while adding a data source in {{ MyVariables.ProductName_Overlord }}.

A user account with the Global Administrator, Application Administrator, or Cloud Application Administrator role is required to grant admin consent for certain permissions to the registered application. @Snippet:1Secure/Configuration:UnifiedAuditLog@

## Register an App in Microsoft Entra ID

Follow the steps to register an application in {{ MyVariables.Azure_AD_app }}. 
@Snippet:Config/EntraID:AdminCenterNote@ 
@Snippet:Config/EntraID/Register:SignIn@ 
@Snippet:1Secure/EntraIDApp:NavAppReg-Step@

On the App registrations page, click **New registration** in the top toolbar. The Register an application page is displayed.

Specify the following information on the Register an application page:

- Name – Enter a user-facing display name  for the application, for example, {{ MyVariables.ProductName_Overlord }} Entra ID
- Supported account types – Select **Accounts in this organizational directory only**
- Redirect URL (optional) – You can leave the field blank

Click **Register**.

The Overview page for the newly registered application opens. The following settings of the registered application are required  while adding a data source in {{ MyVariables.ProductName_Overlord }}. See the [Sources and Connectors](../../Admin/Organizations/SourcesAndConnectors/README.md) topic for additional information on adding a data source. It is recommended to copy these settings and keep them safe.

- Application (client) ID – A client ID for the registered application
- Directory (tenant) ID – A tenant ID for the registered application
- Client Secret – A client secret value generated when a new client secret key is created for the registered application. See the [Generate Client Secret Value](#Generate)  topic for additional information.

## Grant Permissions to the App

You must grant the necessary permissions to the registered application in {{ MyVariables.Azure_AD_app }}, based on the data sources you plan to audit in.

Follow the steps to grant permissions to the application. 
@Snippet:Config/EntraID/Register:SignIn@ 
@Snippet:1Secure/EntraIDApp:NavAppReg-Step@ 
@Snippet:1Secure/EntraIDApp:AppStep2@

Click the application you registered from the list to grant the permissions. The Overview page of the application is displayed.

Click **API permissions** under the Manage section. The API permissions page is displayed.

On the API permissions page, click **Add a permission**. The Request API permissions pane is displayed with the Microsoft APIs tab selected. The tab lists all the APIs available in {{ MyVariables.Azure_AD_app }}. 

Click an API to access its permissions. The permission types are displayed for it.

Click the **Application permissions** tab. The permission categories are listed. Click a category and select the required permissions under it.

See the following topics for the  list of API permissions required to audit the respective data source.  

- [Permissions to Audit Microsoft Entra ID](Permissions.md#EntraID) 
- [Permissions to Audit SharePoint Online](Permissions.md#SharePt) 
- [Permissions to Audit Exchange Online](Permissions.md#Exchange) 

After selecting the required permission(s), click **Add Permissions** at the bottom. You are navigated to the API Permissions page.

Click **Grant admin consent for &lt;tenant&gt;** to grant the selected permissions to the applcation. 

The  API permissions are granted to the application.

## Assign Roles to the App

The registered application must be assigned to the Global Administrator or Exchange Administrator role for {{ MyVariables.Azure_AD_app }} state collection.  
Follow the steps to assign role(s) to an application. 
@Snippet:Config/EntraID/Register:SignIn@ 
@Snippet:1Secure/EntraIDApp:NavAppReg-Step@ 
@Snippet:1Secure/EntraIDApp:AppStep2@

Click the registered application from the list. The Overview page for the application is displayed.

Click **Roles and administrators** under the Manage section. The Roles and administrators page is displayed. From here, go to the All roles page.

On the All roles page, search for one of the following roles as required.

- Global Administrator – Can manage all aspects of {{ MyVariables.Azure_AD_app }} and Microsoft services that use Microsoft Entra identities
- Exchange Administrator – Can manage all aspects of the Exchange product

Click the desired role. The Assignments page is displayed for it.

Click **Add assignments** in the top toolbar. The Add assignments pane is displayed.

On the Add assignments pane, search your application and select it.

Click the **Add** button at the bottom. The application is listed on the Assignments page.

## Generate  Client Secret Value

Follow the steps to generate a client secret value. 
@Snippet:Config/EntraID/Register:SignIn@ 
@Snippet:1Secure/EntraIDApp:NavAppReg-Step@ 
@Snippet:1Secure/EntraIDApp:AppStep2@

Click the registered application from the list. The Overview page for the application is displayed.

Click **Certificates & secrets** under the Manage section. The Certificates and secrets page is displayed with the Client secrets tab selected by default.

On the Client secrets tab, click **New client secret**. The Add a client secret pane is displayed.

- Description – Enter a description for the secret
- Expires – Select an expiration date for the secret key from the Expiry drop-down-menu. By default, the Recommended: 180 days (6 months) option is selected.

Click the **Add** button. The client secret is generated and the client secret value is displayed in the Value column.

The client secret value is required  while adding a data source  in {{ MyVariables.ProductName_Overlord }}. See the [Sources and Connectors](../../Admin/Organizations/SourcesAndConnectors/README.md) topic for additional information on adding a data source.

If you leave this page before copying the key, it cannot be retrieved, and you will need to repeat the process.

## Upload a Certificate

Certain connecters require a certificate rather than a client secret for authentication. This certificate is downloaded while configuring a data source in {{ MyVariables.ProductName_Overlord }}. Once downloaded, you need to upload the certificate to the registered application  in {{ MyVariables.Azure_AD_app }}. See the [Add a Source and Connectors for SharePoint Online](../../Admin/Organizations/SourcesAndConnectors/SharePointOnline.md) topic for additional information on downloading a certificate.

Follow the steps to upload a certificate to the registered application. 
@Snippet:Config/EntraID/Register:SignIn@ 
@Snippet:1Secure/EntraIDApp:NavAppReg-Step@ 
@Snippet:1Secure/EntraIDApp:AppStep2@

Click the application you registered from the list. The Overview page of the application is displayed.

Click **Certificates & secrets** under the Manage section. The Certificates & secrets page is displayed with the Client secrets tab selected by default.

Click the **Certificates** tab.

On the Certificates tab, click **Upload certificate**. The Upload certificate pane is displayed.

Click the select a file icon next to the Select a File field.

Browse and select the certificate file downloaded during the data source configuration in {{ MyVariables.ProductName_Overlord }}, then click **Open**. The certificate file is selected.

Enter a description for this certificate and click the **Add** button at the bottom. The certificate is uploaded to the registered application.

## Assign Permissions to the App Using Manifest

Follow the steps to assign permissions to the registered application by modifying its attribute values using the Manifest app. See the [Microsoft Entra app manifest (Azure AD Graph format)](https://learn.microsoft.com/en-us/entra/identity-platform/reference-app-manifest#requiredresourceaccess-attribute "Microsoft Entra app manifest (Azure AD Graph format)") article for additional information on Manifest.

This is an alternate way for assigning permissions to the registered application that differs from the normal method discussed in the [Grant Permissions to the App](#Grant) topic. 
@Snippet:Config/EntraID/Register:SignIn@ 
@Snippet:1Secure/EntraIDApp:NavAppReg-Step@ 
@Snippet:1Secure/EntraIDApp:AppStep2@

Click the application you registered from the list. The Overview page of the application is displayed.

Click **Manifest** under the Manage section. The Manifest page is displayed.

Locate the **requiredResourceAccess** property in the manifest and edit it with the following in the square brackets ([]). The **requiredResourceAccess** property should look like this:

```json
"requiredResourceAccess": [
  {
     "resourceAppId": "00000003-0000-0ff1-ce00-000000000000",
     "resourceAccess": [
        {
           "id": "678536fe-1083-478a-9c59-b99265e6b0d3",
           "type": "Role"
        }
     ]
  },
  {
     "resourceAppId": "00000003-0000-0000-c000-000000000000",
     "resourceAccess": [
        {
           "id": "b0afded3-3588-46d8-8b3d-9842eff778da",
           "type": "Role"
        },
        {
           "id": "7ab1d382-f21e-4acd-a863-ba3e13f7da61",
           "type": "Role"
        },
        {
           "id": "246dd0d5-5bd0-4def-940b-0421030a5b68",
"type": "Role"
},
{
"id": "332a536c-c7ef-4017-ab91-336970924f0d",
"type": "Role"
}
]
},
{
"resourceAppId": "c5393580-f805-4401-95e8-94b7a6ef2fc2",
"resourceAccess": [
{
"id": "594c1fb6-4f81-4475-ae41-0c394909246c",
"type": "Role"
}
]
},
{
"resourceAppId": "00000002-0000-0ff1-ce00-000000000000",
"resourceAccess": [
{
"id": "dc50a0fb-09a3-484d-be87-e023b12c6440",
"type": "Role"
}
]
}
]
```

Click **Save**.

Optionally, you can select **Download** to edit the manifest locally, and then use Upload to reapply it to your application.