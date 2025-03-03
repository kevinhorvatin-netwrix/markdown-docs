# What's New 

## New Netwrix Community!

All Netwrix product announcements have moved to the new Netwrix Community. See announcements for Netwrix 1Secure in the [1Secure](https://community.netwrix.com/c/1secure/announcements/161 "https://community.netwrix.com/c/1secure/announcements/161") area of our new community.

## Netwrix 1Secure 2024.12.13

New Alerts and Permission Reports for SharePoint Online

We have introduced four new state-in-time reports and six alerts to help users detect risky permission configurations in SharePoint Online. These new reports and alerts enhance visibility and provide actionable insights to maintain a secure SharePoint environment.

Alerts

- External User Activity – Keeps track of all actions performed by guest users.
- Sharing with Anyone Enabled on Site – Helps manage and audit when and how SharePoint sites are made accessible to users outside the organization.
- New Sharing Link with External User Access – Reports the creation of new sharing links that grant access to external users. Helps control how content is being shared externally, ensuring that external access is granted appropriately.
- Anonymous Sharing Link Created – Monitors anonymous access to ensure that only authorized users can view and interact with the content.
- High-Risk Permissions Added – Helps oversee and mitigate potential security risks by ensuring that elevated permissions are granted with proper justification.
- High-Risk Members Added – Helps to ensure that membership changes involving broad or sensitive groups are properly monitored and controlled.

Reports

- Direct User Permissions – Displays user accounts with direct permissions to specific objects, such as documents, lists, or sites. You can filter the list by object types, account status (enabled or disabled), last logon time, or if it’s a guest account.
- Broken Permissions Inheritance – Lists objects with permissions different from their parent, for example, when a folder has different permissions than the site it’s located in, which makes it harder to keep permissions manageable.
- High-Risk Permissions – Shows the permissions of Authenticated users, Anonymous logon, or domain users, including the object URL, resource type, and permission level.
- Direct Object Permissions – Displays all identities (users or groups) that have assigned permissions to specific objects, such as documents, lists, or sites.

New Alerts and Reports for {{ MyVariables.Azure_AD_app }}

Thirteen new alerts and ten new activity reports are now available for {{ MyVariables.Azure_AD_app }} to assist in threat detection. Seven reports and seven alerts (based on these new reports) are completely new. Six of the thirteen alerts and three of the ten reports, previously available for Active Directory, now also cover {{ MyVariables.Azure_AD_app }} activities, helping users better detect and respond to potential threats.

New {{ MyVariables.Azure_AD_app }} alerts and reports

- {{ MyVariables.Azure_AD_app }} Role Management Permission Grant – Identifies when the Microsoft Graph RoleManagement.ReadWrite.Directory (Delegated or Application) permission is granted to a service principal. An adversary could use this permission to add a {{ MyVariables.Azure_AD_app }} object to an Admin directory role and escalate privileges.
- Mail.Read Permissions Granted to Application – Detects applications that have been granted permissions to read mail in all mailboxes without a signed-in user. This can help identify applications that have been abused to gain access to mailboxes.
- MFA Rejected by User – Identifies occurrences where a user has rejected an MFA prompt. This could be an indicator that a threat actor has compromised the username and password of this user account and is using them to try and log into the account.
- (Multiple) User Removed from a Privileged Role – Detects when one or more existing admins are removed, which can be an attempt by adversaries to lock down the organization and retain sole access.
- (Multiple) {{ MyVariables.Azure_AD_app }} Admin Permissions Granted – Identifies when one or more users' permissions are changed at once.
- User Added to a {{ MyVariables.Azure_AD_app }} Privileged Group – Tracks when a user is added to any of the Privileged Groups.
- User Assigned New Privileged Role – Identifies when a new eligible or active privileged role is assigned to a user.

Alerts (previously available for Active Directory)

- Account Deleted – Alerts when a user, computer, or account is deleted.
- Account Disabled – Alerts when a user, computer, or account is disabled.
- Account Enabled – Alerts when a user, computer, or account is enabled.
- Account Locked Out – Alerts when a user account is locked out due to multiple incorrect password inputs.
- Account with Password Tampered – Alerts on changes to the "Password never expires" setting.
- Multiple Failed Logons – Alerts when a user account fails to log on multiple times in a short time frame.

Reports (previously available for Active Directory)

- All Logon Activity – Helps validate compliance and analyze user activity by showing all {{ MyVariables.Azure_AD_app }} logon activities.
- Failed Logons – Shows failed logon attempts.
- User Account Status Changes – Shows changes to the status (enabled, disabled, locked, or unlocked) of user accounts.

New Data Source: SQL Server Logon Reporting

SQL Server is now available as a new data source in {{ MyVariables.ProductName_Overlord }}, enhancing database visibility and security monitoring. The initial two reports allow users to review both successful and failed logon attempts to their SQL databases:

- All SQL Logons – Logs all SQL logon attempts, providing insights into who is accessing the database and when.
- SQL Failed Logons – Logs failed logon attempts, helping users detect potential security threats and unauthorized access attempts.

Risk Mapping with MITRE ATT&CK Matrix for Enterprise

All risks in the {{ MyVariables.ProductName_Overlord }} risk assessment dashboard are now categorized based on the MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK) framework. This categorization helps users understand risks in the context of the cyberattack lifecycle and prioritize responses accordingly, improving their overall security posture.

Major Enhancements

- Numerous additional enhancements have been made to improve administration, performance, and security.

## Netwrix 1Secure 2024.09.12

New: {{ MyVariables.Azure_AD_app }} Reports

Two new reports provide visibility into roles and role members within your {{ MyVariables.Azure_AD_app }} organization. Use these reports to identify improper role assignments or modifications and strengthen your organization's security posture. The new reports include:

- Roles
- Role Members

New: Active Directory Report - Organizational Units

This report shows organizational units and their paths, offering insight into your organization's structure.

New: Co-Managing User Role for Child Organizations

Managed Service Providers (MSPs) can now grant end customers the “Co-managing user” role, allowing them to configure data collection and agent installation within their own organizations.

Enhancement: Billable Users Reporting

Users can now access the Billable Users report to review billable accounts for greater transparency in billing.

## Netwrix 1Secure 2024.04.18

New: Netwrix 1Secure is available for End-Customers

Netwrix 1Secure is available for end-customers. The actionable dashboards in the new user interface ensure that end-customers are promptly alerted to areas requiring attention, while human-readable reports empower them to address auditor or management inquiries with ease. See the [Add Users](/Admin/Organizations/AddingUsers.md)  topic for additional information. 

New: Active Directory Compliance Reports

Six new reports assist clients and Managed Service Providers in gathering information about their Active Directory configuration state at a specific moment, enabling them to demonstrate compliance with various regulations to auditors. The new reports include:

- User Accounts with Attributes
- User Accounts – Locked
- User Accounts – Expired
- User and Computer Accounts – Last Logon Time
- User Membership Report
- Group Membership Report

New: Microsoft Entra ID (formerly Azure AD) Compliance Reports

A new report helps clients and Managed Service Providers collect information about their Microsoft Entra ID configuration state at a specific moment, enabling them to prove compliance with many regulations to auditors. The new report is:

- Azure AD Accounts with Attributes

New: Exchange Online Reports

Three new reports improve the security posture of clients and MSPs by showing:

- All mailbox access performed by someone other than the mailbox owner
- Changes to Exchange Online groups
- Changes to mailbox policies

These reports not only protect Exchange Online by identifying unauthorized activity, but also monitor Exchange Online groups and policies for changes that could lead to data leaks and breaches. See the [Filters](/Admin/SearchAndReports/FilterValues.md)  topic for additional information. 

New: Risk Assessment 2.0

The completely redesigned Risk Assessment not only helps clients and MSPs diagnose their security posture better than ever, but also identifies many new risk factors. Users can subscribe to the report and export it as a .pptx file. Furthermore, {{ MyVariables.Azure_AD_app }} data is incorporated into the assessed risks. The list of new risks includes:

- User Accounts with "No MFA Configured"
- Stale Guest Accounts
- User Accounts Created via Email Verified Self-Service Creation Found
- Dangerous Default Permissions
- Third-Party Applications Allowed
- Unified Audit Log Search is Not Enabled
- MS Graph Powershell Service Principal Assignment Not Enforced
- MS Graph Powershell Service Principal Configuration Missing
- Expired Domain Registration Found
- Self-Service Password Reset is Not Enabled
- Improper Number of Global Administrators

See the [Review Risks using Risks Assessment Dashboard](/Admin/RiskProfiles/RiskAssessmentDashboard.md)  topic for additional information. 

Enhancement: Subscribed Reports for SharePoint Online

Users can now set SharePoint Online as a destination for subscribed reports. See the [SharePoint Online](Integration/SharePointOnline.md)  topic for additional information.