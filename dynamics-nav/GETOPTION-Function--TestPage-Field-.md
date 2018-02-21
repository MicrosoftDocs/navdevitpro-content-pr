---
title: "GETOPTION Function (TestPage Field)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 0c3625be-1ef8-41f9-ab81-1e19515daf10
caps.latest.revision: 4
manager: edupont
---
# GETOPTION Function (TestPage Field)
Gets the options for a field on a test page.  
  
## Syntax  
  
```  
Text := TestPage.Field.GETOPTION([Index]);  
```  
  
#### Parameters  
 *TestPage*  
 Type: TestPage  
  
 The test page variable that you use to refer to the test page.  
  
 *Field*  
 Type: Field  
  
 The field for which you to get the options.  
  
 *Index*  
 Type: Integer  
  
 The index of the field that you want to get the options from. This parameter is optional.  
  
## Property Value/Return Value  
 Type: Text  
  
 The options in the field.