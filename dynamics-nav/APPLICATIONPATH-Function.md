---
title: "APPLICATIONPATH Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6fb5a2e1-5eb8-44c1-8247-33643182cf22
caps.latest.revision: 6
manager: pchapman
---
# APPLICATIONPATH Function
Returns the path of the directory where the executable file for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] is installed.  
  
## Syntax  
  
```  
  
APPLICATIONPATH  
```  
  
## Remarks  
 This function returns a string that contains the path of the directory where the executable file for [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] is installed. This string ends with a backslash \('\\'\) and does not contain the name of the executable file.  
  
 The string cannot contain more than 255 characters.  
  
 If this function is called from an application that is running on a [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Application Server, it returns the path of the directory where the [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] Application Server is installed.  
  
## See Also  
 [GUIALLOWED Function](../dynamics-nav/GUIALLOWED-Function.md)   
 [HYPERLINK Function](../dynamics-nav/HYPERLINK-Function.md)   
 [SLEEP Function](../dynamics-nav/SLEEP-Function.md)   
 [TEMPORARYPATH Function](../dynamics-nav/TEMPORARYPATH-Function.md)