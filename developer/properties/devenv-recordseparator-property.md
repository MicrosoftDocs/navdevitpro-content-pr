---
title: "RecordSeparator Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 88f67ba0-2aa4-42c3-a6fb-f5546b31b22d
caps.latest.revision: 10
---
# RecordSeparator Property
Sets the string that is to be used to separate records.  
  
## Applies To  
  
-   XMLports  
  
## Property Value  
  
|**Value**|**Description**|  
|---------------|---------------------|  
|**\<None>**|There will no be RecordSeparator.|  
|**\<NewLine> \(default\)**|Any combination of CR and LF characters.|  
|**\<CR/LF>**|CR followed by LF.|  
|**\<CR>**|CR alone.|  
|**\<LF>**|LF alone.|  
|**\<TAB>**|Tabulator alone.|  
|**Other strings**|The literal string entered.|  
  
## Remarks  
 The strings in the preceding table must be entered literally, that is, the **\<** and **>** characters must be entered. These special strings can be combined and can be mixed with other characters.  
  
 CR refers to the character with ASCII value 13.  
  
 LF refers to the character with ASCII value 10.  
  
 You can set the record separator in AL code so that the XMLport can import and export records with different separators. For example, if your XMLport must import from a file or stream where one record uses **NewLine** and another uses **TAB**, you can change the record separator at run time.  
  
## See Also  
 [Properties](devenv-properties.md)