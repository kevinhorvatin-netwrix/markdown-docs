# Active Directory: manual configuration

To configure your domain for monitoring manually, you will need:

- **Group Policy Management Console** —  if you plan to perform configuration steps from a domain controller
     -OR-
- **ADSI Edit** — if you plan to perform configuration steps from a server other than domain controller

If these tools are not installed, refer to the related topics:

- [Install ADSI Edit](/Configuration/AD/ADSI.md) 
- [Group Policy Management Console](/Configuration/AD/GroupPolicyManagementConsole.md) 

Take the following configuration steps:

 Configure effective domain controllers policy (by default, Default Domain Controllers Policy). See [Configure Basic Domain Audit Policies](/Configuration/AD/DomainAuditPolicies.md)  
		or [Configure Advanced Audit Policies](/Configuration/AD/AdvancedPolicy.md)  for details. [Configure Object-Level Auditing](/Configuration/AD/ObjectLevel.md)  [Adjust Security Event Log Size and Retention Settings](/Configuration/AD/SecurityLogSize.md) 

If you have an on-premises Exchange server in your Active Directory domain, consider that some changes to AD can be made via that Exchange server. To be able to audit and report who made those changes, you should [Configure Exchange Administrator Audit Logging Settings](../../Admin/DataCollection/ActiveDirectory/AuditLogging.md) 

Also, remember to do the following for AD auditing:

Configure Data Collecting Account, as described in [Active Directory Auditing](../../Admin/DataCollection/ActiveDirectory/ActiveDirectoryAuditing.md) 

Configure required protocols and ports, as described in [Protocols and Ports Required for Monitoring Active Directory, Exchange, and Group Policy](/Configuration/AD/ProtocolsAndPorts.md)  topic. [Enable Secondary Logon Service](/Configuration/AD/SecondaryLogonService.md)  on the computer where Netwrix Cloud Agent resides.