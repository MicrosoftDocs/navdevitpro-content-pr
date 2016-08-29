---
title: "How to: Develop an Extension"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 69203ef8-ceb0-4dc9-8f4c-eacaa0d33a6c
caps.latest.revision: 4
---
# How to: Develop an Extension
You can build extension packages that add functionality to a [!INCLUDE[navnow](includes/navnow_md.md)] deployment. Unlike the familiar development and deployment of [!INCLUDE[navnow](includes/navnow_md.md)] functionality, building an extension relies on the exported version of an application to .TXT files. You can export the application from the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], use the development environment commands, or use the [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlet that is available in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)], `Export-NAVApplicationObjectLanguage`.  
  
> [!TIP]  
>  We recommend that you create a folder structure that can be leveraged by the cmdlets that you use when you build the extension package. That structure should contain folders for the ORIGINAL object files, MODIFIED object files, and DELTA files. These names match those used as parameters in the application merge utilities. For more information, see [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md).  
  
### To create an extension  
  
1.  Establish the BASE as TXT files.  
  
    1.  The foundation for your extension is the exported .txt files of the objects you are modifying. You can export just the objects that you want to modify, or you can export the entire [!INCLUDE[navnow](includes/navnow_md.md)] application. In the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)], the `Export-NAVApplicationObjectLanguage` cmdlet can automate this process or you can use the export functionality in the development environment. The following example uses this cmdlet to export objects to establish the base for the planned modifications.  
  
        ```  
        Export-NAVApplicationObject -Path ORIGINAL -DatabaseName MyDatabase -DatabaseServer MyDatabaseServer  
        ```  
  
        > [!IMPORTANT]  
        >  Objects must be exported as .TXT files. You cannot build an extension based on a .FOB file.  
  
         If you use a source control system, you may want to pull the base .TXT files from there.  
  
2.  Create functionality in the development environment.  
  
    1.  Use the development environment as usual to create new objects or modify ones to the extent your license allows you. Keep in mind the following rules:  
  
        -   DO NOT make C/AL code modifications  
  
        -   DO use subscribing to events to execute code.  
  
        -   DO NOT create new or modified XMLPorts, Queries, or Report. For more information, see [Extension Packages Capability Support Matrix](Extension-Packages-Capability-Support-Matrix.md).  
  
        -   DO NOT change restricted page and table properties.  
  
         In order to get an easy upgrade experience for your extensions, you cannot modify code the way you do in the traditional customization process. Instead, you extend [!INCLUDE[navnow](includes/navnow_md.md)] functionality by subscribing to programming events that are raised either explicitly in code, or implicitly by the platform. For more information, see [Events in Microsoft Dynamics NAV](Events-in-Microsoft-Dynamics-NAV.md).  
  
    2.  Test your application with the extension added.  
  
3.  Export your changed and added application objects to .TXT files.  
  
    1.  Export all objects that you added or modified to .TXT files. Use the same export cmdlet from step 1 or manually export within the development environment. They must also be exported as .TXT files and should be placed in a separate directory so that the packaging process can be pointed at them.  
  
        ```  
        Export-NAVApplicationObject -Path MODIFIED -DatabaseName MyDatabase -DatabaseServer MyDatabaseServer  
        ```  
  
4.  Create DELTA files using the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] cmdlets.  
  
    1.  Extension packages are based on application object deltas. Again, you use the application merge utilities in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)] to distil the changes in the form of application object differences that are stored in DELTA files. Creating an extension uses many of the same concepts and tools as you know from application object deltas. You use the `Compare-NAVApplicationObject` cmdlet to create these delta files.  
  
        ```  
        Compare-NAVApplicationObject -OriginalPath ORIGINAL -ModifiedPath MODIFIED -DeltaPath DELTA  
        ```  
  
        > [!NOTE]  
        >  Your delta files must be one-to-one with the objects you have added or modified. You cannot include a single merged delta file. If you output your export file as a single file use the `Split-NAVAppplicationObjectFile` cmdlet to create the individual files.  
  
5.  Build the extension package.  
  
     For more information, see [How to: Create an Extension Package](How%20to:%20Create%20an%20Extension%20Package.md).  
  
## Extending Other Extensions  
 You can extend the functionality that another extension has made available. When you do that, you create a dependency between the original extension and the one extending it. This dependency must be verified and compiled when the new extension is published.  
  
 You must have the source code for the extension that you want to extend available in the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)] to use as the base of your app. The steps for creating a dependent app, or, in other words, extending another extension, are outlined below.  
  
> [!NOTE]  
>  If you do not identify a dependency when you build your extension package, publishing your extension results in errors that are caused by base objects missing, and the publish operation will fail.  
  
#### To create a dependent extension  
  
1.  Import and compile the source code for the extension that you want to extend.  
  
2.  Use the [T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.Export-NAVApplicationObjectLanguage](assetId:///T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.Export-NAVApplicationObjectLanguage) cmdlet to establish the new base for your app deltas.  
  
3.  Extend the functionality with your modifications and additions using the development environment.  
  
4.  Use the [T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.Export-NAVApplicationObjectLanguage](assetId:///T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.Export-NAVApplicationObjectLanguage) and the [T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.Compare-NAVApplicationObject](assetId:///T:Microsoft.Dynamics.Nav.Model.Tools.Cmdlets.Compare-NAVApplicationObject) cmdlets to export and create the deltas for your app. Since you are comparing against a base that has the functionality that you are extending, you should only see deltas for your changes.  
  
5.  Create the package for your extension using the `New-NAVAppManifest`, `Get-NAVAppInfo`, and `New-NAVAppPackage` cmdlets making sure to use the *–Dependencies* parameter on the `New-NAVAppManifest` to identify the NAV extensions that you dependent on.  
  
## See Also  
 [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)   
 [How to: Create an Extension Package](How%20to:%20Create%20an%20Extension%20Package.md)   
 [How to: Publish and Install an Extension](How%20to:%20Publish%20and%20Install%20an%20Extension.md)   
 [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
 [Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)