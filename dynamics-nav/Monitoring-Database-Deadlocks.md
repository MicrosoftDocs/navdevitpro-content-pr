---
title: "Monitoring SQL Database Deadlocks"
ms.custom: na
ms.date: 09/19/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
---
# Monitoring SQL Database Deadlocks

You can set up the system to log deadlocks that occur in the SQL database. The deadlocks are recorded in the Windows Event Log of computer running [!INCLUDE[nav_server](includes/nav_server_md.md)]. The log entries provide information about the C/AL code that was run when the deadlock occurred, along with the deadlock report from SQL Server. This information can help you identify and resolve problem areas in the application design.

## About Deadlocks

Deadlocks can prevent users from completing tasks in the [!INCLUDE[navnow](includes/navnow_md.md)] client. A deadlock occurs when two or more processes or transactions block each other from continuing because each has locked a database resource that the other transaction needs. SQL Server handles deadlocks by terminating and rolling back transactions that were started after the first transaction.

For general information about deadlocks, see [Detecting and Ending Deadlocks](https://aka.ms/detectingendingdeadlocks).

## Setting Up Deadlock Logging

Setting up deadlock logging requires you to configure the SQL Server instance and the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.

> [!NOTE]
> If you installed the [!INCLUDE[nav_server](includes/nav_server_md.md)] and database components by using the **Install Demo** option in the [!INCLUDE[nav_setup](includes/nav_setup_md.md)], then deadlock logging is set up by default.

### Configure the SQL Server instance

To configure the SQL Server instance to log deadlocks, you must assign specific permissions to the database login for the service account that is used on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. You can do this using SQL Server Management Studio.

In SQL Server Management Studio, connect to the SQL server instance for [!INCLUDE[navnow](includes/navnow_md.md)], and then grant the following permissions:
-   On the database level, grant the login the **View database state**<!--**View server state**--> permission.
-   On the SQL server instance level, grant the login both **Alter any event session** and **View server state** permissions.

For detailed steps on how to do this, see [Giving the account necessary database privileges in SQL Server](Provisioning-the-Microsoft-Dynamics-NAV-Server-Account.md#dbo).

To verify the setup, connect from a client, like the Web client or Windows client. When the session is established with the database, a session for monitoring the [!INCLUDE[navnow](includes/navnow_md.md)] database appears under  **Management** > **Extended Events** > **Sessions**.

#### Configure where to store deadlock events

By default, SQL Server uses an in-memory data structure called a *ring_buffer target* to store deadlock events. You also have the option to store the events to a file on the server, called an *event_file target*. When [!INCLUDE[nav_server](includes/nav_server_md.md)] is notified about the deadlock, it reads data from the target that you specify. An important difference is that the ring_buffer target has a storage size limitation of 5MB, while the event_file target provides a much greater storage capacity. Using the event_file target can eliminate potential overloads in high volume situations. So, if your setup has a high volume of database traffic, you might have to change the SQL Server to write deadlock events to an event_file target as described the the steps that follow. If you want to use the default ring_buffer target, then no further action is required.

> [!NOTE]
> The event_file target is only supported in [!INCLUDE[nav2018_md](includes/nav2018_md.md)] Cumulative Update 13 and later, and is not supported in [!INCLUDE[nav2017](includes/nav2017.md)].

1. Modify the deadlock monitoring session to use a file-based target (known as an *event_file target*).

    The event_file target writes event session output from a buffer to a disk file that you specify. There are two ways to do this:
    - From Object Explorer, open the session's **Properties**, and then on the **Data Storage** page, add an **event_file** type target.  
    - Using a query, run the [ALTER EVENT SESSION](https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2017) transact-sql statement. For example:
      ```
      ALTER EVENT SESSION [Demo Database NAV_deadlock_monitor]
          ON SERVER
	        ADD Target package0.event_file
          (
            SET filename=N'C:\logging\mydeadlocks.xel',max_file_size=(10240)
          )
      ```
    For more information see [Alter an Extended Events Session](https://docs.microsoft.com/en-us/sql/relational-databases/extended-events/alter-an-extended-events-session?view=sql-server-2017) and [Targets for Extended Events in SQL Server](https://docs.microsoft.com/en-us/sql/relational-databases/extended-events/targets-for-extended-events-in-sql-server?view=sql-server-2017#eventfile-target).
    
2. Create a view in the [!INCLUDE[navnow](includes/navnow_md.md)] database that uses the new event_file target. 

    You can create this view based on the default `dbo.deadlock_report_ring_buffer_view` view. To use the event_file target, you change `xt.target_name = N'ring_buffer'` to `xt.target_name = N'event_file'`. For example:
    ```
    USE [Demo Database NAV]
    GO

    SET ANSI_NULLS ON
    GO

    SET QUOTED_IDENTIFIER ON
    GO

    CREATE VIEW [dbo].[deadlock_report_event_file_view] AS
        SELECT target_data AS event_raw_data
        FROM sys.dm_xe_session_targets AS xt INNER JOIN sys.dm_xe_sessions AS xs
        ON xs.address = xt.event_session_address
        WHERE xs.name = N'Demo Database NAV_deadlock_monitor' AND xt.target_name = N'event_file'
    GO
    ```
3. Change the [!INCLUDE[navnow](includes/navnow_md.md)] database synonym `dbo.syn_deadlock_event_view` to point to the deadlock report event file view that you created.

    This synonym is used by the [!INCLUDE[nav_server](includes/nav_server_md.md)] to query the deadlock data. To alter a synonym, you first drop it, and then create a new synonym that has the same name. For example:
    ```
    DROP SYNONYM [dbo].[syn_deadlock_event_view]
    GO
    
    CREATE SYNONYM [dbo].[syn_deadlock_event_view] FOR [dbo].[deadlock_report_event_file_view]
    GO
    ```

### Configure the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance

To log deadlocks, you must enable deadlock logging on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. You can enable deadlock logging by using the [!INCLUDE[nav_admin](includes/nav_admin_md.md)] or the Set-NAVServerConfiguration cmdlet in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)].

-   To enable deadlock logging by using the [!INCLUDE[nav_admin](includes/nav_admin_md.md)], open the server instance for editing, and then select the **Enable Deadlock Monitoring** check box in the **Database** section.

    For more information about how to use the [!INCLUDE[nav_admin](includes/nav_admin_md.md)], see [Microsoft Dynamics NAV Server Administration Tool](Microsoft-Dynamics-NAV-Server-Administration-Tool.md).

-   To enable logging by using the Set-NAVServerConfiguration cmdlet, include the *keyname EnableDeadlockMonitoring keyvalue true* parameters in the command, such as:

    ```
    Set-NAVServerConfiguration -ServerInstance DynamicsNAV -KeyName EnableDeadlockMonitoring -KeyValue true
    ```
    For more information about how to use the [!INCLUDE[nav_shell](includes/nav_shell_md.md)], see [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md) and [Set-NAVServerConfiguration Cmdlet](https://go.microsoft.com/fwlink/?linkid=401394).

## Viewing Deadlocks in the Windows Event Log

Similar to other errors and events in [!INCLUDE[navnow](includes/navnow_md.md)], you can monitor deadlocks by using Event Viewer on the computer running [!INCLUDE[nav_server](includes/nav_server_md.md)]. Deadlocks are recorded as warnings in the [!INCLUDE[nav_server](includes/nav_server_md.md)] **Admin** channel log in the **Applications and Services Logs**. For general information about how to view the [!INCLUDE[nav_server](includes/nav_server_md.md)] logs, see [Monitoring Dynamics NAV Server Events Using Event Viewer](Monitoring-Microsoft-Dynamics-NAV-Server-Events-in-the-Windows-Event-Log.md).

### Deadlock event overview

Deadlock event log entries have the event ID 705 and task category 33 (TelemetryData). The following table describes some of important information that is included in deadlock log entry:

|  Information |  Description  |
|--------------|---------------|
|serverInstanceName|Specifies the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance on which the event occurred.|
|user|Specifies the [!INCLUDE[navnow](includes/navnow_md.md)] user account that ran the transaction that caused the event.|
|AL ObjectType|Specifies the [!INCLUDE[navnow](includes/navnow_md.md)] object in C/AL that ran the transaction, such as a page or report.|
|AL ObjectNumber|Specifies the ID of the object that was run.|
|AL ScopeName|Specifies the C/AL function that ran the transaction that caused the event.|
|SQL Server deadlock XML report|Includes the deadlock report that was recieved from SQL Server. For more information, see [Analyze Deadlocks](https://aka.ms/analyzedeadlocks).|

>[!Note]
> The system cannot record information about C/AL code that was executed on a different  [!INCLUDE[nav_server](includes/nav_server_md.md)]. Therefore, the three attributes *AL ObjectType*, *AL ObjectNumber* and *AL ScopeName* might be empty in a given event log entry.

### View a graphical representation of the deadlock event

To view a graphical representation of the deadlock, perform the following steps:
1.  Open the deadlock event in Event Viewer.
2.  On the General tab, go to the SQL Server deadlock xml report section, and then copy the text in the deadlock tag (including the start and end tag) to a text editor such as Notepad or Visual Studio Code.
3.  Save the file as a .xdl type.
4.  Open the file in SQL Server Management Studio.

### Filter on deadlock events

All deadlock events have the trace tag **00000DI**. If you only want to see deadlocks events in the log, you can use this tag in an XML path filter on the log, as shown in the following example:

```
<QueryList>
  <Query Id="0" Path="Microsoft-DynamicsNAV-Server/Admin">
    <Select Path="Microsoft-DynamicsNAV-Server/Admin">
                 *[EventData[Data[@Name='tag'] and (Data='00000DI')]]
               </Select>
  </Query>
</QueryList>
```
For more information about XML filtering, see [Advanced XML filtering in the Windows Event Viewer](https://aka.ms/advancedxmlfilteringeventviewer).

##  See Also
[Monitoring Microsoft Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md)  
[Monitoring SQL Database Locks](Monitoring-Database-Locks.md)  
[Configuring Microsoft Dynamics NAV Server](Monitoring-Microsoft-Dynamics-NAV-Server.md)  
[Use SQL Server Management Studio](https://aka.ms/usesqlservermanagementstudio)
