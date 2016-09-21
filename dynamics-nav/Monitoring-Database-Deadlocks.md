---
title: "Monitoring SQL Database Deadlocks"
ms.custom: na
ms.date: 09/19/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
---
# Monitoring Database Deadlocks
A deadlock occurs when two or more processes or transactions block each other from continuing because each has locked a database resource that the other transaction needs. SQL Server handles deadlocks by terminating and rolling back transactions that were started after the first transaction.

You can set up [!INCLUDE[navnow](includes/navnow_md.md)] so that deadlocks which occur in the database are recorded in the Windows Event Log of computer running [!INCLUDE[nav_server](includes/nav_server_md.md)]. The log provides information about the deadlock, which can help you identify problem areas in the application design.

## Setting Up Deadlock Logging
Setting up deadlock logging requires you to configure the SQL Server instance and the [!INCLUDE[nav_server_instance](includes/nav_server_instance_md.md)].

In SQL Server
-   The database login account for the service account that is used on the [!INCLUDE[nav_server_instance](includes/nav_server_instance_md.md)] must

## In this section  

-   [Tools for Monitoring Performance Counters and Events](Tools-for-Monitoring-Performance-Counters-and-Events.md)  
-   [Monitoring Microsoft Dynamics NAV Server Using Performance Counters](Monitoring-Microsoft-Dynamics-NAV-Server-Using-Performance-Counters.md)  
-   [Monitoring Microsoft Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md)
-   [Monitoring Deadlocks in SQL Server Database](Monitoring-Deadlocks-in-SQL-Server-Database.md)
