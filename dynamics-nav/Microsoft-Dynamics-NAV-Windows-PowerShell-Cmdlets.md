---
title:"Microsoft Dynamics NAV Windows PowerShell Cmdlets"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 5ec9b35d-a50d-43d7-b20c-efddc98dca32
caps.latest.revision: 17
---
# Microsoft Dynamics NAV Windows PowerShell Cmdlets
[!INCLUDE[navnowlong](includes/navnowlong_md.md)] includes [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlets for administration and for development and file management of application object files and extension packages. The cmdlets are available in two Windows PowerShell modules: [!INCLUDE[nav_shell](includes/nav_shell_md.md)] and [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)].  
  
-   The [!INCLUDE[nav_shell](includes/nav_shell_md.md)] includes cmdlets for administering the [!INCLUDE[navnow](includes/navnow_md.md)] deployment, such as adding and configuring [!INCLUDE[navnow](includes/navnow_md.md)] server instances, databases, and users. Also included are cmdlets for administering extension packages. The [!INCLUDE[nav_shell](includes/nav_shell_md.md)] is installed with the [!INCLUDE[nav_server](includes/nav_server_md.md)].  
  
-   The [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] includes cmdlets for merging and modifying application object files. Also included are cmdlets for creating extension packages. The [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] is installed with the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)].  
  
 The cmdlets are implemented in [!INCLUDE[wps_2](includes/wps_2_md.md)] 3.0, which is included with Windows Server 2012 and Windows 8 and later. For other versions of Windows supported for [!INCLUDE[navnowlong](includes/navnowlong_md.md)], you can install it as part of the [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/?LinkId=293806) on the Microsoft Download Center.  
  
> [!NOTE]  
>  Alternatively to running [!INCLUDE[nav_shell](includes/nav_shell_md.md)] and [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] from where they are installed, you can import the relevant module into the [!INCLUDE[wps_2](includes/wps_2_md.md)] Integrated Scripting Environment \(ISE\).  
  
## Starting a [!INCLUDE[nav_shell](includes/nav_shell_md.md)] Session  
 You must run the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] as an Administrator. On the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)], choose **Start**, in the **Search** box, type **[!INCLUDE[nav_shell](includes/nav_shell_md.md)]**, right\-click the related link, and then choose **Run as Administrator**.  
  
> [!IMPORTANT]  
>  To run the cmdlets in the [!INCLUDE[nav_shell](includes/nav_shell_md.md)], you must be a member of the local Administrator group on the computer where the [!INCLUDE[nav_shell](includes/nav_shell_md.md)] is installed.  
  
## Starting a [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] Session  
 On the computer that is running [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)], choose **Start**, in the **Search** box, type **[!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)]**, and then choose the related link.  
  
## Getting Help on [!INCLUDE[navnow](includes/navnow_md.md)] Cmdlets  
 To see the cmdlets that are available for [!INCLUDE[navnow](includes/navnow_md.md)], type the following at the [!INCLUDE[wps_2](includes/wps_2_md.md)] prompt.  
  
```  
Get-Command *NAV*  
```  
  
 To get Help about syntax and options for a specific cmdlet, type the following cmdlet.  
  
```  
Get-Help <cmd name>  
```  
  
 For example, to get Help about the **Get\-NAVServerInstance** cmdlet, type the following.  
  
```  
Get-Help Get-NAVServerInstance  
```  
  
 To get online Help in the MSDN Library for a specific cmdlet, type the following cmdlet.  
  
```  
Get-Help <cmd name> -online  
```  
  
 For more information about [!INCLUDE[nav_shell](includes/nav_shell_md.md)] cmdlets, see [Administration Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510539) and [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874).  
  
 For more information about [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] cmdlets, see [Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkId=510540) and [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626875).  
  
 For more information about Windows PowerShell, see [Windows PowerShell Getting Started Guide](http://go.microsoft.com/fwlink/?LinkID=252252).  
  
## See Also  
 [Sample Windows PowerShell Scripts for Microsoft Dynamics NAV](Sample-Windows-PowerShell-Scripts-for-Microsoft-Dynamics-NAV.md)   
 [Administration](Administration.md)   
 [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)   
 [Administration Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510539)   
 [Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)   
 [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626875)   
 [Administration Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626874)