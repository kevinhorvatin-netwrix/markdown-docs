# Filters

The following filters may be applied to search results.

Overview

- All Logon Activity – Azure and AD logon activity. Displays all logon activities active accounts on the organization.
- Activity Outside of Business Hours – Shows user's activity before 9am and after 5pm by default.  This report is helpful for Managed Service Providers to track user's activity outside of working hours
- Changes by Date – Displays  changes in AD and Azure connector activities by date
- Changes by User -– Displays changes in AD and Azure connector activities by user
- Failed Logons – Displays failed logon activities

Active Directory Reports

- Accounts Deleted - Displays activities where user accounts were deleted
- Account Disabled  – Displays activities where user accounts were disabled
- Account Enabled – Displays activities where user accounts were enabled
- Account Locked Out – Displays activities where user accounts were locked out
- Accounts with Password Tampered – User account gets password set to never expire enabled
- Administrative Group Membership Changes – Any activity record relating to users being added to or removed from a security group with one of the following names:

    - Domain Admins
    - Enterprise Admins
    - Schema Admins
    - Account Operators
    - Administrators
    - Backup Operators
    - Incoming Forest Trust Builders
    - Service Operators
- All Active Directory Changes – Changes made to the Active Directory
- All Logon Activity – All the logon attempts for the AD
- Computers Removed – Removed computers from the Active Directory
- Failed Logons –  Failed logon activity for the AD
- Members Added to Privileged Group – Activity records relating to users being added to any privileged group
- Members Removed From Privileged Group – Activity records relating to users being added to any privileged group
- Organizational Unit Management – Changes within the Organizational Unit of the AD domain
- Security Group Membership Changes –  Any activity record relating to users being added to or removed from a security group
- User Account Status Change  – User accounts being enabled / disabled / locked out / unlocked

Azure Active Directory Reports

- All Azure Directory Changes – All the directory changes within the Azure AD
- Azure AD Logon Activity – Logon activity within Azure AD

Exchange Online Reports

- All Exchange Online Changes – Displays all actions for Exchange Online entities
- All Exchange Online Non-Owner Mailbox Access Events – Shows all mailbox access performed by someone other than the mailbox owner. Use this report to protect your Exchange Online organization by identifying unauthorized activity. To view the report, you need to prepare for non-owner mailbox access auditing in the Exchange Online organization. See the [Settings for Non-Owner Mailbox Access Audit: Using Application](../../Configuration/ExchangeOnlineNonOwner.md)  topic for additional information

    To start auditing the data for the report, you need to select the  **Collect non-owner mailbox audit data** check box when adding the Exchange Online source. See the [Add an Exchange Online Source and Connectors](../Organizations/SourcesAndConnectors/ExchangeOnline.md) topic for additional information.
- Exchange Online Group Changes – Shows changes to Exchange Online groups. Use this report to monitor the structure of your Exchange Online groups for changes that could lead to data leaks
- Exchange Online Mail User Changes – Displays activity for the properties of mail users, including delivery restrictions
- Exchange Online Mailbox Permissions Changes – Displays activity for any mailbox permissions
- Exchange Online Mailbox Policy Changes – Shows changes to mailbox policies. Use this report to monitor security in your Exchange Online organization and spot changes to business-critical policies

File Server 

- All File Server Changes – All changes on the File Server
- Copied Files – Copied files on the File Server
- Created Files –Created files on the File Server
- Deleted Files – Deleted files on the File Server
- Moved Files –  Moved files on the File Server

Self Audit

- All Self Audit Activity - All changes on product configuration, including with connectors, data sources, audit scope, and others

SharePoint Online Reports

- All SharePoint Online Activity – All changes across audited SharePoint Online sites and OneDrive for Business
- Content Management – Content changes (uploads, downloads, modifications, etc.) to sites, lists, list items, and documents
- Data Access – Shows which users accessed or downloaded documents from your SharePoint Online sites, or synchronized files in OneDrive for Business
- Sharing and Security Changes – Shows changes to security group membership, policies, and sharing settings, such as promoting a user to site collection administrator or sharing data with external users

By default, {{ MyVariables.ProductName_Overlord }} excludes particular excessive data from the monitoring scope in the SharePoint Online reports. This can be helpful if you want to reduce the time required for data collection, reduce the disk space required to store the collected data, and customize your reports and data searches. 

See the omit list with paths for your information below:

- \*.aspx
- \*/\_catalogs/\*
- \*/\_catalogs
- \*/\_layouts/\*
- \*/\_layouts
- \*/SitePages/\*
- \*/SitePages
- \*/SiteAssets/\*
- \*/SiteAssets
- \*/User Photos/\*
- \*/User Photos
- \*/Style Library/\*
- \*/Style Library
- \*/portals/Community
- \*/portals/hub