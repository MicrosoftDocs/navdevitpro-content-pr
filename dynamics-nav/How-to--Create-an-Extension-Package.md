---
title: "How to: Create an Extension Package"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: c3403c71-52c4-4cd9-a8c4-22499bd78cd1
caps.latest.revision: 6
---
# How to: Create an Extension Package
When you have developed a [!INCLUDE[navnow](includes/navnow_md.md)] extension, the next step is to wrap your new .TXT and .DELTA files into a .NAVX file, the packaging format for extensions. The package includes the application objects and metadata that describes your extension, such as name and version.  
  
### To create the extension manifest  
  
-   The extension manifest describes characteristics about your extension. All characteristics have a parameter in the BROKEN-INCLUDE-wps_2](includes/wps_2_md.md)] cmdlet that you use to create the manifest, [!INCLUDE[New-NAVAppManifest. The following table describes the data in the manifest:  
  
    |Data|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
    |----------|---------------------------------------|  
    |Name|Specifies the name of the extension.|  
    |Publisher|Specifies the publisher of the extension, such as your company name.|  
    |Version|Specifies the version of the extension. The version is a string in the format of Major.Minor.Build.Revision, with a default value of 1.0.0.0. You must increment the value for each new version of the extension that you publish.|  
    |Description|Specifies the description for the extension.|  
    |Id|Specifies the unique identifier for the extension. A unique identifier will be generated if a value is not provided. The same unique identifier should be used for each new version of the extension.|  
    |CompatibilityId|Specifies the compatibility ID of the extension. The compatibility ID is a version string in the format of Major.Minor.Build.Revision, with a default value of 1.0.0.0. The value is used to indicate whether there are compatibility related code changes between different versions of the extension. If a new version of the extension does not break compatibility, leave the compatibility ID the same as the previous version.|  
    |Dependencies|Specifies the path to a package file \(.navx\) for another extension that this extension depends on. Use a comma \(,\) to separate the paths to multiple .navx files., such as in the following example: `C:\Proseware\SmartAppBase.navx, C:\Proseware\ProsewareBase.navx`|  
    |Prequisites|Specifies the objects that must exist in order to deploy the extension to a [!INCLUDE[nav_server](includes/nav_server_md.md)] instance. The prerequisites is a string in the format of type=ID, where type can be any object type such as Table, CodeUnit, or Page. Use a comma \(,\) to separate the prerequisites, such as in the following example: Table=397, CodeUnit=78.|  
  
     For more information, see [Manifest Overview](Manifest-Overview.md).  
  
     The New\-NAVAppManifest cmdlet creates an in\-memory Manifest object.  
  
    ```  
    New-NAVAppManifest -Name "Proseware SmartStuff" -Publisher "Proseware, Inc." -Version "1.5.0.12"  
    ```  
  
     You can either persist this object to a file and then check it in to source control by using `New-NAVAppManifestFile`, or you can pass it directly to BROKEN-INCLUDE-New-NAVAppPackage as described in the next step.  
  
    ```  
    New-NAVAppManifest -Name "Proseware SmartStuff" -Publisher "Proseware, Inc." -Version "1.5.0.12" | New-NavAppManifestFile -Path proseware.xml  
    ```  
  
     Related cmdlets are BROKEN-INCLUDE-Get-NAVAppManifest and BROKEN-INCLUDE-Set-NAVAppManifest. For more information, use the Get\-Help command in the [!INCLUDE[nav_dev_shell](includes/nav_dev_shell_md.md)].  
  
    > [!TIP]  
    >  For any [!INCLUDE[wps_2](includes/wps_2_md.md)] cmdlet, you can get help and sample usages, such as the following command:  
  
     `Get-Help Set-NAVAppManifest -Examples`  
  
 Next, you can choose to include permission sets in your package. This is optional, but at a minimum, an extension must include one permission set that grants permission to use the objects contained in the extension. An administrator must map users this permission set ID once it has been imported.  
  
### To retrieve permission sets for the extension  
  
-   Use the BROKEN-INCLUDE-Export-NAVAppPermissionSet cmdlet to export any permission sets that you have created for the extension as shown in the following example.  
  
    ```  
    Export-NAVAppPermissionSet -ServerInstance DynamicsNAVServer -Path ProsewarePerm.xml -PermissionSetId 12  
    ```  
  
    > [!CAUTION]  
    >  If you do not include a permission set with your extension, only users with the SUPER permission set will be able to use the app.  
  
 Once you have the DELTA and TXT files for your app created you can now complete the final step and build the extension package file. Extension packages require a manifest and access to the application objects you created.  
  
### To build the extension package  
  
-   Use the `New-NAVAppManifest` and `New-NAVAppPackage` cmdlets to build the manifest and package file.  
  
     The following is an example on how to create a new extension .NAVX package file with a new manifest.  
  
    ```  
    New-NAVAppManifest -Name "Proseware SmartStuff" -Publisher "Proseware, Inc." -Version "1.5.0.12" | New-NAVAppPackage -Path MyExtension.navx -SourcePath DELTA  
    ```  
  
     Alternatively, if you created a NAV App manifest file, you can use directly from that file:  
  
    ```  
    Get-NAVAppManifest -Path '.\Manifest-Proseware SmartStuff.xml' | New-NAVAppPackage -Path MyExtension.navx -SourcePath DELTA   
    ```  
  
     You have packaged your extension so it is ready to be published and installed on a target server.  
  
    > [!NOTE]  
    >  The packaging process adds a description of the extension to the manifest, such as whether it changes pages or adds tables. While not explicitly being enforced currently, this can be used to determine whether to install an extension, or not. Use `Get-NAVAppManifest –Path` to see capabilities.  
  
 Finally, you can choose to get your extension package signed to help validate its authenticity. Code signing is a common practice for many applications. For more information, see [Authenticode](https://msdn.microsoft.com/en-us/library/ms537359\(VS.85\).aspx) in the MSDN Library.  
  
## See Also  
 [Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)   
 [Manifest Overview](Manifest-Overview.md)   
 [How to: Develop an Extension](How%20to:%20Develop%20an%20Extension.md)   
 [How to: Publish and Install an Extension](How%20to:%20Publish%20and%20Install%20an%20Extension.md)   
 [Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)   
 [Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
 [Development Cmdlets for Microsoft Dynamics NAV Extensions](http://go.microsoft.com/fwlink/?LinkID=626875)
