# Configure Windows Firewall Inbound Connection Rules

You can configure Windows Firewall settings through Group Policy settings. To do this, edit the GPO affecting your firewall settings. Navigate to Computer Configuration &gt;  Administrative Templates &gt; Network &gt; Network Connections  &gt; Windows Firewall, select Domain Profile or Standard Profile. Then, enable the Allow inbound remote administration exception.

On each audited server, navigate to Start &gt; Control Panel and select Windows Firewall.

In the Help Protect your computer with Windows Firewall page, click **Advanced settings** on the left.

In the Windows Firewall with Advanced Security dialog, select Inbound Rules on the left.![](../../../Resources/Images/Auditor/ManualConfig/ManualConfig_NLA_Inbound_Connections2016.png)

Enable the following inbound connection rules:

- Remote Event Log Management (NP-In)
- Remote Event Log Management (RPC)
- Remote Event Log Management (RPC-EPMAP)
- Windows Management Instrumentation (ASync-In)
- Windows Management Instrumentation (DCOM-In)
- Windows Management Instrumentation (WMI-In)
- Network Discovery (NB-Name-In)
- File and Printer Sharing (NB-Name-In)
- File and Printer Sharing (Echo Request - ICMPv4-In)
- File and Printer Sharing (Echo Request - ICMPv6-In)