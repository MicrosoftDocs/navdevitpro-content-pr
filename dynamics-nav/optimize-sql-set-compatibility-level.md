---
title: "Enable query optimizer features in a Dynamics NAV Database by setting the compatibility level"
ms.custom: na
ms.date: 05/07/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Enabling Query Optimizer Features in a [!INCLUDE[navnow_md](includes/navnow_md.md)] Database
If your [!INCLUDE[navnow_md](includes/navnow_md.md)] database is running on Azure SQL Database or SQL Server 2016 or later, set the database's compatibility level to match the database server. This will equip the database with the latest optimizer features of Azure SQL Database or SQL Server. This is particularly relevant for demonstration databases that are installed by using the [!INCLUDE[navnow_md](includes/navnow_md.md)] Setup because the default compatibility level matches SQL Server 2014. 

## To change the compatibility level
You change the compatibility level of the database by using SQL Server Management Studio. There are two ways to do this:

- Open the database properties, select the **Options** page, and then set the **Compatibility Level:**. 
- Run the following query:

    ```
    ALTER DATABASE <database name> SET COMPATIBILITY_LEVEL = 140 | 130 
    ```
 
    where:
   -    `<database name>` is the name of the database to be modified.
   -    `140` sets the database to be compatible with SQL Server 2017
   -    `130` sets the database to be compatible with SQL Server 2016 and Azure SQL Database

   For more information, see [ALTER DATABASE (Transact-SQL) Compatibility Level](https://docs.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).  

## See Also  
[Optimizing SQL Server Performance](Optimizing-SQL-Server-Performance-with-Microsoft-Dynamics-NAV.md)    
[Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
[Microsoft SQL Server documentation](http://go.microsoft.com/fwlink/?LinkId=253107)
a