---
title: "Troubleshooting: SQL Server Connection Problems"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e28202de-a9d4-44db-b5b1-a9be8674a53d
caps.latest.revision: 15
manager: edupont
---
# Troubleshooting: SQL Server Connection Problems
After installing and configuring [!INCLUDE[navnow](includes/navnow_md.md)] software, you may not be able to connect the [!INCLUDE[rtc](includes/rtc_md.md)] to [!INCLUDE[nav_server](includes/nav_server_md.md)]. In this case you see an error message like the following when you attempt to start the [!INCLUDE[rtc](includes/rtc_md.md)].  
  
 **The program could not create a connection to the server. Do you want to try again?**  
  
 This topic describes configuration changes that you can try to resolve SQL Server connection problems.  
  
## Enable Protocols in SQL Server Configuration Manager  
 SQL Server Configuration Manager is a tool for managing SQL Server services and network connectivity. You can use SQL Server Configuration Manager to enable and disable network protocols. For [!INCLUDE[navnow](includes/navnow_md.md)] to work correctly, the Named Pipes and TCP/IP protocols must be enabled for SQL Server.  
  
 Follow these steps to verify that these protocols are enabled or to enable them if they are currently disabled.  
  
#### To enable Named Pipes and TCP/IP in SQL Server  
  
1.  Start SQL Server Configuration Manager.  
  
2.  Expand the SQL Server Network Configuration node in the tree view, and then choose **Protocols for MSSQLSERVER**.  
  
3.  Under **Protocol Name** in the right pane, verify that **Named Pipes** and **TCP/IP** have the status **Enabled**.  
  
4.  If either protocol is not enabled, right-click the protocol, and then choose **Enable**.  
  
 After exiting SQL Server Configuration Manager, start the [!INCLUDE[rtc](includes/rtc_md.md)] again to see if the connection problem has been resolved.  
  
## Allowing SQL Server with Windows Firewall  
 If Windows Firewall is running on the computer running SQL Server, then you must explicitly specify the SQL Server executable file as an allowed exception before you can connect to the [!INCLUDE[navnow](includes/navnow_md.md)] database.  
  
#### To allow SQL Server with Windows Firewall  
  
1.  In Control Panel, open **Windows Firewall**, choose **Change settings**, and then click the **Exceptions** tab.  
  
2.  Choose **Add program**.  
  
3.  Choose **Browse**, and then browse to the location of the SQL Server executable file \(sqlservr.exe\). The default location on a computer running Windows Server 2008 R2 is:  
  
    ```  
    C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\MSSQL\Binn\sqlservr.exe  
    ```  
  
4.  Double-click the executable file to select it and to exit the **Browse** window, and then choose **OK** to close the **Add a Program** window.  
  
5.  Choose **OK** to close **Windows Firewall**.  
  
 After exiting SQL Server Configuration Manager, start the [!INCLUDE[rtc](includes/rtc_md.md)] again to see if the connection problem has been resolved.  
  
## Starting SQL Browser Service  
 When using a named database instance for [!INCLUDE[navnow](includes/navnow_md.md)], and [!INCLUDE[nav_server](includes/nav_server_md.md)] and the SQL server are on separate computers, then SQL Browser Service must be running on the SQL Server. For more information, see [How to: Start SQL Browser Service](How-to--Start-SQL-Browser-Service.md).  
  
## See Also  
 [Configuring Microsoft SQL Server](Configuring-Microsoft-SQL-Server.md)   
 [Walkthrough: Installing the Three Tiers on Three Computers](Walkthrough--Installing-the-Three-Tiers-on-Three-Computers.md)   
 [Installation Considerations for Microsoft SQL Server](Installation-Considerations-for-Microsoft-SQL-Server.md)