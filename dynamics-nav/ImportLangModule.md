---
title: "ImportLangModule"
author: edupont04
ms.custom: na
ms.date: 10/14/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e4d673a7-dbe3-43e7-bb88-baa4fd0047e6
caps.latest.revision: 9
manager: edupont04
---
# ImportLangModule
Imports a language module from a file to the specified [!INCLUDE[navnow](includes/navnow_md.md)] database.  

## Syntax  

```  
finsql.exe command=importlangmodule, file=<importfile>, [servername=<server>,] [database=<database>,] [filter=<filter>,] [logfile=<path and filename>,] [username=<username>,] [password=<password>,] [ntauthentication=<yes|no|1|0>]  
```  

#### Parameters  
 *file*  

 Specifies the path and file name of the language module to import. This parameter is required.  

 The file name should have the extension *.flm*, for example, *C:\\ENUlanguagemodule.flm*.  

 *servername*  

 The name of the database server that hosts the [!INCLUDE[navnow](includes/navnow_md.md)] database in which to import the language module. The format of this parameter is \<*computername*>\\\<*database server instance*>.  

 If you do not specify both the *servername* and the *database* parameter, then the database server and database that are stored in the fin.zup file are used.  

> [!NOTE]  
>  When you first specify a database server and database to open, either from a command at a command prompt or from a client, the database server and database are stored in the fin.zup file. By default, the fin.zup file is located at C:\\users\\\<*user name*>\\AppData\\Roaming\\.  

 If you do not specify the *servername* parameter but you do specify the *database* parameter, then the [Open Database](uiref/-$-S_2335-Open-Database-$-.md) window opens so that you can specify the database server name.  

> [!TIP]  
>  To view the name of the server on which the current database is stored, on the **File** menu, choose **Database**, and then choose **Information**. Use the value of the **Database Server** field for the *servername* parameter.  

 *database*  

 The name of the [!INCLUDE[navnow](includes/navnow_md.md)] database in which to import the language module.  

 If you do not specify both the *servername* and the *database* parameter, then the database server and database that are stored in the fin.zup file are used.  

> [!NOTE]  
>  When you first specify a database server and database to open, either from a command at a command prompt or from a client, the database server and database are stored in the fin.zup file. By default, the fin.zup file is located at C:\\users\\\<*user name*>\\AppData\\Roaming\\.  

 If you do not specify the *database* parameter but you do specify the *servername* parameter, then the [Open Database](uiref/-$-S_2335-Open-Database-$-.md) window opens so that you can specify the database name.  

> [!TIP]  
>  To view the name of the current database, on the **File** menu, choose **Database**, and then choose **Information**. Use the value of the **Database Name** field for the *database* parameter.  

 *filter*  

 A filter on the **Object** table. Use the *filter* parameter to specify the objects to which you want to import the language module. Use a semicolon to separate multiple filters. The only operator that you can use in the filter is '='. The following table shows the fields in the **Object** table on which you can filter.  

|Object table field|Values|Example|  
|------------------------|------------|-------------|  
|Type|Table, Codeunit, Page, Report, XMLport, Query|Type=Table&#124;Page|  
|ID|Integer or range of integers|ID=50000..50500|  
|Name|Any valid object name|"Name=Cost Entry"|  
|Modified|yes, no, 1, 0|Modified=yes|  
|Compiled|yes, no, 1, 0|Compiled=0|  
|Date|Date, in the numeric format determined by your regional settings|Date=12/1/2012|  
|Time|Time, in the numeric format determined by your regional settings|Time=12:00:00|  
|Version List|Any valid version|Version List=NAVW17.00|  
|Caption|Any valid caption|Caption=Company Information|  
|Locked|Yes, no, 1, 0|Locked=1|  
|Locked By|Domain\\username|"Locked By=CRONUS\\viktor"|  

 If you do not specify a filter, then all objects in the **Object** table are included.  

 *logfile*  

 The path and file name for the file that contains error messages that result from the command. If there are no errors, then a log file is not created.  

 By default, the file is named naverrorlog.txt and is located in the same location as finsql.exe.  

 The navcommandresult.txt file, which contains information about the success or failure of the command, is created in the folder that is specified by the *logfile* parameter.  

 When you run finsql.exe with a command, the previous log file and result file are deleted.  

> [!NOTE]  
>  If User Access Control \(UAC\) is turned on and you do not specify to run the command prompt window as Administrator, then the command prompt window runs as a standard user. In this case, if you do not specify the *logfile* parameter, then the command fails because the standard user cannot write to the default location of the log file.  

 *username*  

 The user name to use to authenticate to the database. The user name must exist in the database. If you do not specify a user name and password, then the command uses the Windows user name and password of the current user to authenticate to the database.  

> [!NOTE]  
>  If User Access Control \(UAC\) is turned on, and you do not specify to run the command prompt window as Administrator, then the command prompt window runs as a standard user. In this case, if you do not specify the *username* parameter, then even if the current Windows user is an Administrator, the command is run as the standard user.  

 If you specify the *username* parameter, then you must also specify the *password* parameter and the *ntauthentication* parameter must be **no**.  

 For more information about database users and permissions, see [Setting Database Owner and Security Administration Permissions](Setting-Database-Owner-and-Security-Administration-Permissions.md).  

 *password*  

 The password to use with the *username* parameter to authenticate to the database. If you do not specify a user name and password, then the command uses the Windows user name and password of the current user to authenticate to the database.  

 *ntauthentication*  

 Specifies whether to use NT authentication. The possible values are **yes**, **no**, **1**, or **0**. If you specify the *username* and *password* parameters, then you must specify **ntauthentication=no** or **ntauthentication=0**.  

## Remarks  
 You can specify parameters in any order.  

## Example  
 This example shows how to run the ImportLangModule command to import a language module for Danish \(DAN\) to the *Demo Database NAV \(10-0\)* database. The language module file path is *C:\\DANlanguagemodule.flm*.  

```  
finsql.exe command=importlangmodule, file=C:\DANlanguagemodule.flm, servername=TestComputer01\NAVDEMO, database="Demo Database NAV (10-0)"  
```  

## See Also  
 [BuildVirtualMetadata](BuildVirtualMetadata.md)   
 [CreateDatabase](CreateDatabase.md)   
 [UpgradeDatabase](UpgradeDatabase.md)   
 [CreateLanguage](CreateLanguage.md)   
 [CompileObjects](CompileObjects.md)   
 [Compiling Objects](Compiling-Objects.md)   
 [DeleteObjects](DeleteObjects.md)   
 [DesignObject](DesignObject.md)   
 [ExportObjects](ExportObjects.md)   
 [ImportObjects](ImportObjects.md)   
 [ExportLangModule](ExportLangModule.md)   
 [ExportTranslate](ExportTranslate.md)   
 [ImportTranslate](ImportTranslate.md)   
 [Using the Development Environment from the Command Prompt](Using-the-Development-Environment-from-the-Command-Prompt.md)
