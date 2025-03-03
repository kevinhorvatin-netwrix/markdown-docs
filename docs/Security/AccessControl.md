# Access Control

{{ MyVariables.ProductName_Overlord }} is a multi-tenant cloud application. All data is segregated by tenants and access control is enforced.

Only the users who you explicitly add to your organization in {{ MyVariables.ProductName_Overlord }} get to see your dashboards in the product. User access is set up using a customer Azure AD account. You can further protect access using Azure AD support for Multi-Factor Authentication (MFA). Thus, when users get deprovisioned from their corporate directories they also automatically lose access to {{ MyVariables.ProductName_Overlord }}.

Netwrix employees who have administrative access to the Azure deployment to maintain the application only do so under their own Netwrix corporate accounts and all their activity is audited.