---
title:"How to: Create Databases"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 2263326d-f1b1-459f-9c82-a94be9eaef6a
caps.latest.revision: 9
manager: edupont
---
# How to: Create Databases
You can create new [!INCLUDE[navnow](includes/navnow_md.md)] databases in the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] and by using the [T:Microsoft.Dynamics.Nav.Management.Cmdlets.New\-NAVDatabase](assetId:///T:Microsoft.Dynamics.Nav.Management.Cmdlets.New-NAVDatabase)[!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlet.  
  
 When you create a database you must specify the SQL Server instance for the database and the authentication type.  
  
### To create a database  
  
1.  In the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], on the **File** menu, choose **Database**, and then choose **New**.  
  
2.  In the **Server Name** field, enter the name of the SQL Server instance. You can choose the up arrow to select the server from a list of available servers or you can enter the server name manually.  
  
3.  In the **Authentication** field, select the type of authentication that you require. Choose the drop\-down arrow to select **Database Server Authentication** or **Windows Authentication**.  
  
    -   If you select **Database Server Authentication**, then authentication is performed by the SQL Server instance that you have selected.  
  
    -   If you select **Windows Authentication**, then authentication is performed by the Windows domain controller.  
  
4.  In the **User ID** field, enter your User ID if you have selected **Database Server Authentication**.  
  
5.  In the **Password** field, enter your password if you have selected **Database Server Authentication**.  
  
6.  To set the network type to be used when connecting to the server, choose the **Advanced** tab and select the net type from the drop down list box in the **Net Type** field. However, it is not usually necessary to change the network type from the default setting. The **Default** net type setting allows \($ P\_1 Product Name $\) to connect to a server using the default client network type assigned by SQL Server. You can change the net type with the Client Network Utility, which is part of the SQL Server Client Utilities, if they have been installed on the client computer.  
  
7.  Choose **OK** to connect to the server and open the **\($ S\_2338 New Database $\)** window.  
  
     In the [\($ S\_2338 New Database $\)](-$-S_2338-New-Database-$-.md) window, enter the information about the database that you want to create. The window contains the same tabs as the **\($ S\_2339 Alter Database $\)** window. The tabs are the following:  
  
    -   [Altering Databases \- General Tab](Altering-Databases---General-Tab.md)  
  
    -   [Altering Databases \- Database Files Tab](Altering-Databases---Database-Files-Tab.md)  
  
    -   [Altering Databases \- Transaction Log Files Tab](Altering-Databases---Transaction-Log-Files-Tab.md)  
  
    -   [Altering Databases \- Collation Tab](Altering-Databases---Collation-Tab.md)  
  
    -   [Altering Databases \- Options Tab](Altering-Databases---Options-Tab.md)  
  
    -   [Altering Databases \- Integration Tab](Altering-Databases---Integration-Tab.md)  
  
    -   [Altering Databases \- Advanced Tab](Altering-Databases---Advanced-Tab.md)  
  
 Now that you have created a new database, you must configure your [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to access the database and then restart the service. For more information, see [How to: Configure a Microsoft Dynamics NAV Server Instance](../Topic/How%20to:%20Configure%20a%20Microsoft%20Dynamics%20NAV%20Server%20Instance.md). Next, you must synchronize the table schema. For more information, see [Synchronizing Table Schemas](Synchronizing-Table-Schemas.md).  
  
> [!WARNING]  
>  You can always enlarge a database later on, but you cannot make it smaller.  
  
 After you have created the database, you can enter program objects and company data. Before you can create company data, you must import some basic data from another [!INCLUDE[navnow](includes/navnow_md.md)] database. The imported data must at least include **Data Common to All Companies** and **Application Objects**. For more information, see [Exporting and Importing Companies and Other Data](Exporting-and-Importing-Companies-and-Other-Data.md).  
  
## See Also  
 [How to: Create Companies](../Topic/How%20to:%20Create%20Companies.md)   
 [How to: Select the Network Type of the Database](../Topic/How%20to:%20Select%20the%20Network%20Type%20of%20the%20Database.md)   
 [How to: Delete Databases](../Topic/How%20to:%20Delete%20Databases.md)   
 [How to: Export and Import Companies and Other Data in Clients](../Topic/How%20to:%20Export%20and%20Import%20Companies%20and%20Other%20Data%20in%20Clients.md)