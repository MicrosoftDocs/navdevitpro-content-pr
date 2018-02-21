---
title: "How to use SQL Server Query Store to troubleshoot query performance in Dynamics NAV"
author: KennieNP
ms.custom: na
ms.date: 02/20/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e28202de-a9d4-44db-b5b1-a9be8674a53d
caps.latest.revision: 15
ms.author: kepontop
manager: edupont
---
# Troubleshooting: Using Query Store to Monitor Query Performance in Dynamics NAV

## What is SQL Server Query Store?
The SQL Server Query Store feature provides you with insight on database query plan choice and performance. It simplifies database performance troubleshooting by helping you quickly find performance differences caused by query plan changes. Query Store automatically captures a history of queries, plans, and runtime statistics, and retains these for your review.

## Where is SQL Server Query Store available?
SQL Server Query Store is available in SQL Server (starting with SQL Server 2016) and in Azure SQL Database.

## What are the common scenarios for using the Query Store feature?
Query Store keeps a history of compilation and runtime metrics throughout query execution. With this information, you can get some answers on questions about your workload, such as:
-   What was the last *n* queries executed on the database?
-   What were the number of executions for each query?
-   Which queries had the longest average execution time within last hour?
-   Which queries had the biggest average physical IO reads in last 24 hours, with corresponding average row count and execution count?

## Do you want to read more?
Please visit the SQL Server documentation for more information on setup, configuration and usage of Query Store:

[Monitoring Performance By Using the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store)

[Operating the Query Store in Azure SQL Database](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-operate-query-store)

## See Also
[Configuring Microsoft SQL Server](configuring-microsoft-sql-server.md)  
[Installation Considerations for Microsoft SQL Server](Installation-Considerations-for-Microsoft-SQL-Server.md)  
