---
title: "Editable Property"
ms.custom: na
ms.date: 06/13/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 10e8a6db-079f-4ac1-b589-245b1ad43196
caps.latest.revision: 18
ms.author: edupont
---
# Editable Property
Sets a value that indicates whether a field, page, or control can be edited through the UI.  

## Applies To  

-   Pages and group, part, and field controls  

-   Table fields  

## Property Value  
 **True** on pages if the field, page, or control can be edited; otherwise, **false** on pages. The default value is **true**.  

## Remarks  
 For fields, use this property to make a field for display only.  

 For controls, if the **Editable** property for the container that contains this control is set to **false**, then that setting overrides what you enter here.  

 If a page has **Editable** set to **false**, then the controls on the page are not editable, even if the individual **Editable** properties are set to **true**.  

 The property setting is checked during validation. Validation occurs only if the field or control value is updated through the UI, for example, if a value is updated on a page or if a field is updated in a table. If a field is updated through application code, then the **Editable** property is not validated.  

> [!NOTE]  
>  When using CurrPage.Editable, the **Editable** property also reflects the page mode that the page was opened in. This applies to Edit, Create, and Delete modes, but not to View mode. If the page is editable, then CurrPage.Editable will return **false**.  

 On pages, you use the **Editable** property for group, part, field, and action controls. You can make them editable or non-editable either statically by setting the property to **true** or **false**, or dynamically by using a Boolean variable or a Boolean field on the page. The Boolean field on the page can be either a true/false Boolean or a Boolean expression, such as “Credit Limit > Sales YTD”.  

> [!CAUTION]  
>  Do not use CurrPage.Editable to prevent users from deleting entries. We recommend that you use permissions to control which users can delete data.  

## See Also  
 [Properties](devenv-properties.md)   
 [Page Properties](devenv-page-properties.md)
