# Protocols and Ports Required for Monitoring Active Directory, Exchange, and Group Policy

Review a full list of protocols and ports required for monitoring Active Directory, Exchange, and Group Policy.

- Allow outbound connections from the dynamic (1024 - 65535) local port on the computer where Netwrix Cloud Agent resides.

- Allow outbound connections to remote ports on the source and inbound connections to local ports on the target.

Tip for reading the table: For example, on the computer where Netwrix Auditor Server resides (source), allow outbound connections to remote 389 TCP port. On domain controllers in your domain (target), allow inbound connections to local 389 TCP port.

| Port | Protocol | Source | Target | Purpose |
| --- | --- | --- | --- | --- |
| 389<br><br> | TCP<br> | Netwrix Cloud Agent | <br>Domain controllers<br> | LDAP<br><br><br>
<br>                        <br>Common queries |
| 3268 | TCP<br> | Netwrix Cloud Agent | <br>Domain controllers<br> | LDAP<br>
<br>                        <br>Group membership<br>
<br>                        <br>GC search |
| 3269 | TCP<br> | Netwrix Cloud Agent | Domain controllers | Global catalog LDAP over SSL |
| 88 | TCP/UDP<br> | Netwrix Cloud Agent | Domain controllers | Kerberos authentication |
| 135<br><br>and dynamic range:<br><br>1024 -65535 | TCP<br> | Netwrix Cloud Agent | Domain controllers | Windows Management Instrumentation<br>
<br>                        <br>gpupdate /force |
| 445 | TCP<br> | Netwrix Cloud Agent | Domain controllers | SMB 2.0/3.0<br>
<br>                        <br>Authenticated communication between Netwrix Cloud Agent and domain controllers. |
| 53 | UDP | Netwrix Cloud Agent | Domain controllers | DNS Client |
| 135<br><br>and dynamic range:<br><br>1024 -65535 | TCP<br> | Netwrix Cloud Agent | Exchange Server | <ul>
<br>                            <li>
<br>                                <p style="text-align: center;">Windows Management Instrumentation</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Retrieve Exchange Server configuration settings*</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>Run gpupdate /force *</p>
<br>                            </li>
<br>                        </ul>
<br>                        <br>gpupdate /force |
| 5985<br>
<br>                        <br>5986 | TCP<br> | Netwrix Cloud Agent | Exchange Server | <ul>
<br>                            <li>
<br>                                <p>Windows Remote Management</p>
<br>                            </li>
<br>                            <li>
<br>                                <p>PowerShell connections:</p><ul style="list-style-type: circle;">
<br>                                    <li>
<br>                                        <p>5985 - for HTTP</p>
<br>                                    </li>
<br>                                    <li>
<br>                                        <p>5986 - for HTTPS</p>
<br>                                    </li>
<br>                                </ul>
<br>                            </li>
<br>                        </ul> |