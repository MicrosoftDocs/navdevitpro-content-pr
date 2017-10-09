---
author: jswymer
title: "How to: Write Extension Upgrade Code"
ms.custom: na
ms.date: 07/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---
This topic provides information about how you can upgrade an existing extension after making changes.  

## Overview
Changes to a [!INCLUDE[navnow](includes/navnow_md.md)] deployment by an extension are treated differently than if you had manually added them to your code base. UI modifications are, in their simplest form, just the differences or deltas from the base application code. These are applied at runtime. On the other hand, because an extension package cannot modify existing code or add new code to existing objects, changes in business logic must be encapsulated through the use of events or in new codeunits. For more information, see [Introducing Events](Introducing-Events.md).  

You should not necessarily consider the upgrade of extensions as part of the upgrade process of the [!INCLUDE[navnow](includes/navnow_md.md)] deployment as a whole; unless a product upgrade has an adverse effect on an extension. In this case, you will need to address the condition by adding upgrade code to your extension. You can upgrade your extension independently of the [!INCLUDE[navnow](includes/navnow_md.md)] deployment.  

> [!TIP]  
>  We recommend that you add the upgrade code to your very first version of the extension to handle the uninstallation and reinstallation for cases when an upgrade failed, or the users inadvertently uninstalled.  


## How to Upgrade an Extension
To upgrade an extension, you simply uninstall the old package and then install a new version of the package. The newer version takes care of the rest. You can do this by using the [Uninstall-NAVApp](http://go.microsoft.com/fwlink/?LinkID=618057) and [Install-NAVApp](http://go.microsoft.com/fwlink/?LinkID=618056) cmdlets.  

When an extension package is uninstalled, all data for the extension is archived into a set of special tables, so while the extension is now removed from the system, the data is still preserved. This becomes important when you install an update because at that time, it invokes code designed to upgrade or restore any data from the old version.  

When uninstalling the extension, you can choose to not archive the data from the extension. This is accomplished by use of the *DoNotSaveData* switch parameter for the [Uninstall-NAVApp](https://msdn.microsoft.com/en-us/library/mt584146.aspx) cmdlet. Similarly, when an extension package is installed, you can choose to not load any previous version archived data by use of the *DoNotLoadData* switch parameter on the [Install-NAVApp](https://msdn.microsoft.com/en-us/library/mt584144.aspx) cmdlet. Installing and uninstalling an extension from the **Extension Management** page in the client will always save and load the data. When using these switches to either not archive data or not load archived data, the archived data will not be restored for any tables no matter what functions where written for the individual tables. Any starting data for a table will be imported into the table however.  

The following example illustrates how you can uninstall an extension and not archive its data.  

```  
Uninstall-NAVApp -ServerInstance YourDynamicsNAVServer -Path MyNAVExtension.navx -DoNotSaveData
```  

## Developing an Extension for Upgrading
When you develop an extension, you must write logic that actively upgrades or restores the archived data when the extension is installed. This code must be placed in specific functions in a codeunit in the package. As a developer of an extension, you must make sure that all scenarios for upgrades are included in your upgrade code, including the possibility that the exact same version of the extension is re-installed.  

Your extension is upgraded if you implement global functions with the following names:  

-   `OnNavAppUpgradePerDatabase()`

    Called only once in the installation process.  

-   `OnNavAppUpgradePerCompany()`  

    Called once for each company in the tenant currently being installed to.  

> [!IMPORTANT]  
>  The codeunit cannot be an **Upgrade** codeunit type. You can use more than one codeunit to contain the upgrade functions. However, it is recommended that you use a single codeunit because this gives you more control over the execution order of the upgrade code. Within a single codeunit, the `OnNavAppUpgradePerDatabase` function is run before the `OnNavAppUpgradePerCompany` function.  

There are several system functions that enable you access and manage archived data from the last version of the extension that was uninstalled. For more information about these functions, see [NAV App](NAV-App.md).  

For each new or modified table in your extension, you must use one of the following options in the appropriate upgrade global function for handling any archived data. A single extension may combine the approaches as long as all modified or added tables are handled.  

-   Restore table data  

-   Delete table data  

-   Upgrade table data  

-   Load default or starting table data  

You must include `OnNavAppUpgradePerDatabase` or `OnNavAppUpgradePerCompany` functions to your upgrade code. If these functions are not present at the time of creating the extension package and there are schema changes, the packaging will fail with an error. The installation of an extension package will also validate that all table changes are handled, and the following error occurs if they are not handled:

*The package contains changes to the database schema that are not handled in upgrade code.*

> [!NOTE]  
>  An extension package that was created by using [!INCLUDE[navcorfu](includes/navcorfu_md.md)] prior to Cumulative Update 1 may have been successfully created without the handling of archive data. This package can be published successfully for [!INCLUDE[navcorfu](includes/navcorfu_md.md)], but it may fail on a re-install if there is archive data. You will need to use the –DoNotLoadData parameter or create a new version of the extension package with upgrade code in order to successfully re-install this extension.  

For detailed instructions about how to write upgrade code, see [How to: Write Extension Upgrade Code](extensions-upgrade-howto.md).

# How to: Write Extension Upgrade Code
The process of upgrading an extension includes uninstalling the current version of the extension and then installing a new version. If the extension modifies the schema of an existing table, or adds new tables, upgrade code will be required to handle the data that was automatically archived from the tables during uninstall. The upgrade code is written in a specific type of codeunit called and upgrade codeunit. The upgrade codeunit is built into the extension package together with the application objects. 


For more information about upgrading extensions, see [Upgrading Extensions](extensions-upgrading.md).  

## To write upgrade code for an extension
1.  Create new codeunit, and set the [SubType Property](properties/devenv-subtype-property-codeunit.md) to **Upgrade**. 

2. Make sure the function is declared as global so that the **Local** property is set to **No**.  

3.	Add the upgrade trigger functions to the codeunit.
  
    1. Add the *OnNavAppUpgradePerDatabase()* function if the extension contains cross-company tables.   
    2. Add the *OnNavAppUpgradePerCompany()* function if the extension contains per-company tables.

3.  Add the upgrade code to the appropriate function.  

    The upgrade code will depend on what you want to do with the archived data, plus additional factors such as the version of the archive data, whether the schema has changed, and whether the data can be modified by users. Determine which of the following upgrade methods is required for each new or modified table in your extension. For more information, see the next sections.  

### Restore Table Data
If the table has the same schema as the archive data and doesn’t require any special upgrade logic, then use the [RESTOREARCHIVEDATA](restorearchivedata-function.md) system function to copy the archived data to the table. The data that is copied may be for new tables added as part of the extension or for fields added to existing base tables.  

The following code example restores the archived data for tables 50000 and 50001 on a company basis.  

```  
PROCEDURE OnNavAppUpgradePerCompany@1();  
BEGIN  
  NAVAPP.RESTOREARCHIVEDATA(50000);  
  NAVAPP.RESTOREARCHIVEDATA(50001);  
END;  
```  

### Delete Table Data
If you do not want to restore the archived data to the table, then use the [DELETEARCHIVEDATA](deletearchivedata-function.md) system function to delete the archived data.  

The following code deletes the archived data for table 50002 on a company basis.

```  
PROCEDURE OnNavAppUpgradePerCompany@1();  
BEGIN  
  NAVAPP.DELETEARCHIVEDATA(50002);  
END;  
```  

### Upgrade Table Data
If the archived data is from a previous version and requires special upgrade logic, then use custom code to upgrade the records retrieved from the archive tables. For this scenario, you will use the following system functions:  

-   [GETARCHIVEVERSION Function](GETARCHIVEVERSION-Function.md)  

    Returns the extension version of archived data.  

-   [GETARCHIVERECORDREF Function](GETARCHIVERECORDREF-Function.md)  

    Returns a RecordRef for the identified table.  

-   [RESTOREARCHIVEDATA Function](restorearchivedata-function.md)  

    Restores the archived data to the database.

The following code upgrades records that are retrieves from the archived table for table 50003. The upgrade code that is run depends on the extension version number of the archived data.  

```  
VAR
  ArchiveRecRef@1000 : RecordRef;  
  FldRef@1001 : FieldRef;  
  DestRec@1002 : Record;  
  Version@1003 : Text[20];  
PROCEDURE OnNavAppUpgradePerCompany@1();  
BEGIN  
  Version := NAVAPP.GETARCHIVEVERSION();  
  IF Version < '2.0.0.0' THEN BEGIN  
    // The Version 1 to Version 2 upgrade code block. Copy over relevant old fields and initialize new fields using archive data.  
    IF NAVAPP.GETARCHIVERECORDREF(50003, ArchiveRecRef) THEN BEGIN  
      IF ArchiveRecRef.FINDSET(FALSE) THEN BEGIN  
        DestRec.INIT;  
        REPEAT  
          FldRef := ArchiveRecRef.FIELD(50000);  
          DestRec.Key := FldRef.VALUE;  
          FldRef := ArchiveRecRef.FIELD(50001);  
          DestRec.V1Field := FldRef.VALUE;  
          DestRec.V2Field := 'NEW FIELD DEFAULT VALUE';  
          DestRec.INSERT;  
        UNTIL ArchiveRecRef.NEXT = 0;  
      END  
    END  
  END  
  ELSE BEGIN  
    // This is the reinstall (version 2 to version 2) block.  
    // Because the schema is the same for all minor versions of the version 2 product,  
    // you can copy the data in without changes.  
    NAVAPP.RESTOREARCHIVEDATA(50003);  
  END  
END;  
```  

> [!NOTE]  
>  The preceding sample code uses a strongly typed instance of the record for the destination. The other option is to use a RecordRef for both the source and destination. The sample code also assumes that any version 2 build of the extension uses the same table schema. If this is not true for your extension, you may have to use more specific version checks.  

> [!TIP]  
>  It is a best practice to use the `IF NAVAPP.GETARCHIVERECORDREF(50003, ArchiveRecRef) THEN BEGIN` construct to catch any exception that is thrown, for example, if a non-valid table was passed.  

### Load Default or Starting Table Data

If the table should always be populated with starting or default data that was included in the package, then use the `NAVAPP.LOADPACKAGEDATA(TableNo)` function to import the starting data to the table. If starting data is imported, then any archived data for the table will be deleted and not restored.

The following code example shows how to populate table 50004 with data.
```
PROCEDURE OnNavAppUpgradePerDatabase@1();
    BEGIN
        NAVAPP.LOADPACKAGEDATA(50004);
    END;
```

### Conditional Restore or Load Starting Table Data
In some situations, you may want to conditionally use different options. For example, say that if archive data exists for a new extension table, you want to restore that data. But if archive data doesn’t exist, you want to import starting data from the package. In this scenario you will want to check for the existence of an archive table using the NAVAPP.GETARCHIVERECORDREF(TableNo) function and if a RecordRef is returned then restore or upgrade the table. If a record isn’t returned, then use the function to import the starting data for the table.

Sample Code:
```
PROCEDURE OnNavAppUpgradePerDatabase@1();
    // Variables:
    // ArchiveRecRef 	RecordRef		
    BEGIN
      IF NAVAPP.GETARCHIVERECORDREF(50001, ArchiveRecRef) THEN
            NAVAPP.RESTOREARCHIVEDATA(50001)
        ELSE
                  NAVAPP.LOADPACKAGEDATA(50001);
    END;
```

## See Also  
[Extending Microsoft Dynamics NAV Using Extension Packages](Extending-Microsoft-Dynamics-NAV-Using-Extension-Packages.md)  
[Upgrading Extensions](extensions-upgrading.md)  
[GETARCHIVEVERSION Function](GETARCHIVEVERSION-Function.md)  
[GETARCHIVERECORDREF Function](GETARCHIVERECORDREF-Function.md)  
[RESTOREARCHIVEDATA Function](restorearchivedata-function.md)  
[DELETEARCHIVEDATA Function](deletearchivedata-function.md)  
[How to: Develop an Extension](How-to--Develop-an-Extension.md)  
[How to: Create an Extension Package](How-to--Create-an-Extension-Package.md)  
[Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)  
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)  
[Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)  
[Development](development.md)  
