---
title: "FieldDelimiter Property"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0a30827a-bbd7-4894-ba9f-9bb20caef174
caps.latest.revision: 7
manager: terryaus
---
# FieldDelimiter Property
Specifies the text delimiter for a field.  
  
## Applies To  
  
-   XMLports  
  
## Remarks  
 The default value is “”, an empty string.  
  
 You can set the field delimiter in C\/AL code so that the XMLport can import and export records with different delimiters. For example, if your XMLport must import from a file or stream where one record uses commas and another uses an empty string, you can change the field delimiter property at run time.  
  
## See Also  
 [Properties](Properties.md)