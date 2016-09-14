---
title: "How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: dad134e4-d110-4eba-97af-3173471d6d50
caps.latest.revision: 5
manager: edupont
---
# How to: Run the Sync-NAVTenant Cmdlet to Synchronize the Tenant Database with the Application Database
This topic describes how to run the [T:Microsoft.Dynamics.Nav.Management.Cmdlets.Sync-NAVTenant](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.Sync-NAVTenant) cmdlet to synchronize the business data \(tenant\) database schema with the application database. You can use this cmdlet in a multitenant and non-multitenant deployment environment.  
  
### To run the Sync-NAVTenant cmdlet  
  
1.  On the computer that is running the [!INCLUDE[nav_server](includes/nav_server_md.md)], run **[!INCLUDE[navnow](includes/navnow_md.md)] Administration Shell** as an Administrator.  
  
    1.  Choose **Start**, in the **Search** box, type **[!INCLUDE[navnow](includes/navnow_md.md)] Administration Shell**.  
  
    2.  Right-click the related link, and then choose **Run as Administrator**.  
  
2.  At the command prompt, type one of the following commands:  
  
    -   If the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance is not configured to be a multitenant instance:  
  
        ```  
        Sync-NAVTenant –ServerInstance <ServerInstanceName>  
        ```  
  
    -   If the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance is configured to be a multitenant instance:  
  
        ```  
        Sync-NAVTenant –ServerInstance <ServerInstanceName> -Tenant <TenantId>  
        ```  
  
     Change the following parameter values.  
  
    |Parameter|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
    |---------------|---------------------------------------|  
    |*\<NAVServerInstance>*|Specifies the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.|  
    |*\<TenantId>*|Specifies the name of the tenant database.|  
  
3.  Press Enter to run the cmdlet.  
  
## See Also  
 [Scaling the Microsoft Dynamics NAV Network Topology](Scaling-the-Microsoft-Dynamics-NAV-Network-Topology.md)   
 [Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md)   
 [Migrating to Multitenancy](Migrating-to-Multitenancy.md)   
 [Deploying and Managing Microsoft Dynamics NAV on Microsoft Azure](Deploying-and-Managing-Microsoft-Dynamics-NAV-on-Microsoft-Azure.md)   
 [How to: Add a Microsoft Dynamics NAV Web Server Instance](How-to--Add-a-Microsoft-Dynamics-NAV-Web-Server-Instance.md)   
 [How to: Add a Microsoft Dynamics NAV Database](How-to--Add-a-Microsoft-Dynamics-NAV-Database.md)   
 [How to: Add a Microsoft Dynamics NAV Server Instance](How-to--Add-a-Microsoft-Dynamics-NAV-Server-Instance.md)