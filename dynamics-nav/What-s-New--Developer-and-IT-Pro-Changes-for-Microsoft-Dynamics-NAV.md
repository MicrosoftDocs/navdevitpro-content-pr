---
title: "What&#39;s New: Developer and IT Pro Changes for Microsoft Dynamics NAV"
ms.custom: na
ms.date: 07/20/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 823f9666-1de0-49f7-a630-01d0b82e6918
caps.latest.revision: 282
manager: edupont
---
# What&#39;s New: Developer and IT Pro Changes for Microsoft Dynamics NAV
[!INCLUDE[navnow](includes/navnow_md.md)] is a complete enterprise resource planning \(ERP\) software solution for mid-sized organizations that is fast to implement, easy to configure, and simple to use. Right from the start, simplicity has guided—and continues to guide—innovations in product design, development, implementation, and usability.  

 This document details new features and functionality that are available in BROKEN-INCLUDE-navcorfu](includes/navcorfu_md.md)] and have been added to the product since [!INCLUDE[navcrete](includes/navcrete_md.md)]. It also describes features that have been deprecated since [!INCLUDE[navcrete](includes/navcrete_md.md)]. For information about [!INCLUDE[navcrete](includes/navcrete_md.md)], see [What's New: Developer and IT Pro Changes for Microsoft Dynamics NAV 2015](http://msdn.microsoft.com/en-us/library/hh174007\(v=nav.80\).aspx) in the MSDN Library. [!INCLUDE[endchmFor more information, see the "What's New: Developer and IT Pro Changes for Microsoft Dynamics NAV 2015" section in the [!INCLUDE[navnow](includes/navnow_md.md)] Help in the MSDN Library.  

## What's New for Developers, Administrators, and IT Pros in [!INCLUDE[navcorfu](includes/navcorfu_md.md)]  
 [!INCLUDE[navcorfu](includes/navcorfu_md.md)] introduces changes to the upgrade, development, deployment, and administration experiences compared to [!INCLUDE[navcrete](includes/navcrete_md.md)].  

### Redesigned C/AL Editor  
 The C/AL Editor in the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] has been redesigned to give you more coding capabilities. Coding in the new C/AL editor is like before except you benefit from new features such as IntelliSense, name completion, change tracking, improved syntax highlighting and colorization. The new design has a look-and-feel that resembles the Debugger regarding breakpoints.  

> [!TIP]  
>  You can use the old version of the C/AL Editor by running the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] from a command prompt and setting the `useoldeditor` parameter.  

### Record Permissions and Apply Permissions Sets to User Groups  
 Administrators can record new permission sets in [!INCLUDE[navnowlong](includes/navnowlong_md.md)]. Recording permissions is based on the code coverage functionality. You can access the various windows and activities in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or the [!INCLUDE[nav_web](includes/nav_web_md.md)] that you want users with this permission set to access. You must carry out the tasks that you want to record permissions for. Then, you can apply the new permission set to a group of users.  

 BROKEN-INCLUDE-startchm](../Token/startchm_md.md)] For more information, see [User Groups](User-Groups.md) and [How to: Create or Modify Permission Sets](How-to--Create-or-Modify-Permission-Sets.md).[!INCLUDE[endchm  

 For more information, see the [User Groups](User-Groups.md) topic in the Application Help and the [How to: Create or Modify Permission Sets](How-to--Create-or-Modify-Permission-Sets.md) topic in the Developer and IT Pro Help.  

### Events in C/AL  
 By implementing events in C/AL code, you can design applications to react to specific actions or behavior that occur. Events enable you to separate customized functionality from the application business logic. By using events in the application where customizations are typically made, you can lower the cost of code modifications and upgrades to the original application.  

 For more information, see [Events in Microsoft Dynamics NAV](Events-in-Microsoft-Dynamics-NAV.md).  

### Event Channels on Microsoft Dynamics NAV Server Events  
 [!INCLUDE[navcorfu](includes/navcorfu_md.md)] introduces event channels on events that occur on [!INCLUDE[nav_server](includes/nav_server_md.md)] instances. Event channels provide a way to collect and view event data from a specific provider, which in this case in [!INCLUDE[nav_server](includes/nav_server_md.md)], and for a specific type of event, such as admin, operational, or debug. The implementation of event channels offers the following enhancements to event logging and viewing:  

-   In addition to the Windows Application log, [!INCLUDE[nav_server](includes/nav_server_md.md)] events are recorded in specific [!INCLUDE[nav_server](includes/nav_server_md.md)] logs in the Applications and Services Logs of Windows.  

     This provides an advantage over the Windows Application log which contains events from several providers, not just the [!INCLUDE[nav_server](includes/nav_server_md.md)]. You also have the option to disable logging to the Windows Application log.  

-   You can use Event Viewer to view trace events.  

-   You can use *FilterXpath* parameter of the Get-WinEvent Windows PowerShell cmdlet to filter events for a specific [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  

 BROKEN-INCLUDE-startchm](../Token/startchm_md.md)]For more information, see [Monitoring Microsoft Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md).[!INCLUDE[endchmFor more information, see the "Monitoring Microsoft Dynamics NAV Server Events" topic in the Developer and IT Pro Help.  

### Multiple Namespaces on XMLports  
 You can define multiple namespaces on XMLports that import or export data as XML. This improves the ability to create XMLports that are compatible with the XML schemas that are used by the systems that consume or provide the [!INCLUDE[navnow](includes/navnow_md.md)] data.  

 You define namespaces in the new [Namespaces Property](Namespaces-Property.md) of the XMLport object. Each namespace is defined by a prefix and the namespace, which is typically a URI \(uniform Resource Identifier\). You then apply the prefix to specific elements of the XMLport by setting the new [NamespacePrefix Property](NamespacePrefix-Property.md).  

 BROKEN-INCLUDE-startchm](../Token/startchm_md.md)]For more information, see [!INCLUDE[endchm[Using Namespaces with XMLports](Using-Namespaces-with-XMLports.md).For more information, see the "Using Namespaces with XMLports" topic in the Developer and IT Pro Help.  

### Updating Custom Report Layouts by Using Upgrade Codeunits  
 You can update custom report layouts by creating upgrade codeunits to handle changes in report datasets that affect the report layouts. Upgrade codeunits enable you to programmatically update multiple custom report layouts in the database to changes in report datasets that cannot be resolved by users from the [!INCLUDE[navnow](includes/navnow_md.md)] client. For more information, see [Updating Custom Report Layouts by Using Upgrade Codeunits](Updating-Custom-Report-Layouts-by-Using-Upgrade-Codeunits.md).  

### Filter Pages for Filtering Tables  
 [!INCLUDE[navcorfu](includes/navcorfu_md.md)] includes the new C/AL data type **FILTERPAGEBUILDER**. You can use the FILTERPAGEBUILDER data type and its functions to create a filter page that enables users to set filters on one or more tables. A filter page contains one or more filter controls, where each filter control can be used to set filters on a specific table. Similar to report request pages in the [!INCLUDE[navnow](includes/navnow_md.md)] client, filter pages are generated at runtime and run in a modal dialog box.  

 For more information, see [Creating Filter Pages for Filtering Tables](Creating-Filter-Pages-for-Filtering-Tables.md) and [FilterPageBuilder Data Type](FilterPageBuilder-Data-Type.md).  

### C/AL Try Functions for Handling Errors  
 Try functions enable you to catch and handle errors that occur when running the application. You can use try functions to catch errors and exceptions that are thrown by [!INCLUDE[navnow](includes/navnow_md.md)] or .NET Framework interoperability operations.  

 For more information, see [Handling Errors by Using Try Functions](Handling-Errors-by-Using-Try-Functions.md).  

### HyperlinkHandler Function Type in Test Codeunits  
 You can write HyperlinkHandler functions in test codeunits to test hyperlink URLs that are passed to the HYPERLINK function. This is similar to other handler function types for handling UI interactions in application testing.  

 For more information, see [How to: Create Handler Functions](How-to--Create-Handler-Functions.md).  

### Object Metadata Virtual Tables  
 [!INCLUDE[navnowlong](includes/navnowlong_md.md)] includes the following virtual tables that contain metadata about [!INCLUDE[navnow](includes/navnow_md.md)] objects.  

-   **Codeunit Metadata** virtual table  

-   **Page Metadata** virtual table  

-   **Report Metadata** virtual table  

-   **Table Metadata** virtual table  

 BROKEN-INCLUDE-startchm](../Token/startchm_md.md)]For more information, see [!INCLUDE[endchm[Virtual Tables](Virtual-Tables.md)For more information, see the "Virtual Tables" topic in the Developer and IT Pro Help.  

### New CLIENTTYPE Options Added  
 With[!INCLUDE[navnow](includes/navnow_md.md)] the `CLIENTTYPE` function has been expanded to support [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)], [!INCLUDE[nav_phone](includes/nav_phone_md.md)] and running the app in [!INCLUDE[nav_web](includes/nav_web_md.md)], which is Desktop mode. This allows showing, for example, pages differently depending on the display target. For more information, see [CURRENTCLIENTTYPE Function](CURRENTCLIENTTYPE-Function.md) and [DEFAULTCLIENTTYPE Function](DEFAULTCLIENTTYPE-Function.md).  

### Column Layout on Role Centers  
 The mechanism behind the column layout on the Role Center specifically for the [!INCLUDE[nav_web](includes/nav_web_md.md)] has been changed. It is still possible to define groups as previously, and thereby keep the design of existing Role Centers. But when these Role Centers are displayed on larger screens, there is an automatic switch to a 4 column layout. When developing new Role Centers, it is now possible to not define any groups and let the dynamic layout handle the switch from 1 to 2 to 3 column layout, depending on the screen size.  

 When building Role Centers it is recommended to avoid using the **Group** type to group the parts that make up the Role Center, and instead create all parts directly underneath the **Container** type. This will optimize the layout to be more dynamic and thereby fit more display targets.  

### Camera and Location  
 With [!INCLUDE[navnow](includes/navnow_md.md)]an API for integrating to a camera and getting GPS coordinates is available. The camera option is implemented in the application as functionality available when using Incoming Documents on, which you can see on, for example, the Accounting Manager profile. For a code example of how to integrate with the camera option, see [How to: Implement the Camera in C/AL](How-to--Implement-the-Camera-in-C-AL.md). For a code example of how to get GPS coordinates, see [How to: Implement Location in C/AL](How-to--Implement-Location-in-C-AL.md).  

### Sizing Settings for Control Add-ins  
 To control that the sizing of the control add-ins is always optimal on all display targets a number of new settings are available to you when writing the manifest code. For more information, see [Manifest Overview](Manifest-Overview.md).  

### Structure for Resource Files in Manifest  
 [!INCLUDE[navnow](includes/navnow_md.md)] supports resource files to be described in the manifest file with or without a relative path allowing you to organize and maintain resource files the way you prefer. For more information, see [Manifest Overview](Manifest-Overview.md).  

### Tooltips on [!INCLUDE[nav_web](includes/nav_web_md.md)]  
 The [ToolTip Property](ToolTip-Property.md) and the [ToolTipML Property](ToolTipML-Property.md)have been added on **ActivityButtons** and **ActionContainers** of the subtype **HomeItems** to support displaying descriptions in the navigation pane.  

### Microsoft Dynamics CRM Integration  
 [!INCLUDE[navcorfu](includes/navcorfu_md.md)] introduces a new and improved integration with [!INCLUDE[crm](includes/crm_md.md)]. The new [!INCLUDE[crm](includes/crm_md.md)] integration provides an optimal and seamless experience for integrating [!INCLUDE[crm](includes/crm_md.md)] entities, such as accounts, and corresponding [!INCLUDE[navnow](includes/navnow_md.md)] business data tables, such as customers. [!INCLUDE[crm](includes/crm_md.md)] integration enables users to view [!INCLUDE[crm](includes/crm_md.md)] data in [!INCLUDE[navnow](includes/navnow_md.md)] and [!INCLUDE[navnow](includes/navnow_md.md)] data in [!INCLUDE[crm](includes/crm_md.md)]. It also enables you to synchronize the data between the solutions so that it is the same in both places.  

 [!INCLUDE[navcorfu](includes/navcorfu_md.md)] includes a default integration setup that is supported by several objects, including tables, pages, and codeunits. You can customize these objects to extend the integration to other [!INCLUDE[crm](includes/crm_md.md)] entities and change processes like synchronization.  

 For more information, see [Integrating Microsoft Dynamics CRM in Microsoft Dynamics NAV](Integrating-Microsoft-Dynamics-CRM-in-Microsoft-Dynamics-NAV.md) .BROKEN-INCLUDE-endchm and [Customizing Dynamics CRM and Dynamics NAV Integration](Customizing-Dynamics-CRM-and-Dynamics-NAV-Integration.md).  

### Additional Numeric Data Types Supported in Aggregations by Queries, FlowFields, and SIFT  
 In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], data aggregations \(such as sum and average\) on tables by Query objects, FlowFields, and SumIndexField Technology could only be done on **Decimal** data type fields. With [!INCLUDE[navcorfu](includes/navcorfu_md.md)] you can use **Decimal**, **Integer**, **BigInteger**, and **Duration** data types in aggregations.  

 For more information, see [Understanding Query Totals and Grouping](Understanding-Query-Totals-and-Grouping.md), [FlowFields](FlowFields.md), and [SumIndexField Technology \(SIFT\)](SumIndexField-Technology--SIFT-.md).  

### Timestamp Field Available in Tables  
 Each table in [!INCLUDE[navnow](includes/navnow_md.md)] includes a hidden timestamp field. The timestamp field contains row version numbers for records as maintained in SQL Server. In earlier versions of [!INCLUDE[navnow](includes/navnow_md.md)], the timestamp field could not be used in tables. In [!INCLUDE[navcorfu](includes/navcorfu_md.md)], you can expose the timestamp field in tables, write code against it, add filters, and so on, similar to any other field in a table.  

 For more information, see [How to: Use a Timestamp Field](How-to--Use-a-Timestamp-Field.md).  

### SQL Server Authentication  
 [!INCLUDE[navcorfu](includes/navcorfu_md.md)] supports SQL Server authentication between the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance and the [!INCLUDE[navnow](includes/navnow_md.md)] database in SQL Server. Previously only Windows authentication was supported.  

 For more information, see [How to: Configure SQL Server Authentication in Microsoft Dynamics NAV](How-to--Configure-SQL-Server-Authentication-in-Microsoft-Dynamics-NAV.md).  

### Microsoft Azure SQL Database Support  
 You can deploy a [!INCLUDE[navnow](includes/navnow_md.md)] database to Azure SQL Database. Azure SQL Database is a cloud service for data storage that is a part of the Azure Services Platform.  

 For more information, see [How to: Deploy a Microsoft Dynamics NAV Database to Azure SQL Database](How-to--Deploy-a-Microsoft-Dynamics-NAV-Database-to-Azure-SQL-Database.md).  

### Automatic Deployment of Add-ins From the Database  
 [!INCLUDE[navcrete](includes/navcrete_md.md)] introduced the automatic deployment of Microsoft .NET Framework Interoperability and control add-in assemblies from the [!INCLUDE[nav_server](includes/nav_server_md.md)] to the [!INCLUDE[navnow](includes/navnow_md.md)] clients. [!INCLUDE[navcorfu](includes/navcorfu_md.md)] now makes it possible to automatically deploy add-in assemblies \(including client control add-ins, .NET Framework interoperability, and language resources\) directly from [!INCLUDE[navnow](includes/navnow_md.md)] database to the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance or client as required. To accomplish this, you import the add-in files as a compressed \(.zip\) file into the database. You perform this by using page **9820 Control Add-ins** or using the [New-NAVAddin cmdlet](http://go.microsoft.com/fwlink/?LinkID=521781), [Set-NAVAddin cmdlet](http://go.microsoft.com/fwlink/?LinkID=521784), [Get-NAVAddin](http://go.microsoft.com/fwlink/?LinkID=521782), or [Remove-NAVAddin](http://go.microsoft.com/fwlink/?LinkID=521783) cmdlets from the [!INCLUDE[nav_shell](includes/nav_shell_md.md)]. The add-ins are then stored in system table **2000000069 Add-ins**.  

 For more information, see [How to: Install a Windows Client Control Add-in Assembly](How-to--Install-a-Windows-Client-Control-Add-in-Assembly.md) and [How to: Set .NET Framework Types to Run on the Microsoft Dynamics NAV Windows Client or Microsoft Dynamics NAV Server Computers](How-to--Set-.NET-Framework-Types-to-Run-on-the-Microsoft-Dynamics-NAV-Windows-Client-or-Microsoft-Dynamics-NAV-Server-Computers.md).  

### Running NAS Services with Administrator Rights  
 In earlier [!INCLUDE[navnow](includes/navnow_md.md)] versions, to run NAS services, the [!INCLUDE[nav_server](includes/nav_server_md.md)] service account had to be added as a user in [!INCLUDE[navnow](includes/navnow_md.md)] and assigned the required permissions to perform the operations. In [!INCLUDE[navcorfu](includes/navcorfu_md.md)], you can set up NAS services to run with administrator rights, which grants the NAS service the same permissions as the SUPER permission set without having to add the [!INCLUDE[nav_server](includes/nav_server_md.md)] service account as a user in [!INCLUDE[navnow](includes/navnow_md.md)]. This feature is supported for NAS services in a single tenant \(non-multitenant\) and multitenant [!INCLUDE[nav_server](includes/nav_server_md.md)] deployment.  

 For more information, see [Configuring NAS Services](Configuring-NAS-Services.md).  

### Tenant Configurations Stored in Application Database  
 In a multitenant [!INCLUDE[nav_server](includes/nav_server_md.md)] deployment, the configuration information about the tenants that are mounted on a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance is now stored in the application database \(table **dbo.$ndo$tenants**\) instead of a tenant.config file for the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  

 This change is especially useful in application deployments where multiple [!INCLUDE[nav_server](includes/nav_server_md.md)] instances serve the same tenants. It is now easier to add [!INCLUDE[nav_server](includes/nav_server_md.md)] instances to load-balance or scale an application deployment. Instead of having to mount tenants manually, new server instances will automatically inherit the tenant configurations from the application database and mount tenants automatically. Also, when you want to mount or dismount a tenant, you only have to mount or dismount the tenant on one of the server instances for an application database because other server instances will automatically detect and apply the changes.  

 For more information, see [Multitenant Deployment Architecture](Multitenant-Deployment-Architecture.md).  

### Loading Application Assemblies When Microsoft Dynamics NAV Server Instances Start  
 You can configure a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance to compile all the business application assemblies and load them to cache memory when the server instance is started. The assemblies are then retrieved from memory when requested by a [!INCLUDE[navnow](includes/navnow_md.md)] client. This improves the response time after restarting a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  

 For more information, see the **Compile and Load Business Application** setting in [Configuring Microsoft Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md).  

### Automatic Company Initialization During Data Upgrade  
 Previously, when upgrading data from an older version of [!INCLUDE[navnow](includes/navnow_md.md)] to the latest version, you had to manually run codeunit 2 **Company Initialization** on each company in the database. When upgrading data to [!INCLUDE[navcorfu](includes/navcorfu_md.md)], this task is automatically performed for you by the upgrade process.  

 For more information, see the [Upgrading Data](Upgrading-Data.md).  

### Microsoft Dynamics NAV Windows Client Available in 64-Bit Version  
 On a 64-bit Windows operating system, the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] is available in 64-bit version and 32-bit version. By default, when you install the [!INCLUDE[nav_windows](includes/nav_windows_md.md)], the 64-bit version is used. The 64-bit version is better when you have to run several large reports. However, there are some components, such as COM, which are not supported on 64-bit applications. Therefore, you can also run the 32-bit version of the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] if it is required. For more information, see [Running 32-Bit Microsoft Dynamics Windows Client on 64-Bit Windows](Running-32-Bit-Microsoft-Dynamics-Windows-Client-on-64-Bit-Windows.md).  

### Multilanguage Captions Compile as Unicode  
 When you compile application objects, [!INCLUDE[navnow](includes/navnow_md.md)] stores the objects in Unicode encoding. If the application objects contain multilanguage captions, [!INCLUDE[navnow](includes/navnow_md.md)] uses the code pages that are relevant for the languages that you have specified. For more information, see [Developing Multilanguage-Enabled Applications](Developing-Multilanguage-Enabled-Applications.md).  

## Changes to C/AL Functions, Data Types, Properties, and Triggers in [!INCLUDE[navcorfu](includes/navcorfu_md.md)]  
 BROKEN-INCLUDE-startchm](../Token/startchm_md.md)]For a list of changes to C/AL functions, data types, properties, and triggers, see [Changes in C/AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV](Changes-in-C-AL-Behavior-and-Support-from-Earlier-Versions-of-Microsoft-Dynamics-NAV.md). [!INCLUDE[endchmFor a list of changes to C/AL functions, data types, properties, and triggers, see the "Changes in C/AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV" topic in the Developer and IT Pro Help.  

## Changes to [!INCLUDE[nav_shell](includes/nav_shell_md.md)] and [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] cmdlets  
 For a list of new, changed, or removed Windows PowerShell cmdlets, see [Changes to Microsoft Dynamics NAV Cmdlets From Previous Release](Changes-to-Microsoft-Dynamics-NAV-Cmdlets-From-Previous-Release.md).  

## See Also  
 [What’s New: Application Changes for Microsoft Dynamics NAV](What-s-New:-Application-Changes-for-Microsoft-Dynamics-NAV.md)
