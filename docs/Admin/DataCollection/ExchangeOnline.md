# Exchange Online Auditing

Before  adding an Exchange Online data source for your organization, plan for the account that will be used for data collection. This account will be specified in the monitored item (Office 365 tenant) settings.

{{ MyVariables.ProductName_Overlord }} will access the cloud-based Office 365 infrastructure using a dedicated {{ MyVariables.Azure_AD_app }} application, formerly Azure AD. This app should be created manually by user with administrative role and assigned required permissions. See the [App Registration and Configuration in Microsoft Entra ID](../../Configuration/EntraID/RegisterConfig.md)  topic for additional information.