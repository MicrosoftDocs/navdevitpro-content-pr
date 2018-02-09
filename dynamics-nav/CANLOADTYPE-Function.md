---
title: "CANLOADTYPE Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 9b8a593c-0a96-4e09-97c6-00cb4311dbe6
caps.latest.revision: 2
---
# CANLOADTYPE Function
Tests if the specified .NET Framework type can be loaded by [!INCLUDE[navnow](includes/navnow_md.md)].  

 You can use the CANLOADTYPE function to test the availability of assemblies that are expected to be present on the [!INCLUDE[navnow](includes/navnow_md.md)] client computer or on the [!INCLUDE[nav_server](includes/nav_server_md.md)] computer.  

## Syntax  

```  

Ok := CANLOADTYPE(DotNet)  
```  

#### Parameters  
 *DotNet*  
 Type: A variable of the DotNet data type to represent the .NET Framework type.  

## Property Value/Return Value  
 Returns **true** if the specified type can be accessed by [!INCLUDE[navnow](includes/navnow_md.md)]; otherwise **false**.  

## Example  
 The following code example is based on codeunit 5300 in the [!INCLUDE[demolong](includes/demolong_md.md)]. This example requires that you create the following variable and text constant in the C/AL Globals window.  

|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|OObjLibrary|DotNet|Microsoft.Dynamics.NAV.OLSync.OLSyncSupplier.OutlookObjectLibrary.'Microsoft.Dynamics.NAV.OLSync.OLSyncSupplier, Version=7.1.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'|  

|Text constant name|ConstValue|  
|------------------------|----------------|  
|MyError|Cannot access the specified type.|  

```  
IF NOT CANLOADTYPE(OObjLibrary) THEN  
   ERROR(MyError);  
```  

## See Also  
 [Calling .NET Framework Members from C/AL](Calling-.NET-Framework-Members-from-C-AL.md)
