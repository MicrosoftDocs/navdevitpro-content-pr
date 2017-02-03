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
author: jswymer
---
# Microsoft Dynamics NAV Performance Counters
The following table describes the performance counters that are available in [!INCLUDE[navnow](includes/navnow_md.md)] for monitoring [!INCLUDE[nav_server](includes/nav_server_md.md)] instances.

##  Client session counters
These counters pertain to sessions from the clients, NAS, and web services, to the server instance.
|  Counter  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|-----------|-----------------------------------------------------------------------|
|\# Active sessions|Number of active sessions on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.<br /><br /> An active session is a connection to the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance from a [!INCLUDE[navnow](includes/navnow_md.md)] client, such as the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)], NAS, or Web services.|
|<br />|Server operations/sec|Number of operations that have started on the [!INCLUDE[nav_server](includes/nav_server_md.md)] per second.<br /><br /> An operation is a call to the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance from a [!INCLUDE[navnow](includes/navnow_md.md)] client to run [!INCLUDE[navnow](includes/navnow_md.md)] objects. **Note:**  OData and SOAP requests are not included.|
|<br />|Average server operation time \(ms\)|Average duration of server operations in milliseconds.|

### Investigating poor client performance 
If you are experiencing poor or degraded performance of the clients, perform the following tasks:

1.  Monitor the ‘CPU usage %’ (% Processor Time counter).

    If the value consistently matches ‘logical cores’ – 1 (50% on 1-core machines, 75% on 2-core machines), this indicates that the thread dispatcher constantly has threads waiting to execute.

2.  Monitor the **# Active sessions** counter
    High ‘CPU usage %’ can be caused by background tasks or client sessions. Looking at **# Active sessions** gives an indication of whether the load is because of the large number of sessions (see notes below).

3. Monitor the **Total # Pending Tasks** counter

    Another strong indicator of an overloaded CPU is a persistently high **Total # Pending Tasks** value. If **Total # Pending Tasks** is high, take a look at the scheduled task performance counters to help identify possible cause.
4.  Monitor the **Heartbeat time \(ms\)** counter

    The **Heartbeat time \(ms\)** counter can indicate whether there is high latency to the database server.

## SQL Server connection counters
These counters pertain to the connection from the server instance to the SQL Server instance and databases.
|  Counter  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|-----------|-----------------------------------------------------------------------|
|\# Mounted tenants|Number of tenants that are mounted on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.<br /><br />For more information about tenants, see [Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md).|
|\# Open connections|The current number of open connections from the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to [!INCLUDE[navnow](includes/navnow_md.md)] databases on SQL Servers.|
|# Open application connections|The current number of open application connections from the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to the [!INCLUDE[navnow](includes/navnow_md.md)] application database on SQL Servers.|
|\# Open tenant connections|The current number of open tenant connections from the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to [!INCLUDE[navnow](includes/navnow_md.md)] databases on SQL Servers.|
|% Query repositioning rate|Percentage of queries that are re-executed when fetching the query result.|
|Hard throttled connections|*tbd*|
|Soft throttled connections|*tbd*|
|Transient errors|*tbd*|
|Heartbeat time \(ms\)|The time that it takes to complete a single write to a system table. Every 30 seconds, the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance writes a record to indicate that the instance is "alive."<br /><br />You can use this counter to indicate if there is network latency between the [!INCLUDE[nav_server](includes/nav_server_md.md)] and the SQL Server.|
|\# Preferred connection total requests|Count of the total number of requests to the preferred connection cache. The preferred connection cache contains requests from the SQL connection pool that was last used by a [!INCLUDE[navnow](includes/navnow_md.md)] user.|
|% Preferred connection cache hit rate|Percentage of hits in the preferred connection cache, compared to the total number of requests.|

### Investigating database connection failures
If you are experiencing significant instances where the server instance cannot establish a session with the database, monitor **# Open application connections** and **# Open tenant database connections**.

Each database has a limit on the number of connections/sessions that can be made to it. When the limit for the database is reached, new connections are denied. 

## Data and caching counters
These counters pertain to the data caching on the server instance.

|  Counter  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|-----------|-----------------------------------------------------------------------|
|\# Calculated fields cache total requests|Count of the total number of requests to the calculated fields cache. The calculated fields cache contains the results of [CALCFIELDS Function \(Record\)](CALCFIELDS-Function--Record-.md) calls.|
|% Calculated fields cache hit rate|Percentage of hits in the calculated fields cache, compared to the total requests to the calculated fields cache.|
|\# Command cache total requests|Count of the total number of requests to the command cache. The command cache contains the results of all SQL commands.|
|% Command cache hit rate|Percentage of hits in the command cache, compared to the total requests to the command cache.|
|\# Primary key cache total requests|Count of the total number of requests to the primary key cache. The primary key cache contains the results of requests to get a record by using its primary key.|
|% Primary key cache hit rate|Percentage of hits in the primary key cache, compared to the total requests to the primary key cache.|  
|\# Result set cache total requests|Count of the total number of requests to the result set cache. The result set cache contains result sets that are returned from SQL Server.|
|% Result set cache hit rate|Percentage of hits in the result set cache, compared to the total requests to the result set cache.|
|\# Rows in all temporary tables|Count of number of rows in all temporary tables.|

## Scheduled task counters
These pertain to tasks that are run by Task Scheduler. See [Task scheduler metrics](#TaskSchedulerMetrics).

|  Counter  |  [!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]  |
|-----------|-----------------------------------------------------------------------|
|# Available tasks|Remaining number of tasks that can potentially run simultaneously before the maximum number of tasks is reached. The value of this counter is the value the **Maximum # of tasks** counter minus the value of the **# Running tasks** counter.|
|# of task errors/sec|Number of errors per second that are caused by running tasks. The task are causing errors in C/AL or exceptions on the server instance. If the value is greater than zero for an extended period of time, this typically indicates a failing task that keeps getting rescheduled.|
|# Running tasks|Number of tasks that are currently running on the server instance. The  value is limited to the value of the **Maximum # of tasks** counter.|
|Average task execution time|The average time (in ticks) that tasks have taken to complete.  Task execution time is counted regardless of whether the task completed successfully or raised an error. <br /><br />There is no general rule for what the normal operations level is. To analyze this counter, look for large spikes to identify long-running tasks.<br /><br />**Note:** A tick is the smallest unit that the your system uses for time measurements, and it is typically determined by the operating system. For example, in Windows, a single tick represents one hundred nanoseconds, which means that there are 10,000 ticks in a millisecond. Tick durations can differ bewteen systems, so be aware of this fact when comparing absolute values across systems.|
|Maximum # of tasks|The maximum number of tasks that can run simultaneously. This value is defined by the **Maximum Concurrent Running** (TasksTaskSchedulerMaxConcurrentRunningTasks) setting in the server instance configuration. Therefore, this  value is constant until the server instance setting is changed and the instance is restarted. |
|Total # Pending tasks|The total number of tasks in the shared task list that are waiting to be picked up by server instances connected to this application database. The tasks counted are those that are ready and have been scheduled to run now or earlier and that are not currently running.|
|Total # Running tasks|Total number of tasks in the shared task list that are currently running by any server instance connected to this application database. |
|Time (ms) since the list of running tasks last had capacity for new tasks|The time (ms) since the list of running tasks last had capacity for new tasks.|

###  <a name="TaskSchedulerMetrics"></a>Task scheduler metrics
The task scheduler controls when certain operations or processes (tasks) are run. Tasks are run in a background session between the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance and database.  Every two seconds, the task scheduler performs the following operations : 
*   Reads the list of tasks from the database (shared with other server tasks) and find all tasks running or ready to run (candidate tasks)
*   Removes the completed tasks from the list of active tasks on this server instance
*   Keeps the running tasks in the list of active tasks, and adds new tasks as they they are ready, until the maximum number of tasks is met.
    *   New tasks are run using the specified user account. 
*   Updates all performance counters.

For more information about task scheduler, see [Task Scheduler](task-scheduler.md).

## See Also  
 [How to: Set up Performance Counters in Windows Performance Monitor](How-to--Set-up-Performance-Counters-in-Windows-Performance-Monitor.md)   
 [How to: Create a Data Collector Set From the Microsoft Dynamics NAV Template](How-to--Create-a-Data-Collector-Set-From-the-Microsoft-Dynamics-NAV-Template.md)   
 [Optimizing SQL Server Performance with Microsoft Dynamics NAV](Optimizing-SQL-Server-Performance-with-Microsoft-Dynamics-NAV.md)   
<!-- temporatily removed until we determine our support for this [Microsoft Dynamics NAV Management Pack for System Center Operations Manager](http://go.microsoft.com/fwlink/?LinkID=722863) -->
