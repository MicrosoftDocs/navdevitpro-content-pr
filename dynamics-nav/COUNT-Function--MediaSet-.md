---
title: "COUNT Function (MediaSet)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4dab6c93-efcd-47ae-bf85-9cbcaf94b994
caps.latest.revision: 4
---
# COUNT Function (MediaSet)
Counts the number of media files that are included in the MediaSet of a record. The MediaSet defines a collection of media files that are assigned to a record which can be displayed in the client.  
  
## Syntax  
  
```  
  
Number := Record.MediaSet.COUNT  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record.  
  
 MediaSet  
 Type: MediaSet  
  
 Specifies the MediaSet data type field for the record.  
  
## Property Value\/Return Value  
 Type: Integer  
  
 The number of media files that are associated with the MediaSet of the record.  
  
## Example  
 This example is counts the number of media files for item No. 1000 in the **Item** table. The field in the **Item** table that is used for the MediaSet data type is **MediaSetField**.  
  
 This code requires you to create the following variables..  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|item|Record|Item|  
|count|Integer||  
  
 This code requires you to create the following text constants.  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|The number of media files: %1|  
  
```  
Item.GET('1000');  
    count := (item.MediaSetField.COUNT);  
    MESSAGE(Text001,count);  
```  
  
## See Also  
 [MediaSet Data Type](../dynamics-nav/MediaSet-Data-Type.md)   
 [MEDIAID Function \(MediaSet\)](../dynamics-nav/MEDIAID-Function--MediaSet-.md)   
 [IMPORTFILE Function \(MediaSet\)](../dynamics-nav/IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](../dynamics-nav/IMPORTSTREAM-Function--MediaSet-.md)