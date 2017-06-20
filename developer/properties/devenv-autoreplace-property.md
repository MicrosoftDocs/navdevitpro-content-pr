---
title: "AutoReplace Property"
ms.custom: na
ms.date: 06/09/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6a09a5b0-1106-45a4-83b5-367138884339
caps.latest.revision: 11
author: SusanneWindfeldPedersen
---
# AutoReplace Property
Sets whether imported records automatically replace existing records with the same primary key.  
  
## Applies To  
 Data items in XMLports.  
  
## Property Value 
 **True** if the records are replaced; otherwise, **false**. The default value is **false**.  
  
## Remarks
 If a record with the same primary key is found in the database, then the record is initialized with the initial value for each field and then populated with the values in the imported record. Any field in the record that is not present in the imported record retains its initial value. For more information about initial values, see [InitValue Property](devenv-initvalue-property.md).  
  
> [!WARNING]  
>  If this property is set to **true**, then the [AutoUpdate Property](devenv-autoupdate-property.md) has no effect.  
  
## See Also  
 [AutoUpdate Property](devenv-autoupdate-property.md)   
 [AutoSave Property](devenv-autoSave-property.md)