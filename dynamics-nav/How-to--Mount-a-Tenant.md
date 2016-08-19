---
title: "How to: Mount a Tenant"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 81caea90-e090-412a-997a-25b9e78dab96
caps.latest.revision: 4
---
# How to: Mount a Tenant
This topic describes how to mount a tenant database on a [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance in a multitenant [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] deployment. To mount a tenant database, you use the [T:Microsoft.Dynamics.Nav.Management.Cmdlets.Mount\-NAVTenant](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.Mount-NAVTenant) cmdlet of the [!INCLUDE[nav_shell](../dynamics-nav/includes/nav_shell_md.md)].  
  
> [!TIP]  
>  You can also mount a tenant by using the [!INCLUDE[nav_admin](../dynamics-nav/includes/nav_admin_md.md)]. For more information, see [How to: Mount or Dismount a Tenant on a Microsoft Dynamics Server Instance](../Topic/How%20to:%20Mount%20or%20Dismount%20a%20Tenant%20on%20a%20Microsoft%20Dynamics%20Server%20Instance.md).  
  
### To mount a tenant database on a [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instances  
  
1.  On the computer that is running the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)], run **[!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Administration Shell** as an Administrator.  
  
    1.  Choose **Start**, in the **Search** box, type **[!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Administration Shell**.  
  
    2.  Right\-click the related link, and then choose **Run as Administrator**.  
  
2.  At the command prompt, type the following command:  
  
    ```  
    Mount-NAVTenant [-ServerInstance] <NAVServerInstance> -DatabaseName <NAVDatabase> -DatabaseServer <MyDatabaseServer  
    ```  
  
     Change the following parameter values.  
  
    |Parameter|[!INCLUDE[bp_tabledescription](../dynamics-nav/includes/bp_tabledescription_md.md)]|  
    |---------------|---------------------------------------|  
    |*\<NAVServerInstance\>*|Specifies the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance that you want to mount the tenant against, such as [!INCLUDE[nav_server_instance](../dynamics-nav/includes/nav_server_instance_md.md)].|  
    |*\<NAVDatabase\>*|Specifies the name of the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database that you want to mount against the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance, such as `'Demo Database NAV (7-1)'`.|  
    |*\<MyDatabaseServer\>*|Specifies the name of the database server that hosts the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] database that you want to mount against the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance.|  
  
    > [!NOTE]  
    >  The command that is shown includes only a subset of all the parameters of the Mount\-NavTenant cmdlet. For more information about the syntax and parameters, see [T:Microsoft.Dynamics.Nav.Management.Cmdlets.Mount\-NAVTenant](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.Mount-NAVTenant) topic in the Administration Cmdlets for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] section of the Technical Reference.  
  
3.  Press Enter to run the cmdlet.  
  
     The tenant database is mounted on the [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance.  
  
## See Also  
 [Scaling the Microsoft Dynamics NAV Network Topology](../dynamics-nav/Scaling-the-Microsoft-Dynamics-NAV-Network-Topology.md)   
 [Multitenant Deployment Architecture](../dynamics-nav/Multitenant-Deployment-Architecture.md)   
 [Migrating to Multitenancy](../dynamics-nav/Migrating-to-Multitenancy.md)   
 [Deploying and Managing Microsoft Dynamics NAV on Microsoft Azure](../dynamics-nav/Deploying-and-Managing-Microsoft-Dynamics-NAV-on-Microsoft-Azure.md)   
 [How to: Add a Microsoft Dynamics NAV Web Server Instance](../Topic/How%20to:%20Add%20a%20Microsoft%20Dynamics%20NAV%20Web%20Server%20Instance.md)   
 [How to: Add a Microsoft Dynamics NAV Database](../Topic/How%20to:%20Add%20a%20Microsoft%20Dynamics%20NAV%20Database.md)   
 [How to: Add a Microsoft Dynamics NAV Server Instance](../Topic/How%20to:%20Add%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md)