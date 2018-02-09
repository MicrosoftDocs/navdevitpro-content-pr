---
title: "How to: Synchronize the Tenant Database with the Application Database"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: dad134e4-d110-4eba-97af-3173471d6d50
caps.latest.revision: 5
manager: edupont
---
# How to: Synchronize the Tenant Database with the Application Database
This topic describes how to synchronize the business data \(tenant\) database schema with the application database in either a single tenant (non-multitenant) or multitenant deployment environment. You can synchronize the database from the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] or by using the Sync-NAVTenant cmdlet in the Dynamics NAV Administration Shell.

## Synchronize database from the development environment

1.  Open [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] as an administrator.

2.  On the **Tools** menu, choose **Sync. Schema For All Tables**, and then choose **With Validation** and follow the schema synchronization instructions.

## Synchronize database with the Sync-NAVTenant cmdlet  

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
        Sync-NAVTenant –ServerInstance ServerInstanceName -Tenant TenantId  
        ```  

     Change the following parameter values.  

     <table>
     <tr>
     <th>Parameter</th>
     <th>[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]</th>
     </tr>
     <tr>
     <td>NAVServerInstance</td>
     <td>Specifies the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.</td>
     </tr>
     <tr>
     <td>TenantId</td>
     <td>Specifies the ID of the tenant.</td>
     </tr>
     </table>

3.  Press Enter to run the cmdlet.  

## See Also  
[Synchronizing Table Schemas](Synchronizing-Table-Schemas.md)  
[Converting a Database.md](Converting-a-Database.md)  
[Upgrading the Database](Upgrading-the-Data.md)  
[Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md)   
