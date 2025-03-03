# Protocols and Ports Required for Monitoring File Servers

Review a full list of protocols and ports required for {{ MyVariables.ProductName_Overlord }} for File Servers.

- Allow outbound connections from the dynamic (1024 - 65535) local port on the computer where Netwrix Cloud Agent resides.
- Allow outbound connections to remote ports on the source and inbound connections to local ports on the target.

Tip for reading the table: For example, on the computer where Netwrix Cloud Agent  resides (source), allow outbound connections to remote 389 TCP port. On domain controllers in your domain (target), allow inbound connections to local 389 TCP port.

| **Port** | <![CDATA[	]]>**Protocol** | **Source** | **Target** | <![CDATA[	]]>**Application protocol** |
| :---: | :---: | :---: | :---: | :---: |
| <br>389 | <br><br>TCP/UDP | <br><br>Netwrix Cloud Agent | Domain Controllers | <br>LDAP<br><br>
<br>                        <br><br>DC query<br><br><br>
<br>                        <br>Account resolve |
| 135<br><br>+ Dynamic:<br><br>1024 -65535 | TCP | <br><br>Netwrix Cloud Agent | <br>Monitored computer | <br>Windows Management Instrumentation<br>
<br>                        <br><br><br>Firewall configuration<br><br>
<br>                        <br><br>Core Service communication |
| 135 | TCP | <br><br>Netwrix Cloud Agent | <br>Monitored computer | Service Control Manager Remote Protocol Core Service installation<br> |
| 137 | UDP | <br><br>Netwrix Cloud Agent | <br>Monitored computer | File and Printer Sharing (NetBIOS Name Resolution) |
| 138 | UDP | <br><br>Netwrix Cloud Agent | Monitored computer | File and Printer Sharing (NetBIOS Datagram Service) |
| 139 | TCP | <br><br>Netwrix Cloud Agent | Monitored computer | File and Printer Sharing (NetBIOS Session Service) |
| 445 + 139 | TCP | <br><br>Netwrix Cloud Agent | <br>Monitored computer | <br>SMB 2.0/3.0 |
| 3268 | TCP | Netwrix Cloud Agent | Domain controllers
<br><br> | LDAP<br>
<br>                        <br>Group membership<br>
<br>                        <br>GC search |

<![CDATA[ 

]]>