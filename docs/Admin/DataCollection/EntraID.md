# Microsoft Entra ID Auditing

The product supports {{ MyVariables.Azure_AD app }}  (formerly Azure AD) provided within Microsoft Office 365.

{{ MyVariables.ProductName_Overlord }} allows you to audit Office 365 organizations that have established modern authentication as their identity management approach, including support for [multi-factor authentication (MFA)](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-mfa-howitworks). 

In this scenario, {{ MyVariables.ProductName_Overlord }} will access the cloud-based infrastructure via Microsoft Graph and other modern APIs, being authenticated through a pre-configured {{ MyVariables.Azure_AD app }} application with appropriate access permissions. So, you should register a {{ MyVariables.Azure_AD app }}  app  and provide its settings to {{ MyVariables.ProductName_Overlord }} when configuring a monitored item.

## Multi-factor Authentication

Support for modern authentication will allow you to audit the organizations where MFA is enabled for all users, including service accounts. See the [App Registration and Configuration in Microsoft Entra ID](../../Configuration/EntraID/RegisterConfig.md)  topic for additional information.