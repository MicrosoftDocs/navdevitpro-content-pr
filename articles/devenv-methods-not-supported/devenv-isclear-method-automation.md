---
title: "ISCLEAR Method (Automation)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 4efc480e-c2d1-451d-a7c4-6ee84360998d
caps.latest.revision: 17
manager: edupont
---
# ISCLEAR Method (Automation)
Checks whether an Automation object has been created or cleared.  
  
## Syntax  
  
```  
  
Ok := ISCLEAR(Automation)  
```  
  
#### Parameters  
 *Automation*  
 Type: Automation  
  
 A variable that has previously been declared.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if any of the following is true; otherwise, **false**:  
  
-   The Automation variable has not been created. See [CREATE Method \(Automation\)](devenv-CREATE-Method-Automation.md).  
  
-   The Automation variable has been cleared. See [CLEAR Method](devenv-CLEAR-Method.md).  
  
-   The Automation variable has been assigned NULL by an Automation server.  
  
## Remarks  
 This method is not supported in the [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
## Example  
 The following example shows how you can use the ISCLEAR method. This example requires that you create the following variables.  
  
|Name|DataType|Subtype|  
|----------|--------------|-------------|  
|Document|Automation|'Microsoft XML, V3.0'.DOMDocument|  
|ReturnValue|Boolean|Not applicable|  
  
```  
ReturnValue := ISCLEAR(Document);  
// ReturnValue will be TRUE.  
CREATE(Document);  
ReturnValue := ISCLEAR(Document);  
// ReturnValue will be FALSE.  
CLEAR(Document);  
ReturnValue := ISCLEAR(Document);  
// ReturnValue will be TRUE.  
```  
  
## See Also  
 [Automation Data Type](Automation-Data-Type.md)