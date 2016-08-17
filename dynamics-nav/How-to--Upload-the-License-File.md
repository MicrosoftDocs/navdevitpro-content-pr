---
title: "How to: Upload the License File"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9a36eb3e-521e-4684-9ebe-f4ab8fc1a5fd
caps.latest.revision: 40
manager: terryaus
---
# How to: Upload the License File
After an administrator or a Microsoft Certified Partner initially installs [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)], the next step is to upload the license file that is supplied by Microsoft.  
  
 To save the license file, you must have the Per Database license granule \(2020\) in your license. You must also have the necessary roles and permissions in SQL Server. See [Setting Database Owner and Security Administration Permissions](../dynamics-nav/Setting-Database-Owner-and-Security-Administration-Permissions.md).  
  
> [!NOTE]  
>  Uploading the license file is typically something you do once for each database installation, not once for each client installation. If you need to upload a license for a specific database, see [Uploading a License File for a Specific Database](../Topic/How%20to:%20Upload%20the%20License%20File.md#UploadtoDatabase).  
  
 Initially, [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] uses CRONUS.flf, which is the demonstration license file. All license files that are not demonstration license files are named FIN.flf. The demonstration license file has been given a different name so that it cannot be mistakenly overwritten.  
  
## Uploading the License File to SQL Server  
 The following procedure uploads the license for all [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] databases on the SQL Server instance.  
  
#### To upload your license file for all [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] databases  
  
1.  Start the [!INCLUDE[nav_dev_long](../dynamics-nav/includes/nav_dev_long_md.md)].  
  
    > [!NOTE]  
    >  On a computer running any version of Windows with User Access Control enabled, you must start the development environment with administrator privileges. In the **Start** menu, right\-click **[!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Development Environment** in the Start menu, and then choose **Run as administrator**.  
  
2.  Verify that you are connected to your database. On the **File** menu, point to **Database**, and then choose **Open**.  
  
3.  Upload the new license.  
  
    1.  On the **Tools** menu, choose **License Information**.  
  
    2.  In the **License Information** window, choose **Upload**.  
  
    3.  In the **Upload License File** dialog box, browse to and open the license file.  
  
     You should see the following message:  
  
     **The Server license was successfully uploaded.**  
  
4.  Restart the [!INCLUDE[nav_dev_short](../dynamics-nav/includes/nav_dev_short_md.md)] to activate the license.  
  
5.  Restart all [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instances on the computer to activate the license for other clients. For more information, see [Managing Microsoft Dynamics NAV Server Instances](../dynamics-nav/Managing-Microsoft-Dynamics-NAV-Server-Instances.md).  
  
> [!NOTE]  
>  Always review your license file after uploading, to verify that all information is correct and that you have all necessary license granules.  
  
##  <a name="UploadtoDatabase"></a> Uploading a License File for a Specific Database  
  
#### To upload a license file for a specific database  
  
1.  In the development environment, on the **File** menu, point to **Database**, and then choose **Alter**.  
  
2.  In the **Alter Database** window, choose **Integration**, and then select **Save license in database**.  
  
3.  Restart all [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instances on the computer to activate the license for other clients. For more information, see [Managing Microsoft Dynamics NAV Server Instances](../dynamics-nav/Managing-Microsoft-Dynamics-NAV-Server-Instances.md).  
  
## See Also  
 [License Types](../dynamics-nav/License-Types.md)   
 [How to: Install C\-SIDE Development Environment](../Topic/How%20to:%20Install%20C-SIDE%20Development%20Environment.md)   
 [Microsoft Dynamics ERP Software License Terms \(requires login\)](http://go.microsoft.com/fwlink/?LinkId=247426)   
 [Microsoft Dynamics ERP Licensing Guide \(requires PartnerSource login\)](http://go.microsoft.com/fwlink/?LinkID=318024)