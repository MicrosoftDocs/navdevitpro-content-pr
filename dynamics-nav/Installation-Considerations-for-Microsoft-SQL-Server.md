---
title:"Installation Considerations for Microsoft SQL Server"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 0c1e0c2f-e8c1-412e-86a8-6a2ba944af24
caps.latest.revision: 31
manager: edupont
---
# Installation Considerations for Microsoft SQL Server
This topic describes the requirements for installing and configuring Microsoft SQL Server to work with [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
## SQL Server Components to Install  
 For a list of supported editions of SQL Server, see [Microsoft Dynamics NAV Database Components for SQL Server Requirements](System-Requirements-for-Microsoft-Dynamics-NAV-2016.md#SQLReq).  
  
### SQL Server Components  
 If you are installing SQL Server to use with [!INCLUDE[navnow](includes/navnow_md.md)], then install the following components:  
  
-   Database Engine Services  
  
-   Client Tools Connectivity  
  
-   Management Tools \- Complete  
  
## Setup Options for Microsoft SQL Server  
 When you are running Microsoft SQL Server Setup, you must provide additional information. Your responses can affect how you use SQL Server with [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
### Instance Configuration  
 If you plan on installing the [!INCLUDE[navnow](includes/navnow_md.md)] Demo database with [!INCLUDE[navnowlong](includes/navnowlong_md.md)], and you want [!INCLUDE[navnow](includes/navnow_md.md)] Setup to use an already installed version of SQL Server \(and not to install SQL Server 2012 Express\) you must create a SQL Server instance named **NAVDEMO** in SQL Server before you install [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. Otherwise, [!INCLUDE[navnow](includes/navnow_md.md)] Setup will install SQL Server 2012 Express automatically, even if there is a valid version of SQL Server already on the computer. If you do not plan to install the Demo database, or if you have no objection to using SQL Server 2012 Express, you are free to use the **default instance** and **Instance ID** on the **Instance Configuration** page, or to specify any instance name.  
  
### Server Configuration  
 We recommend that you use a dedicated domain user account that you create specifically for your [!INCLUDE[nav_server](includes/nav_server_md.md)] instances and for your [!INCLUDE[navnow](includes/navnow_md.md)] instance on SQL Server, instead of a Local System account or the Network Service account.  
  
## Data Encryption Between [!INCLUDE[nav_server](includes/nav_server_md.md)] and SQL Server  
 When SQL Server and [!INCLUDE[nav_server](includes/nav_server_md.md)] are running on different computers, you can make this data channel more secure by encrypting the connection with IPSec. \(Other encryption options are not supported.\) For information on how to do this, see [Encrypting Connections to SQL Server](http://go.microsoft.com/fwlink/?LinkId=147732), which is part of SQL Server 2008 Books Online in MSDN library.  
  
## Using Microsoft Azure SQL Database  
 You can deploy a [!INCLUDE[navnow](includes/navnow_md.md)] database to Azure SQL Database. Azure SQL Database is a cloud service that provides data storage as a part of the Azure Services Platform.  
  
 To optimize performance, we recommend that the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that connects to the database is also deployed on a virtual machine in Azure. Additionally, the virtual machine and SQL Database must be in the same Azure region.  
  
 For development and maintenance work on [!INCLUDE[navnow](includes/navnow_md.md)] applications, if the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] is installed on the same virtual machine in Azure as the [!INCLUDE[nav_server](includes/nav_server_md.md)], then you can connect to the Azure SQL database from the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)].  
  
 For more information, see [How to: Deploy a Microsoft Dynamics NAV Database to Azure SQL Database](../Topic/How%20to:%20Deploy%20a%20Microsoft%20Dynamics%20NAV%20Database%20to%20Azure%20SQL%20Database.md).  
  
## See Also  
 [Data Access](Data-Access.md)   
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
 [Troubleshooting: SQL Server Connection Problems](../Topic/Troubleshooting:%20SQL%20Server%20Connection%20Problems.md)   
 [Deployment](Deployment.md)