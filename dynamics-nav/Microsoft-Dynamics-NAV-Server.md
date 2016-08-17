---
title: "Microsoft Dynamics NAV Server"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 169cdd88-5449-42e8-8c79-90af2f6ca484
caps.latest.revision: 25
manager: terryaus
---
# Microsoft Dynamics NAV Server
[!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] is a .NET\-based Windows Service application that manages communications between [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] clients and [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] databases in SQL Server. It uses the Windows Communication Framework \(WCF\) as its communication protocol.  
  
 [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] uses an ADO.NET interface, which is a managed data access layer that supports SQL Server connection pooling. This simplifies deployment of the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] three\-tier architecture for deployments where the three tiers are installed on separate computers. Specifically, administrators are not required to manually create service principal names \(SPNs\) or to set up delegation when the client, [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)], and SQL Server are on separate computers. For more details, see [Data Access](../dynamics-nav/Data-Access.md).  
  
 [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] supports a range of different client types. This includes the [!INCLUDE[nav_windows](../dynamics-nav/includes/nav_windows_md.md)] and the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] and two types of web services. For more information, see [Client Types](../dynamics-nav/Client-Types.md). You administer [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] using either [!INCLUDE[nav_admin](../dynamics-nav/includes/nav_admin_md.md)] or Windows PowerShell cmdlets. For more information, see  [Microsoft Dynamics NAV Server Administration Tool](../dynamics-nav/Microsoft-Dynamics-NAV-Server-Administration-Tool.md) or [Microsoft Dynamics NAV Windows PowerShell Cmdlets](../dynamics-nav/Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md).  
  
 [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] is installed when you select either the [Server Option](../dynamics-nav/Server-Option.md) or the [Developer Option](../dynamics-nav/Developer-Option.md) in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Setup.  
  
> [!NOTE]  
>  Installing [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] on encrypted drives is not supported. You may experience issues if the server runs as a user that does not have access rights to the encrypted files.  
  
> [!NOTE]  
>  You can install [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] only on 64\-bit operating systems.  
  
## See Also  
 [Server Option](../dynamics-nav/Server-Option.md)   
 [System Requirements for Microsoft Dynamics NAV 2016](../dynamics-nav/System-Requirements-for-Microsoft-Dynamics-NAV-2016.md)   
 [Configuring Microsoft Dynamics NAV Server](../dynamics-nav/Configuring-Microsoft-Dynamics-NAV-Server.md)   
 [Enhancing Microsoft Dynamics NAV Server Security](../dynamics-nav/Enhancing-Microsoft-Dynamics-NAV-Server-Security.md)