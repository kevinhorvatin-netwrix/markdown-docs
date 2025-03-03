# 
            <madcap:keyword term="Best practices: Netwrork traffic compression"></madcap:keyword>Network Traffic Compression

To reduce network traffic in distributed deployments, multi-site networks and other environments with remote locations that have limited bandwidth, it is recommended to use network traffic compression.  For that purpose, special Netwrix utilities should be installed in the audited environment. These utilities will run on the target computers, collect, pre-filter  data and send it to Netwrix Cloud Agent in a highly compressed format. 

With network traffic compression, data from the target machines is collected simultaneously, providing for network load balance and minimizing data collection time. (Unlike that, without network traffic compression the target machines will be processed sequentially, i.e. one at a time.) So, network traffic compression helps to increase scalability and optimize network traffic. @Snippet:1Secure/Configuration:NetworkTrafficCompression@
        
Its key capabilities are as follows:   

- Allows {{ MyVariables.ProductName_Overlord }} to collect detailed metrics for the servers, log files, hardware and individual processes
- Collects audit data with no recognizable load on the server
- Communicates with Netwrix Cloud Agent at predefined intervals, relaying data back to a central repository for storage

Network traffic compression  is available for the following data sources:

- Active Directory
- Computer