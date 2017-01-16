---
title: "Microsoft Dynamics NAV Performance Counters"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 5c13ad00-234e-4307-8159-deef62da9b90
caps.latest.revision: 28
manager: edupont
---
# Microsoft Dynamics NAV Performance Counters
The following table describes the performance counters that are available in [!INCLUDE[navnow](includes/navnow_md.md)] for monitoring [!INCLUDE[nav_server](includes/nav_server_md.md)] instances.  

|Category|Counter|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|-------------|---------------------------------------|  
|Client, server instance, NAS, and web service sessions|\# Active sessions|Number of active sessions on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.<br /><br /> An active session is a connection to the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance from a [!INCLUDE[navnow](includes/navnow_md.md)] client, such as the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)], NAS, or Web services.|
|<br />|# Available tasks|*tbd*|
|<br />|# of task erors/sec|*tbd*|
|<br />|# Running tasks|*tbd*|
|<br />|Total # Running tasks|*tbd*|
|<br />|# Total # Pending tasks|*tbd*|
|<br />|Average task execution time|*tbd*|
|<br />|Maximum # of tasks|*tbd*|
|<br />|Time (ms) since the list of running tasks last had capacity for new tasks|The time (ms) since the list of running tasks last had capacity for new tasks.|
|<br />|Server operations/sec|Number of operations that have started on the [!INCLUDE[nav_server](includes/nav_server_md.md)] per second.<br /><br /> An operation is a call to the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance from a [!INCLUDE[navnow](includes/navnow_md.md)] client to run [!INCLUDE[navnow](includes/navnow_md.md)] objects. **Note:**  OData and SOAP requests are not included.|
|<br />|Average server operation time \(ms\)|Average duration of server operations in milliseconds.|
|SQL Server connections|\# Mounted tenants|Number of tenants that are mounted on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.<br /><br /> For more information about tenants, see [Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md).|
|<br />|\# Open connections|The current number of open connections from the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to [!INCLUDE[navnow](includes/navnow_md.md)] databases on SQL Servers.|
|<br />|# Open application connections|The current number of open application connections from the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to the [!INCLUDE[navnow](includes/navnow_md.md)] application database on SQL Servers.|
|<br />|\# Open tenant connections|The current number of open tenant connections from the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to [!INCLUDE[navnow](includes/navnow_md.md)] databases on SQL Servers.|
|<br />|% Query repositioning rate|Percentage of queries that are re-executed when fetching the query result.|
|<br />|Hard throttled connections|*tbd*|
|<br />|Soft throttled connections|*tbd*|
|<br />|Transient errors|*tbd*|
|<br />|Heartbeat time \(ms\)|The time that it takes to complete a single write to a system table. Every 30 seconds, the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance writes a record to indicate that the instance is "alive."<br /><br /> You can use this counter to indicate if there is network latency between the [!INCLUDE[nav_server](includes/nav_server_md.md)] and the SQL Server.|
|<br />|\# Preferred connection total requests|Count of the total number of requests to the preferred connection cache. The preferred connection cache contains requests from the SQL connection pool that was last used by a [!INCLUDE[navnow](includes/navnow_md.md)] user.|
|<br />|% Preferred connection cache hit rate|Percentage of hits in the preferred connection cache, compared to the total number of requests.|
|Data and caching|\# Calculated fields cache total requests|Count of the total number of requests to the calculated fields cache. The calculated fields cache contains the results of [CALCFIELDS Function \(Record\)](CALCFIELDS-Function--Record-.md) calls.|
|<br />|% Calculated fields cache hit rate|Percentage of hits in the calculated fields cache, compared to the total requests to the calculated fields cache.|
|<br />|\# Command cache total requests|Count of the total number of requests to the command cache. The command cache contains the results of all SQL commands.|
|<br />|% Command cache hit rate|Percentage of hits in the command cache, compared to the total requests to the command cache.|
|<br />|\# Primary key cache total requests|Count of the total number of requests to the primary key cache. The primary key cache contains the results of requests to get a record by using its primary key.|
|<br />|% Primary key cache hit rate|Percentage of hits in the primary key cache, compared to the total requests to the primary key cache.|  
|<br />|\# Result set cache total requests|Count of the total number of requests to the result set cache. The result set cache contains result sets that are returned from SQL Server.|
|<br />|% Result set cache hit rate|Percentage of hits in the result set cache, compared to the total requests to the result set cache.|
|<br />|\# Rows in all temporary tables|Count of number of rows in all temporary tables.|

## See Also  
 [How to: Set up Performance Counters in Windows Performance Monitor](How-to--Set-up-Performance-Counters-in-Windows-Performance-Monitor.md)   
 [How to: Create a Data Collector Set From the Microsoft Dynamics NAV Template](How-to--Create-a-Data-Collector-Set-From-the-Microsoft-Dynamics-NAV-Template.md)   
 [Optimizing SQL Server Performance with Microsoft Dynamics NAV](Optimizing-SQL-Server-Performance-with-Microsoft-Dynamics-NAV.md)   
<!-- temporatily removed until we determine our support for this [Microsoft Dynamics NAV Management Pack for System Center Operations Manager](http://go.microsoft.com/fwlink/?LinkID=722863) -->
