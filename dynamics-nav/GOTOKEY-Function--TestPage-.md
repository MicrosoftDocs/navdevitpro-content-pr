---
title: "GOTOKEY Function (TestPage)"
ms.custom: na
ms.date: 06/04/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e880f74c-c0a9-498f-8c91-bfcf207680bf
caps.latest.revision: 3
manager: terryaus
---
# GOTOKEY Function (TestPage)
Finds the row in a dataset on the test page that is identified by the specified values.  
  
## Syntax  
  
```  
[Ok :=]TestPage.GOTOKEY([Value],...);  
```  
  
#### Parameters  
 *TestPage*  
 Type: TestPage  
  
 The test page that contains the dataset.  
  
 *Value*  
 Type: Text or Integer  
  
 The value or list of values to use to find the row. If this parameter is omitted, the primary key value is used.  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if the specified row is found; otherwise, **false**. The return value is optional.  
  
## See Also  
 [TestPage Functions](../dynamics-nav/TestPage-Functions.md)