---
title: "Optimizing SQL Server Performance with Microsoft Dynamics NAV"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e4c70172-b5bb-4649-a5cb-27fe0afd988c
caps.latest.revision: 3
author: jswymer
---
# Ensure Performance with Microsoft Dynamics NAV

If your [!INCLUDE[navnowlong](includes/navnowlong_md.md)] database is running on Azure SQL Database or SQL Server 2016 or later, you can optimize the database's performance by setting the its compatibility level to match the database server. This will equip the database with the latest optimization features of the database server. For exampl, this is particularly relevant for demonstration databases that are installed by using the [!INCLUDE[navnowlong](includes/navnowlong_md.md)] Setup or bacpak files provided by [!INCLUDE[navnowlong](includes/navnowlong_md.md)] because by default these databases have a compatibility level that matches SQL Server 2014. 

## To change the compatibility level
You change the compatibility level of the database by using SQL Server Management Studio. There are two ways to do this:

- Run the following query:

    ```
    ALTER DATABASE <database name> SET COMPATIBILITY_LEVEL = { 140 | 130 }
    ```
 
    where:
    SQL Server 2017 is 140
    Azure SQL Database is 130  
    
    SQL Server 2016 is 130


[Data Access](Data-Access.md)   

[Table Keys and Performance](Table-Keys-and-Performance.md)   

[Bulk Inserts](Bulk-Inserts.md)   

[C/AL Database Functions and Performance on SQL Server](C-AL-Database-Functions-and-Performance-on-SQL-Server.md)   

[Query Objects and Performance](Query-Objects-and-Performance.md)  
[Troubleshooting: Analyzing Long Running SQL Queries Involving FlowFields by Disabling SmartSQL](Troubleshooting-Queries-Involving-FlowFields-By-Disabling-SmartSQL.md)  

[Troubleshooting: Using Query Store to Monitor Query Performance in Dynamics NAV](troubleshooting-query-performance-using-query-store.md)

[Troubleshooting: Using the Event Log to Monitor Long Running SQL Queries in Dynamics NAV](troubleshooting-long-running-queries-using-event-log.md)

## See Also  
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
 [Microsoft SQL Server documentation](http://go.microsoft.com/fwlink/?LinkId=253107)
a