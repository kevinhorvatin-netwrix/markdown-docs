# Configure Windows Firewall Inbound Connection Rules

For successful data collection, {{ MyVariables.ProductName_Overlord }} may have to create inbound Firewall rules. If you do not enable the Network traffic compression option, the product will try creating these rules automatically and will notify you it fails to do so. In this case, you have to configure Windows Firewall inbound rules manually. 

Follow the steps to configure Windows Firewall Inbound Connection Rules.

On every domain controller, navigate to **Start** &gt; **Control Panel** and select **Windows Firewall**.

In the **Help Protect your computer with Windows Firewall** page, click **Advanced settings** on the left.

In the Windows Firewall with Advanced Security dialog, select Inbound Rules on the left.![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_NLA_Inbound_Connections2016.png)

Enable the following inbound connection rules:

- Remote Event Log Management (NP-In)
- Remote Event Log Management (RPC)
- Remote Event Log Management (RPC-EPMAP)