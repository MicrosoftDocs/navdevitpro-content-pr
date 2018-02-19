---
title: "ExternalType Property"
description: Specifies the name of the orginal table in the external database. 
ms.custom: na
ms.date: 02/13/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: ddde23c8-cc94-4b5b-a5d7-83595ea4943a
caps.latest.revision: 2
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# ExternalType Property
Specifies the data type of the corresponding field in the external database. 

## Applies To  

-   Fields 
-   Tables

## Property Value  
The data type of the corresponding field value in the external database.  

## Remarks  
This property is used when you specify **CRM** or **ExternalSQL** in the **TableType** property. These tables use a different SQL Server connection than the normal tables in the [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](../includes/navnow_md.md)] database.  

## See Also  
[TableType Property](devenv-tabletype-property.md)   
[ExternalSchema Property](devenv-externalschema-property.md)   
[Name Property](devenv-name-property.md)   
[Properties](devenv-properties.md)   

