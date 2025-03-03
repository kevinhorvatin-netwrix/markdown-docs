# Activity Reports

Activity reports help administrators monitor, track, and analyze various user activities across their audited environment. These reports provide detailed insights into user behavior, helping to identify any suspicious or unauthorized actions. For example, you can easily track all changes made by a specific user, view a list of deleted accounts, and much more.

You can choose to view predefined Activity reports or create customized reports tailored to your needs by applying specific filters. To view custom reports, see the [Create Reports with Custom Filters ](/Admin/SearchAndReports/CreateReportsWithCustomFilters.md) topic.

Activity reports collect data from the following environments:

- Active Directory
- {{ MyVariables.Azure_AD app }}
- Exchange Online
- File Server
- SharePoint Online
- SQL Database

## Review a Report

Follow the steps to review an Activity report.

Navigate to the **Reports** &gt; **Activity** tab. The left pane displays reports organized under the following categories:

- Overview
- Active Directory
- Active Directory - Tags
- Active Directory Reports
- Azure Active Directory Reports
- Custom Reports
- {{ MyVariables.Azure_AD app }}
- Exchange Online
- File Server
- SharePoint Online
- SQL Database

Select a report to view it.

A list of the available Activity reports is given below.

## Overview

| Report Name | Description |
| --- | --- |
| Activity Outside of Business Hours | Lists user activities that occur outside of predefined business hours. It helps detect unusual or suspicious behavior, such as logins or changes made during non-working hours. |
| All Logon Activity | Lists all user login attempts across the environment. It helps track login trends, such as repeated failed login attempts. |
| Changes by Date | Lists all  changes to monitored objects by date. |
| Changes by User | Lists all changes made by a specific user. It helps track specific user action, such as changes made to accounts, permission, settings, etc. |
| Exchange Online | Lists audit logs for the Exchange sandbox. |
| Failed Logons | Lists all failed login attempts. It helps identify potential security issues, such as unauthorized users trying to access the network. |

## Active Directory

| Report Name | Description |
| --- | --- |
| Accounts Deleted | Lists all user accounts that have been deleted. It also provides information about when and by whom the accounts were deleted, which can help identify any unauthorized or suspicious activity within the system. |
| Accounts Enabled | Lists all user accounts that have been disabled. |
| Accounts Disabled | Lists all user accounts that have been disabled. It also provides information about when and by whom the accounts were disabled. |
| Accounts Locked Out | Lists all user accounts that have been locked out. It also provides information about when and by whom the accounts were locked out. |
| Accounts Password Tempered | Lists the user accounts where the password has been altered. It helps to detect unauthorized password changes. |
| Administrative Group Membership Changes | Lists changes to membership of the Domain Admins, Enterprise Admins, Schema Admins, Account Operators, and other administrative groups. Members of these groups are entitled to perform critical activities in your IT infrastructure. Subscribe to this report or review it on a regular basis to detect security issues and ensure that administrative group membership is granted or revoked in compliance with your organization's security policies. |
| All Active Directory Changes | Lists changes to all Active Directory objects including changes to permissions, configuration, etc. This is the most comprehensive report on Active Directory changes. Use it when you need to review every single change to any Active Directory object. |
| All Logon Activity | Lists all user login attempts across the Active Directory. It helps track the login trends, such as repeated failed login attempts. |
| Computers Removed | Lists all computer accounts that have been deleted. It also provides information about when and by whom the accounts were deleted, which can help identify any unauthorized or suspicious activity within the system. |
| Failed Logons | Lists the failed login attempts. It is useful for identifying the potential security issues, such as unauthorized users trying to access the system. |
| Members Added to Administrative Group | Lists all users who have been added to administrative groups. It helps administrators monitor changes to privileged groups and ensures that only authorized users have elevated access. |
| Members Removed from Administrative Group | Lists all users who have been removed from the administrative groups. It helps administrators monitor changes to privileged groups and ensures that only authorized users have elevated access. |
| Organizational Unit Management | Lists changes made to organization units including, changes to name, description, delegation settings, etc. |
| Security Group Membership Changes | Lists changes made to security groups including, changes to group membership, permissions, descriptions, etc. |
| User Account Status Changes | Lists changes made to the status of user accounts, such as enabling, disabling, locking, or unlocking accounts. |

## Microsoft Entra ID

| Report Name | Description |
| --- | --- |
| All {{ MyVariables.Azure_AD app }} Changes | Lists all changes made to {{ MyVariables.Azure_AD app }} objects, including creation, modification, and deletion. |
| {{ MyVariables.Azure_AD app }} Sign-In Activity | Lists all sign-in attempts across{{ MyVariables.Azure_AD app }}. |

## Exchange Online

| Report Name | Description |
| --- | --- |
| All Exchange Online Changes | Lists all changes made to Exchange Online objects, configurations, and permissions. |
| All Exchange Online Non-Owner Mailbox Access Events | Lists all mailbox access performed by someone other than the mailbox owner. Use this report to protect your Exchange Online organization by identifying unauthorized activity. |
| Exchange Online Group Changes | Lists changes made to Exchange Online groups. Use this report to monitor the structure of your Exchange Online groups for changes that could lead to data leaks. |
| Exchange Online Mail User Changes | Lists changes made to the properties ofmailusers, including delivery restrictions. Use this report to detect suspicious activity in your Exchange Online organization. |
| Exchange Online Mailbox Permissions Changes | Lists all changes made to mailbox permissions, such as granting or revoking access rights to specific users. Use this report to detect unapproved permission changes. |
| Exchange Online Mailbox Policy Changes | Lists modifications made to mailbox policies. Use this report to monitor security in your Exchange Online organization and spot changes to business-critical policies. |

## File Server

| Report Name | Description |
| --- | --- |
| All File Server Changes | Lists all activities occurring on audited file servers, including changes, failed modifications, file reads, and failed read attempts. |
| Copied Files | Lists files that were copied within the monitored file share. For each file, it provides details, including the name, original file location, who copied the file, and when it was copied. Use this report to protect critical information against misuse and ensure that files containing sensitive data are not copied without a proper authorization. The report can be generated only for Windows file servers. |
| Created Files | Lists newly created files and folders. It can be used to analyze increased disk space usage. |
| Deleted Files | Lists the deleted files and folders. It helps track the removal of critical data and prevent accidental or unauthorized deletions. |
| Moved Files | Lists files and folders that were moved to a new location within the monitored scope. For each file or folder, the report displays the name and location of the original object, who moved the object, and when it was moved. |

## SharePoint Online

| Report Name | Description |
| --- | --- |
| All SharePoint Online Activity | Lists all activities across SharePoint Online sites and OneDrive for Business. Use this report to monitor overall activity and identify any suspicious or unauthorized actions. |
| Anonymous Sharing Link Created | Lists all instances where anonymous sharing links are created. This report is crucial for monitoring and restricting anonymous access to ensure that only authorized users can view and interact with your content. |
| Content Management | Lists content-related activities, such as uploads, downloads, modifications, and deletions, that have occurred within the sites, lists, list items, and documents. Use this report to detect suspicious activity and prevent the loss of important data. |
| Data Access | Lists the users who have accessed or downloaded documents from your SharePoint Online sites, or who have synchronized files to OneDrive for Business. |
| External User Activity | Lists all activities performed by external users, such as guest users, on SharePoint Online. By using this report, administrators can monitor external user interactionsandensure compliance with external collaboration policies. |
| High Risk Members Added | Monitors the addition of high-risk members to sensitive groups. It helps administrators ensure that changes involving critical groups are closely monitored and align with security policies. |
| High Risk Permissions Added | Tracks the assignment of high-risk permissions, such as granting broad access to various user groups. This report helpsoversee and mitigate potential security risks by ensuring that elevated permissions are granted with proper authorization. |
| New Sharing Link with External User Access | Monitors the creation of new sharing links that grant access to external users. Use this report to oversee and control how content is being shared externally, ensuring that external access is granted appropriately. |
| Sharing and Security Changes | Tracks changes to security group membership, policies, and sharing settings, such as promoting a user to site collection administrator or sharing data with external users. |
| Site Sharing Settings Changed | Tracks changes to site sharing settings, specifically for allowing external users. This report helps you manage and audit when and how your SharePoint sites are made accessible to users outside your organization. |

## SQL Database

| Report Name | Description |
| --- | --- |
| All SQL Logons | Lists all login attempts on the SQL Server. Use this report to analyze user activity on production databases. |
| SQL Failed Logons | Lists the failed login attempts on the SQL Server. Use this report to identify potential security threats and analyze login issues. | @Snippet:1Secure/Reports:ReportSearch@
        
Subscribe to Activity Reports

You can subscribe to Activity reports to receive them automatically via email, or have them uploaded to a specified folder in SharePoint Online. See the [Subscriptions](/Admin/SearchAndReports/Subscriptions.md)  topic for additional information.