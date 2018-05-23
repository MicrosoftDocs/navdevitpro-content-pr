---
title: "Monitoring Long Running SQL Queries in the Event Log"
description: This topic provides an overview on how to monitor long running SQL queries in the event log starting with NAV 2017. 
ms.custom: na
ms.date: 05/23/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
---
# Monitoring Long Running SQL Queries in the Event Log

<!-- This topic needs to be updated for the BC autumn release. -->
 
[!INCLUDE[nav2017](includes/nav2017.md)] is the first version that allows long running SQL queries to be logged in the event log. The queries are logged when the application communicates with the database and the call to the database takes too long.

## Defining Long Running SQL Queries 
The time used by long running SQL queries is the time spent on the called database as seen from the server. There are multiple reasons that can cause this delay, such as the waiting time allocated to SQL to perform something that takes a long time or SQL executing an operation that perfoms badly due to missing indexes.   
The threshold of what long means is changed in the configuration value of the SqlLongRunningThreshold key. The default value is 1000 ms. For more information about *SqlLongRunningThreshold*, see [Configuring Microsoft Dynamics NAV Server](configuring-microsoft-dynamics-nav-server.md#database-settings). 


## Changing Configuration Values
With [!INCLUDE[nav2018_md](includes/nav2018_md.md)], some of the configuration values for the server can be changed in the memory of the server, without doing a server restart. To reset the configuration values dynamically, run the Dynamics NAV Administration Shell as Administrator and then type the following PowerShell cmdlet:

```
Set-NAVServerConfiguration -KeyName SqlLongRunningThreshold -ServerInstance DynamicsNAV110 -KeyValue 2000 -ApplyTo Memory
```



## See Also
<!-- Include 
[Troubleshooting: Using the Event Log to Monitor Long Running SQL Queries in Dynamics NAV](troubleshooting-long-running-queries-using-event-log.md) once is done. -->

<!--
Hi Kennie! Which articles would you like to have in this section? The ones below are some I thought could help. 

[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md) 
[Set-NAVServerConfiguration](https://go.microsoft.com/fwlink/?linkid=401394)   
[Tools for Monitoring Performance Counters and Events](Tools-for-Monitoring-Performance-Counters-and-Events.md)  
[Monitoring Microsoft Dynamics NAV Server Using Performance Counters](Monitoring-Microsoft-Dynamics-NAV-Server-Using-Performance-Counters.md)  
[Monitoring Microsoft Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md)    
[How to: Use PerfView to Collect Event Trace Data](How-to--Use-PerfView-to-Collect-Event-Trace-Data.md)     
[Troubleshooting: Using Query Store to Monitor Query Performance in Dynamics NAV](troubleshooting-query-performance-using-query-store.md)
-->
