---
title: "ExternalAccess Property"
ms.custom: na
ms.date: 02/09/2018
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

# ExternalAccess Property
Specifies the access permission level of the table in the external database.  

 Specify this property if the original name is different from the name that you specify in the **Name** property. This means that you can use a different name for the table in [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)].  

## Applies To  

-   Fields  

## Property Values  
 
|Property value| Description|
|------|-----------|
|Full  |Allows the full access to the external database.|
|Insert|Allows the insert access to the table fields in the external database.|
|Modify|Allows the Modify access to the external database. |
|Read  |Allows the read-only access to the external database.|

## Remarks  
 This property appears when you specify **CRM** in the **TableType** property. These tables use a different SQL Server connection than the normal tables in the [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] and [!INCLUDE[navnow_md](../includes/navnow_md.md)] database.  

## See Also  
 [TableType Property](devenv-tabletype-property.md)   
 [ExternalSchema Property](devenv-externalschema-property.md)   
 [Name Property](devenv-name-property.md)   
 [Properties](devenv-properties.md)   