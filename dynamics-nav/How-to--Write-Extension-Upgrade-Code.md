---
title: "How to: Write Extension Upgrade Code"
author: edupont04
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: f76ac1a0-9529-4c87-bad2-b468f3f95506
caps.latest.revision: 2
---
# How to: Write Extension Upgrade Code
The process of upgrading an extension includes uninstalling the current version of the extension and then installing a new version. If the extension modifies the schema of an existing table, or adds new tables, upgrade code will be required to handle the data that was automatically archived from the tables during uninstall.



## To write upgrade code for an extension
1.	Add a new codeunit.

> [!NOTE]  
>  Do not create this codeunit as an upgrade codeunit.

2.	Add upgrade functions to the codeunit.  
    1. Add the *OnNavAppUpgradePerDatabase()* function if the extension contains cross-company tables. Make sure the function is declared as global so that the **Local** property is set to **No**.  
    2. Add the *OnNavAppUpgradePerCompany()* function if the extension contains per-company tables. Make sure the function is declared as global so that the **Local** property is set to **No**.  

3.	Add the upgrade code to the relevant function.
    The upgrade code you add will depend on what you need to do with the archived data. What you need to do may depend on many factors including the version of the archive data, whether the schema has changed and whether the data can be modified by users. Determine which of the following upgrade methods is required for each new or modified table in your extension.

    1. Restore table data

    If the table has the same schema as the archive data and doesn’t require any special upgrade logic, then use the NAVAPP.RESTOREARCHIVEDATA (TableNo) system function to copy the data back. The data to copy back may be for new tables added as part of the extension or for fields added to existing base NAV tables.  

    Sample Code:
    ```
    PROCEDURE OnNavAppUpgradePerCompany@1();
    BEGIN
      NAVAPP.RESTOREARCHIVEDATA(50000);
      NAVAPP.RESTOREARCHIVEDATA(50001);
    END;
    ```

    2. Delete table data

    If the table data doesn’t need to be restored, then use the NAVAPP.DELETEARCHIVEDATA(TableNo) system function to delete the archive data.

    Sample Code:
    ```
    PROCEDURE OnNavAppUpgradePerCompany@1();
    BEGIN
      NAVAPP.DELETEARCHIVEDATA(50002);
           END;
   ```

    3. Upgrade table data
    If the archive data is from a previous version and requires special upgrade logic, then use custom code to upgrade the records retrieved from the archive tables. The two system functions that provide access to the archived data are:

    |Function|Description|
    |--------|-----------|
    |[Version :=] NAVAPP.GETARCHIVEVERSION()|Returns the extension version.|  
    |[Ok :=] NAVAPP.GETARCHIVERECORDREF(TableNo, VAR RecordRef)|Returns a RecordRef for the table identified.|  

    Sample Code:
    ```
    PROCEDURE OnNavAppUpgradePerCompany@1();
    // Variables:
    // ArchiveRecRef 	RecordRef		
    // FldRef 			FieldRef		
    // DestRec  			Record
    // Version	  		Text 20
    Version := NAVAPP.GETARCHIVEVERSION();
    IF Version < '2.0.0.0' THEN BEGIN
      // The V1 -> V2 upgrade block. Copy over relevant old        //   fields and initialize new fields using archive data.
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
      // The reinstall (V2 -> V2) block. Since we know the schema is the same for all minor versions of the V2 product, we can copy the data in without changes.
      NAVAPP.RESTOREARCHIVEDATA(50003);
    END
    ```
    > [!NOTE]  
    >  The sample code above uses a strongly typed instance of the record for the destination. The other option is to use RecordRef for both the source and destination. The sample code also assumes that any version 2 build of the extension uses the same table schema, if that is not true for your extension you may need to use more specific version checks.  
    > Also, as a best practice, we recommend that you use the GETARCHIVERECORDREF function to catch if an exception is thrown, such as if an invalid table was passed.
    > `IF NAVAPP.GETARCHIVERECORDREF(50003, ArchiveRecRef) THEN BEGIN`

    4. Load default or starting table data
    If the table should always be populated with starting or default data that was included in the package, then use the `NAVAPP.LOADPACKAGEDATA(TableNo)` function to import the starting data to the table. If starting data is imported, then any archived data for the table will be deleted and not restored.

    Sample Code:
    ```
    PROCEDURE OnNavAppUpgradePerDatabase@1();
        BEGIN
        NAVAPP.LOADPACKAGEDATA(50004);
        END;
    ```
    5. Conditional restore or load starting table data
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
[How to: Develop an Extension](How-to--Develop-an-Extension.md)  
[How to: Create an Extension Package](How-to--Create-an-Extension-Package.md)  
[Comparing and Merging Application Object Source Files](Comparing-and-Merging-Application-Object-Source-Files.md)   
[Microsoft Dynamics NAV Windows PowerShell Cmdlets](Microsoft-Dynamics-NAV-Windows-PowerShell-Cmdlets.md)   
[Development Cmdlets for Microsoft Dynamics NAV](http://go.microsoft.com/fwlink/?LinkID=510540)  
[Development](development.md)  
