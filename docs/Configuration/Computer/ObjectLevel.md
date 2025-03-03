# Configure Object-Level Access Auditing

{{ MyVariables.ProductName_Overlord }} can be configured to audit all the access types mentioned below:![](../../../Resources/Images/1Secure/ObjectLevelAccessAudit.png "Advanced Activity Selection options")

## Configure Object-level Access Auditing on Windows Server 2012 and Above 
@Snippet:_CrossProduct/Auditor/FileServers:ConfigObjLevelAccess2012@ 
@Snippet:_CrossProduct/Auditor/FileServers:ObjLevelStep1@ 
@Snippet:_CrossProduct/Auditor/FileServers:ObjLevelStep2@ 
@Snippet:_CrossProduct/Auditor/FileServers:ObjLevelStep3@!
[](../../../Resources/Images/Auditor/ManualConfig/Auditing_Entries_NetApp_2016.png "Advanced Security Settings for &lt;Share_Name&gt; dialog box") 
@Snippet:_CrossProduct/Auditor/FileServers:ObjLevelStep4@ 
@Snippet:_CrossProduct/Auditor/FileServers:ObjLevelStep5@

You can specify any other group as needed. The product will audit only user accounts that are members of the selected group.

Apply settings to your Auditing Entries depending on the access types you want to audit. If you want to audit all access types, you need to add separate Auditing Entries for each file share. Otherwise, reports will contain limited data and warning messages.