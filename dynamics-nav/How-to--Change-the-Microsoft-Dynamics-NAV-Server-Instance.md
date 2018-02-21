---
title: Change the Server Instance
description: Change the currently used Dynamics NAV Server instance by specifying the server instance from a list, or the field in the Database options window. 
ms.custom: na
ms.date: 11/21/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: c06ea848-bc0d-493d-99b8-9db10a684ecb
caps.latest.revision: 5
manager: edupont
---
# How to Change the Microsoft Dynamics NAV Server Instance
In some cases, you may want to change the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that is being used. For example:  

-   When you select an object in Object Designer and then choose the **Run** button, you may want the selected object to run on a different [!INCLUDE[nav_server](includes/nav_server_md.md)] instance that the one that is currently specified.  

-   You may want to debug a session that is connected to a different [!INCLUDE[nav_server](includes/nav_server_md.md)] than the one that is currently specified.  

### To change the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance by selecting from a list  

1.  In the development environment, on the **File** menu, choose **Database**, and then choose **Information**.  

    > [!TIP]  
    >  If the **Information** menu item is not available, then you must first open a database.  

2.  In the **Database Information** window, in the **Server Instance** field, choose the drop-down arrow to open the **Available Server Instances** window.  

3.  Select a server instance, and then choose the **OK** button.  

    > [!NOTE]  
    >  The instance that you select is also displayed in the [Options](uiref/-$-S_2355-Options-$-.md) window.  

### To change the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance by specifying the field in the Database Options window  

1.  In the development environment, on the **Tools** menu, choose **Options**.  

2.  In the **Options** window, in the **Server Instance** field, enter the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. The format is \<*servername*>:\<*port*>/\<*ServerInstance*>.  

    > [!NOTE]  
    >  The value that you set is also displayed in the [Database Information](uiref/-$-S_2349-Database-Information-$-.md) window.  

## See Also  
 [Running Objects from the Development Environment](Running-Objects-from-the-Development-Environment.md)   
 [Debugging](Debugging.md)   
 [Managing Microsoft Dynamics NAV Server Instances](Managing-Microsoft-Dynamics-NAV-Server-Instances.md)
