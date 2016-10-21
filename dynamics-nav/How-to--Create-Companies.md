---
title: "How to: Create Companies"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 84546d7f-30b6-4de0-ab8d-2b01035dfbc9
caps.latest.revision: 11
manager: edupont
---
# How to: Create Companies
You can create as many companies as you want in a database. You can create companies in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] and the [!INCLUDE[nav_web](includes/nav_web_md.md)]. You can also create companies by using the **New-NAVCompany** Windows PowerShell cmdlet.  

> [!IMPORTANT]  
>  If the company name starts with CRONUS \(in uppercase letters\) and you use a [!INCLUDE[demolonglight](includes/demolonglight_md.md)] license, the company automatically becomes a demonstration company with all the restrictions that are set in the [!INCLUDE[demolonglight](includes/demolonglight_md.md)]. For example, in [!INCLUDE[demo](includes/demo_md.md)] you can only post between November and February.  

 The following procedure illustrates how you can create a new company in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)], but similar steps apply to creating companies in the [!INCLUDE[nav_web](includes/nav_web_md.md)].  

### To create a company in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or [!INCLUDE[nav_web](includes/nav_web_md.md)]  

1.  In [!INCLUDE[navnow](includes/navnow_md.md)], in the **Search** box, enter **Companies**, and then choose the related link.  

2.  On the **Home** tab, in the **Manage** group, choose **Edit List**.  

     You can create a new company, or you can create a copy of an existing company. When you create a new company, data is not included. When you create a copy, the business data is copied to the new company.  

    1.  To create a new company, choose an empty row, and then, in the **Company Name** field, enter the name of the new company.  

         The company name can have a maximum of 30 characters. If the database collation is case-sensitive, you can have one company called COMPANY and another called Company. However, if the database is case-insensitive, you cannot create companies with names that differ only by case.  

    2.  To create a copy of an existing company, choose a company, and then, on the **Home** tab, in the **New** group, choose **Copy**.  

         Then, in the **\($ B\_357 Copy Company $\)** window, in the **Company Name** field, enter the name of the new company.  

         Choose the **OK** button to create the company.  

 When you create the company name, remember that it will be written at the top of various reports. Therefore, write it exactly as you want it to appear. You can rename existing companies. For more information, see [How to: Rename Companies](How-to--Rename-Companies.md).  

 You can create as many companies as your license allows for.  

## See Also  
 [Companies](\($-N_357-Companies-$\).md)   
 [How to: Select a Company](\($-S_COMPANY-How-to--Select-a-Company-$\).md)   
 [How to: Rename Companies](How-to--Rename-Companies.md)   
 [How to: Delete Companies](How-to--Delete-Companies.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)
