---
title: "EXPORTSTREAM Function (Media)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4e4b21e5-d738-4db6-b78b-218a48b96e09
caps.latest.revision: 2
---
# EXPORTSTREAM Function (Media)
Export the current media type \(such as jpeg image\) that is used on record to an OUTSTREAM object  
  
 . The OUTSTREAM object can be created from a BLOB field, a FILE or from a .NET Framework interoperability object. In the record, the media is referenced in a **Media** data type field.  
  
## Syntax  
  
```  
[Ok := ] Record.Media.EXPORTSTREAM(OutStream)  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that includes the media.  
  
 Media  
 Type: Media  
  
 Specifies the field of the record that includes the media.  
  
 *OutStream*  
 Type: OutStream  
  
 Specifies the OutStream object that is created by the object that will receive the media content.  
  
## Property Value\/Return Value  
 Type: Boolean  
  
 **true** if the media was successfully exported; otherwise, **false**.  
  
## Remarks  
 The OutStream object must be a valid and writeable stream that is created by the receiving object. The EXPORTSTREAM function does not create the OutStream object. It only uses the object for writing data.  
  
## Example  
 This example uses the EXPORTSTREAM to iterate over the **Items** table and export any media that is used on records to an OutStream that is created on a file object.  
  
 This example assumes that **Item** table contains a **Media** data type field that is named **itemPicture**, and that you have imported some image files on records. For information about importing media, see [IMPORTFILE Function \(Media\)](../dynamics-nav/IMPORTFILE-Function--Media-.md).  
  
 The example code requires that you create the following variables:  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
|FileName|Text||  
|status|Boolean||  
|DataOutStream|||  
  
```  
IF Item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    FileName := 'C:\images\' + 'ItemPictureFromStream' + FORMAT(Item."No.") + '.jpg';  
    DataFile.CREATE(FileName);  
    DataFile.CREATEOUTSTREAM(DataOutStream);  
    status := Item.ItemPicture.EXPORTSTREAM(DataOutStream);  
    DataFile.CLOSE;  
  UNTIL Item.NEXT < 1;  
END;  
  
```  
  
## See Also  
 [Working With Media on Records](../dynamics-nav/Working-With-Media-on-Records.md)   
 [IMPORTSTREAM Function \(Media\)](../dynamics-nav/IMPORTSTREAM-Function--Media-.md)   
 [IMPORTFILE Function \(MediaSet\)](../dynamics-nav/IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](../dynamics-nav/IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](../dynamics-nav/MediaSet-Data-Type.md)   
 [EXPORTFILE Function \(Media\)](../dynamics-nav/EXPORTFILE-Function--Media-.md)