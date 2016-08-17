---
title: "HASVALUE Function (Media)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0ab5b55d-2fb7-493c-93f4-8c88eec28acd
caps.latest.revision: 3
manager: edupont
---
# HASVALUE Function (Media)
Checks whether a **Media** data type field in a record has been initialized with a media object and that the specified media object exists in the database.  
  
## Syntax  
  
```  
HasValue := Record.Media.Media.HASVALUE  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that includes the media set.  
  
 *Media*  
 Type: Media  
  
 Specifies the **MediaSet** data type field of the record that includes the media.  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if the **Media** data type field has media data; otherwise, **false**.  
  
## Exceptions  
  
## Remarks  
  
## Example  
 This example uses the HASVALUE function to iterate over the **Item** table to determine whether media objects are available on records.  
  
 This example assumes that **Item** table contains a **Media** data type field that is named **itemPicture**, and that you have imported some image files on records. For information about importing media, see [IMPORTFILE Function \(Media\)](../dynamics-nav/IMPORTFILE-Function--Media-.md).  
  
 The example code requires that you create the following variable:  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
  
 The following code returns a message if a record does not include a media object.  
  
```  
IF Item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    If NOT Item.ItemPicture.HASVALUE THEN  
      ERROR('Item %1 does not have a valid media attached', Item."No.");  
  UNTIL Item.NEXT < 1;  
END;  
```  
  
## See Also  
 [Working With Media on Records](../dynamics-nav/Working-With-Media-on-Records.md)   
 [IMPORTSTREAM Function \(Media\)](../dynamics-nav/IMPORTSTREAM-Function--Media-.md)   
 [IMPORTFILE Function \(MediaSet\)](../dynamics-nav/IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](../dynamics-nav/IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](../dynamics-nav/MediaSet-Data-Type.md)   
 [EXPORTSTREAM Function \(Media\)](../dynamics-nav/EXPORTSTREAM-Function--Media-.md)