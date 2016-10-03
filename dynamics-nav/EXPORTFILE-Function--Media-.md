---
title: "EXPORTFILE Function (Media)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 0f180552-fae1-40fc-a72f-87da1c9d3f36
caps.latest.revision: 2
manager: edupont
---
# EXPORTFILE Function (Media)
Exports the current media type \(such as jpeg image\) that is used on record to a file on your computer or network. In the record, the media is referenced in a **Media** data type field.  

## Syntax  

```  
[Ok := ] Record.Media.EXPORTFILE(FileName)   
```  

#### Parameters  
 *Record*  
 Type: Record  

 Specifies the record that includes the media.  

 *Media*  
 Type: Media  

 Specifies the field of the record that includes the media. This field has the **Media** data type.  

 *FileName*  
 Type: Text  

 Specifies the full path and name of the file to create for the exported media.  

## Property Value/Return Value  
 Type: Boolean  

 **true** if the media was successfully exported; otherwise, **false**.  

## Remarks  
 The exported media file will be of the same media file type, such as .jpg or .gif, as it was when imported.  For more information about the media types, see [Supported Media Types](Working-With-Media-on-Records.md#SupportedMediaTypes).  

 If a file with the same name as the exported file already exists in the target folder and the current session has write access on the file, the existing file will be automatically replaced by the new file. If the export fails, the existing file will be erased.  

## Example  
 This example uses the EXPORTFILE to iterate over the **Item** table and export any media that is used on records to a file in a temporary folder. A separate file is created for each media.  

 This example assumes that **Item** table contains a **Media** data type field that is named **itemPicture**, and that you have imported some image files on records. For information about importing media, see [IMPORTFILE Function \(Media\)](IMPORTFILE-Function--Media-.md).  

 The example code requires that you create the following variables:  

|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
|FileName|Text| |  
|status|Boolean|  |  

 This code iterates over records in the **Items** table. If a record has a media reference in the *itemPicture* field, the media is exported to a file in the *C:\\image* folder and given a name in the format *ItemNNNN.jpg*, where *NNNN* is the actual item number in the database.  

```  
IF Item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    FileName := 'C:\images\' + 'Item'  + FORMAT(Item."No.") + '.jpg';  
    status := Item.itemPicture.EXPORTFILE(FileName);  
  UNTIL Item.NEXT < 1;  
END;  
```  

## See Also  
 [Working With Media on Records](Working-With-Media-on-Records.md)  
 [IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md)   
 [IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)   
 [EXPORTSTREAM Function \(Media\)](EXPORTSTREAM-Function--Media-.md)
