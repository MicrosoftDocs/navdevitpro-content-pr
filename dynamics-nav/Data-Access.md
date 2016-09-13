---
title: "Data Access"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: fd5a62ed-50c7-49ad-9610-f299e1961725
caps.latest.revision: 19
manager: edupont
---
# Data Access
The SQL Server interface from [!INCLUDE[nav_server](includes/nav_server_md.md)] uses ADO.NET instead of ODBC, which was used in [!INCLUDE[nav2009](includes/nav2009_md.md)] and earlier. The advantages of the new access layer are described in the following sections.  
  
## Simplified Deployment  
 The new ADO.NET interface is a managed data access layer that supports SQL Server connection pooling, which can dramatically decrease memory consumption by [!INCLUDE[nav_server](includes/nav_server_md.md)]. SQL Server connection pooling also simplifies deployment of the [!INCLUDE[navnow](includes/navnow_md.md)] three-tier architecture for deployments where the three tiers are installed on separate computers. Specifically, administrators are no longer required to manually create SPNs or to set up delegation when the client, [!INCLUDE[nav_server](includes/nav_server_md.md)], and SQL Server are on separate computers. For more information, see [Walkthrough: Installing the Three Tiers on Three Computers](Walkthrough:%20Installing%20the%20Three%20Tiers%20on%20Three%20Computers.md).  
  
## Collation  
 SQL Server 2008 is full aligned with the collations in Windows Server 2008. If you upgrade to [!INCLUDE[navnow](includes/navnow_md.md)] from [!INCLUDE[nav_2009_long](includes/nav_2009_long_md.md)], the step to convert the database includes upgrading the database to Windows collation. The collation changes provide users with the most up-to-date and linguistically accurate cultural sorting conventions. For more information, see [Collation and Unicode Support](http://go.microsoft.com/fwlink/?LinkID=247971).  
  
## Decreased Resource Consumption  
 There is no longer a one-to-one correlation between the number of client connections and the number of SQL Server connections. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], each SQL Server connection could consume up to 40 MB of memory. Additionally, memory allocation is now in managed memory, which is generally more efficient than unmanaged memory.  
  
 In [!INCLUDE[navnow](includes/navnow_md.md)], the data cache is shared by all users who are connected to the same [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. This means that after one user has read a record, a second user who reads the same record gets it from the cache. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], the data cache was isolated for each user.  
  
## Caching  
 [!INCLUDE[navnowlong](includes/navnowlong_md.md)] uses an improved cache system. The following functions use the cache system:  
  
-   GET  
  
-   FIND  
  
-   FINDFIRST  
  
-   FINDLAST  
  
-   FINDSET  
  
-   COUNT  
  
-   ISEMPTY  
  
-   CALCFIELDS  
  
 There are two types of caches:  
  
-   Global cache – for all users connected to a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  
  
-   Private cache – per user, per company, in a transactional scope. Data in a private cache for a given table and company are flushed when a transaction ends.  
  
 The cache that is used is determined by the lock state of a table. If a table is not locked than the global cache is queried for data; otherwise, the private cache is queried.  
  
 Results from query objects are not cached.  
  
 For a call to any of the **FIND** functions, 1024 rows are cached. You can set the size of the cache by using the **Data Cache Size** setting in the [!INCLUDE[nav_server](includes/nav_server_md.md)] configuration file. The default size is 9, which approximates a cache size of 500 MB. If you increase this number by one, then the cache size doubles.  
  
 You can bypass the cache by using the [SELECTLATESTVERSION Function \(Database\)](SELECTLATESTVERSION-Function--Database-.md).  
  
 [!INCLUDE[navnow](includes/navnow_md.md)] synchronizes caching between [!INCLUDE[nav_server](includes/nav_server_md.md)] instances that are connected to the same database. By default, the synchronization occurs every 30 seconds.  
  
 You can set the cache synchronization interval by using the *CacheSynchronizationPeriod* parameter in the CustomSettings.config file. For more information, see [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md).  
  
## Performance  
 Records are retrieved using multiple active result sets \(MARS\). Functions such as NEXT, FIND\('-'\), FIND\('+'\), FIND\('>'\), and FIND\('\<'\) are generally faster with MARS than the server cursors that earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)] used.  
  
 SIFT indexes have also been improved. For example, COUNT and AVERAGE formulas can now use SIFT indexes. For more information, see [CALCSUMS Function \(Record\)](CALCSUMS-Function--Record-.md) and [CALCFIELDS Function \(Record\)](CALCFIELDS-Function--Record-.md). MIN and MAX formulas now use SQL Server MIN and MAX functions exclusively.  
  
 RecordIds and SQL Variant columns in a table no longer prevent the use of BULK insert inserts. For more information, see [Bulk Inserts](Bulk-Inserts.md).  
  
 In most cases, filtering on FlowFields issues a single SQL statement. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], filtering on FlowFields issued an SQL statement for each filtered FlowField and for each record in the table in order to calculate the filtered FlowFields. The exceptions in [!INCLUDE[navnow](includes/navnow_md.md)] in which filtering on FlowFields does not issue a single SQL statement are as follows:  
  
-   You use the ValueIsFilter option on a field and the field has a value. For more information about the ValueIsFilter option, see [How to: Create, View, and Edit a Calculation Formula](How-to--Create,%20View,%20and%20Edit%20a%20Calculation%20Formula.md).  
  
-   A second predicate is specified on a source field and the field that is used for the second predicate has a value. For example, when you specify the [CalcFormula Property](CalcFormula-Property.md) for a FlowField, you can specify table filters in the **Calculation Formula** window. If you specify two or more filters on the same source field, then filtering does not issue a single SQL statement.  
  
-   You specify **Validated** for the [SecurityFiltering Property](SecurityFiltering-Property.md) on a record. This value for the **SecurityFiltering** property means that each record that is part of the calculation must be verified for inclusion in the security filter.  
  
 In most cases, calling the FIND or NEXT functions after you have set the view to include only marked records issues a single SQL statement. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], calling FIND or NEXT functions that have marked records issued an SQL statement for each mark. There are some exceptions if many records are marked. For more information, see [MARKEDONLY Function \(Record\)](MARKEDONLY-Function--Record-.md).  
  
## See Also  
 [Changes in C-AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV](Changes-in-C-AL-Behavior-and-Support-from-Earlier-Versions-of-Microsoft-Dynamics-NAV.md)   
 [SumIndexField Technology \(SIFT\)](SumIndexField-Technology--SIFT-.md)   
 [Query Objects and Performance](Query-Objects-and-Performance.md)