# Logon Activity Auditing

Before you start adding the logon activity connector in your domain, plan for the domain account that will be used for data collection – it should meet the requirements listed below. Then you will provide this account in the {{ MyVariables.ProductName_Overlord }} configuration window.

Depending on the network traffic compression setting you need to use, one of the following is required:

- If network traffic compression is enabled, then the account must belong to the Domain Admins group;
- If network traffic compression is disabled, then you can choose between account which belongs to the Domain Admins group or non-administrative account. See [Configure Non-Administrative Account to Collect Logon Activity](/Admin/DataCollection/LogonActivity/NonDomainAdmin.md) for more information;