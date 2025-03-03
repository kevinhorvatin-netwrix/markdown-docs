# SQL Server Ports

Review a full list of protocols and ports required for {{ MyVariables.ProductName_Overlord }} for SQL Server. @Snippet:_CrossProduct/1Secure/SQLServerConf:Ports@

| <madcap:annotation madcap:createdate="2024-12-02T15:41:48.3711988+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="Verify all ports" madcap:editor="AyeshaAzeem" madcap:editdate="2024-12-02T15:41:52.1503593+05:00">Port	</madcap:annotation> | Protocol | Source | Target | Purpose |
| --- | --- | --- | --- | --- |
| 1433 | TCP | Netwrix Cloud Agent | Default SQL Server Instance | Connection to the default named instance server. Port 1433 is the default connections port, however, you can configure another TCP port. |
| 1434 | UDP | Netwrix Cloud Agent | SQL Server Browser Service | Service that helps to resolve named instance servers |
| <br>                            <madcap:annotation madcap:createdate="2024-12-02T15:41:38.6079631+05:00" madcap:creator="AyeshaAzeem" madcap:initials="AY" madcap:comment="The dynamic port range is incorrect.  Should be 49152 to 65535" madcap:editor="AyeshaAzeem" madcap:editdate="2024-12-02T15:41:40.0268415+05:00">Dynamic</madcap:annotation>:<br>
<br>                        <br>1024 -65535 | TCP | Netwrix Cloud Agent | Named SQL Server Instance | Connection to the named instance servers |