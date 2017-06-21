---
title: "DecimalPlaces Property"
ms.custom: na
ms.date: 06/12/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0cb9434-57f4-4f39-a8a2-66800a2a8822
caps.latest.revision: 14
author: SusanneWindfeldPedersen
---

# DecimalPlaces Property
Sets display and storage requirements for the [Decimal Data Type](../datatypes/devenv-decimal-data-type.md).  
  
## Applies To  
  
-   Page Fields  
  
-   Report Columns  
  
## Property Value  
 You can enter minimum, maximum, or both values for the number of decimal places, as shown in the following examples.  
  
|Value|Description|  
|-----------|---------------------------------------|  
|**1**|A minimum of 1 and a maximum of 1 decimal place.|  
|**1:4**|A minimum of 1 and a maximum of 4 decimal places.|  
|**2:**|At least 2 decimal places.|  
|**:2**|No more than 2 decimal places.|  
  
## Remarks  
 For decimal fields, this property specifies the number of decimal places that you want to store. The default storage requirements for [Decimal Data Type](../datatypes/devenv-decimal-data-type.md) are two decimal places for amounts. Use this property to specify storage requirements that are different than the default.  
  
 This setting is evaluated on text boxes and fields during validation.  
  
 When you create a new field of [Decimal Data Type](../datatypes/devenv-decimal-data-type.md), the value is automatically formatted as a currency. If your decimal field does not contain a currency value, then you can use this property to determine the number of decimal places that appear on the screen. For example, in the G/L Entry table, the DecimalPlaces property of field 42, Quantity, is set to 0:5. The minimum number of decimal places that you can enter is 0 and the maximum is 5.  
  
## See Also  
 [Decimal Data Type](../datatypes/devenv-decimal-data-type.md)   