---
title: "OnFindRecord Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-financials"
ms.assetid: d27b1678-5656-4483-9fbe-b6278e0cffc4
caps.latest.revision: 6
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnFindRecord Trigger
Overrides the default page behavior and enables you to specify which record you want to display when the page opens.  
  
## Syntax  
  
```  
  
[Ok]:= OnFindRecord(Which)  
```  
  
#### Parameters  
 *Which*  
  
 Text or code value with the following options:  
  
|Parameter Value|Result|  
|---------------------|------------|  
|- \(a dash\)|First record|  
|+ \(a plus sign\)|Last record|  
|=>\<|Record defined in the `Rec` variable or the closest match|  
  
## Return Value  
 *Ok*  
  
 \(Boolean\) Indicates whether the specified record was found.  
  
|Value|Result|  
|-----------|------------|  
|true|Found|  
|false|Not found (default)|  
  
## Applies To  
  
-   Pages  
  
## Remarks  
 By default, opened pages display the last record shown when the user exited the page. Use this trigger to override the default behavior and display the first record, last record, or a specific record as defined in the `Rec` variable.  
  
## See Also  
 [Triggers](devenv-triggers.md)