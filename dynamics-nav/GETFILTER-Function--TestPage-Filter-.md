---
title: "GETFILTER Function (TestPage Filter)"
ms.custom: na
ms.date: 03/13/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: f3137870-5c6b-46c1-9b0c-d126388b71fe
caps.latest.revision: 4
manager: edupont
---
# GETFILTER Function (TestPage Filter)
Gets the filter that is applied to the specified field in a dataset that is displayed on a test page.  
  
## Syntax  
  
```  
String := TestPage.Part.Filter.GETFILTER(Field);  
```  
  
#### Parameters  
 *TestPage*  
 Type: TestPage  
  
 The test page that displays the dataset that contains the specified field.  
  
 *Part*  
 Type: Part  
  
 The control on the test page that contains the dataset.  
  
 *Filter*  
 Type: Filter  
  
 The filter that is applied to the dataset.  
  
 *Field*  
 Type: Field  
  
 The field that you want to get the filter from.  
  
## Property Value/Return Value  
 Type: Text  
  
 The filter that is applied to the specified field.  
  
## See Also  
 [TestPage Filter Functions](TestPage-Filter-Functions.md)