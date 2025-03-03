# SharePoint Online Auditing

 {{ MyVariables.ProductName_Overlord }} allows you to audit Office 365 organizations that have established modern authentication as their identity management approach, including support for [multi-factor authentication (MFA)](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-mfa-howitworks "multi-factor authentication (MFA)"). See the Microsoft <madcap:xref href="../../Configuration/EntraID/RegisterConfig.htm" target="_parent" title="App Registration and Configuration in Microsoft Entra ID" alt="App Registration and Configuration in Microsoft Entra ID"><a href="https://docs.microsoft.com/en-us/office365/enterprise/hybrid-modern-auth-overview#BKMK_WhatisModAuth" target="_blank" title="What is modern authentication" alt="What is modern authentication">What is modern authentication</a></madcap:xref> article for additional information.

In this scenario, {{ MyVariables.ProductName_Overlord }} will access the cloud-based infrastructure via Microsoft Graph and other modern APIs, being authenticated through a pre-configured {{ MyVariables.Azure_AD app }} application, formerly Azure AD, with appropriate access permissions. So, you should register a {{ MyVariables.Azure_AD app }} app and provide its settings to {{ MyVariables.ProductName_Overlord }}when adding a SharePoint Online data source.

## Modern Authentication

 Support for modern authentication will allow you to audit the organizations where MFA is enabled for all users, including service accounts.  See the [App Registration and Configuration in Microsoft Entra ID](../../Configuration/EntraID/RegisterConfig.md)  topic for additional information.

## Configure SharePoint Online Auditing

To collect audit data from your SharePoint Online and OneDrive for Business, {{ MyVariables.ProductName_Overlord }} uses a dedicated {{ MyVariables.Azure_AD app }} application and leverages  APIs access permissions granted to that app. To register this application and assign required permissions, an Azure AD  account with an administrative role will be required:

 {{ MyVariables.Azure_AD app }} application should be created manually by user with administrative role and assigned required permissions. This app will allow you to collect activity. See the [App Registration and Configuration in Microsoft Entra ID](../../Configuration/EntraID/RegisterConfig.md)  topic for additional information.

##