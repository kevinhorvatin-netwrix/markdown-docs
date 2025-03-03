# Security

## Physical security

{{ MyVariables.ProductName_Overlord }} runs on Microsoft Azure infrastructure. Click [here](https://azure.microsoft.com/en-us/overview/trusted-cloud/ "here") to learn more about Azure cloud security, or click [here](https://azure.microsoft.com/en-us/overview/trusted-cloud/compliance/ "here") to view all Azure compliance certifications.

## Network security

The Azure SQL database used to store the data is isolated from direct access. We use firewall rules that prevent database access to the API backend services running in Azure.

All API access happens on behalf of specific user accounts in Azure Active Directory. See Access Control section.