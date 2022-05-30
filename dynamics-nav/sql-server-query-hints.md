---
title: "Configuring Query Hints for Optimizing SQL Server Performance with Dynamics NAV"
description: Describes strategies that can be enforced by the SQL Server query processor to override any execution plan that the query optimizer might select for a query.
ms.custom: na
ms.date: 01/18/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
# Configuring Query Hints for Optimizing SQL Server Performance with Dynamics NAV

On its own, SQL Server query optimizer will try to select the best execution plan for queries. Most of the time, query optimizer makes the right choice. [Query hints](https://docs.microsoft.com/sql/t-sql/queries/hints-transact-sql-query?view=sql-server-2017 &preserve-view=true) are strategies that can be enforced by the SQL Server query processor to override any execution plan that the query optimizer might select for a query. The [!INCLUDE[server](includes/nav_server_md.md)] instance includes configuration settings that let you enable or disable the use of the following hints on queries in the database:

|  Hint  |  Description  | Used by default |
|--------|---------------|--|
|FORCE ORDER|Instructs the query optimizer to preserve the join order that is indicated by the query syntax.<|No|
|LOOP JOIN|Instructs the query optimizer to use LOOP JOIN for all join operations in the whole query.|No|
|OPTIMIZE FOR UNKNOWN|Instructs the query optimizer to use statistical data instead of the initial values for all local variables when the query is compiled and optimized, including parameters created with forced parameterization.<br /><br />If you clear the check box (`false`), the OPTIMIZE FOR UNKNOWN hint is used in queries.|Yes|

For more information about configuring the [!INCLUDE[server](includes/nav_server_md.md)] instance, see [Configuring Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md#Database).

> [!IMPORTANT]
> We recommend that you do not change the query hint settings from the default values unless you are certain that the change will better suit your scenario.

## See Also
  
[Optimizing SQL Server Performance with Business Central](optimizing-sql-server-performance-with-microsoft-dynamics-nav.md)  
[Installation Considerations for Microsoft SQL Server](installation-considerations-for-microsoft-sql-server.md)  
[Microsoft SQL Server documentation](https://go.microsoft.com/fwlink/?LinkId=253107)
