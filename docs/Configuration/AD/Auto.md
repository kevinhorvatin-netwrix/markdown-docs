# Active Directory: automatic configuration

This is a recommended method of applying Active Directory audit settings required by {{ MyVariables.ProductName_Overlord }} to monitor your AD domain. With this approach, the program will check your current audit settings at each data collection session and adjust them if necessary.

To adjust audit settings automatically, do any of the following:

- When creating an organization, select the **Adjust audit settings automatically** option.

- For the existing organization, modify data collection settings for Active Directory, selecting **Adjust audit settings automatically** option.

See also: 

- [Configure Domain for Monitoring Active Directory](ADManual.md) 
- [Active Directory: manual configuration](CfgManual.md) 