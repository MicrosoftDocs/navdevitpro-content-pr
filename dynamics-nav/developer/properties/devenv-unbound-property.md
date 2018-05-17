---
title: "Unbound Property"
ms.custom: na
ms.date: 06/16/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: d0632b9c-70ba-4a30-8b4b-5283ebb11b90
caps.latest.revision: 5
redirect_url: /dynamics365/business-central/dev-itpro/developer/properties/devenv-properties
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# Unbound Property
Sets whether the element can be repeated an unknown number of times at runtime before the import or export moves on to the next element.  
  
## Applies To  
  
-   XMLports.  
  
## Property Value  
 **True** if the element can be unbound; otherwise, **false**. The default value is **false**.  
  
## Remarks  
 If you design an XMLport that is used to import or export data in different formats where the number of columns can vary, you can use this property to handle the number of columns.  
  
> [!WARNING]  
>  If this property is set to **true**, then your code for handling exports must specify when to break to the next element by using the **BREAKUNBOUND** method.  
>   
>  During an import, the XMLport will automatically move on to the next record when the code reaches a record separator.  
  
 For example, your XMLport can export data in two different file formats. One format contains 5 columns, and the other contains 10 columns. Instead of duplicating the maximum number of columns and writing code that skips any redundant columns, you can set up a single column, make it unbound, and then specify in code when to break to the next element.  
  
## See Also  
 [BREAKUNBOUND Method \(XMLport\)](../methods/devenv-BREAKUNBOUND-method-xmlport.md)