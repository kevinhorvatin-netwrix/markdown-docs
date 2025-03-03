# Enable Secondary Logon Service

On the computer where Netwrix Cloud Agent resides, navigate to **Start** &gt; **Windows Administrative** Tools (Windows Server 2016 and higher) or Administrative Tools (Windows 2012) **&gt; Services**.

In the **Services** dialog, locate the **Secondary Logon** service. 

 Right-click the service and on the **General** tab make sure that **Startup type** for this service is other than *Disabled*. Startup type can be either *Automatic* or *Manual*.