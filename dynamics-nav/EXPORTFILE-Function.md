---
title: "EXPORTFILE Function"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 62c90423-764c-451b-ad12-8d8e6c0dd4e1
caps.latest.revision: 3
manager: edupont
---
# EXPORTFILE Function
Exports the media objects in the current media set of a record to individual files on your computer or network. In the record, the media set is referenced in a **MediaSet** data type field.  
  
## Syntax  
  
```  
[Count := ]Record.MediaSet.EXPORTFILE(FileNamePrefix)  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that includes the media set.  
  
 *MediaSet*  
 Type: Media  
  
 Specifies the **MediaSet** data type field of the record that includes the media.  
  
 *FileNamePrefix*  
 Type: Text  
  
 Specifies the location and name of the exported media files.  
  
 Each exported media file is given a name that consists of a prefix that you specify, plus an index number that is automatically assigned. The file name has the format *prefix*\-*index*.*type*, for example, Image\-1.jpg, Image\-2.jpg, and Image\-3.jpg. To set the parameter value, use the format: *path*\\*prefix*.*type*.  
  
-   *path* is the folder path where you want to store the files.  
  
-   *prefix* is the text that you want before the index number.  
  
-   *type* is the media type extension.  
  
## Property Value\/Return Value  
 Type: Integer  
  
 The number of media files that were generated and stored in the output file path.  
  
## Remarks  
 The exported media files will be of the same media file type as when they were imported, such as .jpg or .gif. For more information about the media types, see [Supported Media Types](../dynamics-nav/Working-With-Media-on-Records.md#SupportedMediaTypes). The function has the following behavior:  
  
-   If a file that has the same name as the exported file already is located in the target folder and the current session has write access on the file, the existing file will be automatically replaced by the new file.  
  
-   If the export fails, the existing file will be erased.  
  
-   If a media in the media set cannot be found in the database, no file will be generated for this object.  
  
## Example  
 This example imports three image files from a local folder into the media set of a record in the **Item** table. Then, the media objects are exported to another local folder. This example assumes that **Item** table contains a **MediaSet** data type field that is named **itemGallery**.  
  
 The example code requires that you create the following variables:  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
|MediaCount|Boolean||  
  
 This code imports the image \(.jpg\) files from the folder *C:\\images* to the first record in the **Item** table, and then exports the media files to the folder *C:\\images\\export*.  
  
```  
// Import three image files the C:\images folder.  
IF Item.FINDFIRST() THEN  
BEGIN  
  Item.ItemGallery.IMPORTFILE('C:\images\FirstItemA.jpg', 'Gallery A');  
  item.ItemGallery.IMPORTFILE('C:\images\FirstItemA.jpg', 'Gallery B');  
  item.ItemGallery.IMPORTFILE('C:\images\FirstItemC.jpg', 'Gallery C');  
  Item.MODIFY;  
END;  
COMMIT;  
  
// Export the MediaSet to three separate image files in the c:\images\export folder.  
IF Item.FINDFIRST() THEN  
BEGIN  
  MediaCount := Item.ItemGallery.EXPORTFILE('C:\images\export\' + 'FirstItemGallery.jpg');  
END;  
Message('Exported %1 files', MediaCount);  
```  
  
 The folder *C:\\images\\export* will contain these files: FirstItemGallery\-1.jpg, FirstItemGallery\-2.jpg, and FirstItemGallery\-3.jpg.  
  
## See Also  
 [Working With Media on Records](../dynamics-nav/Working-With-Media-on-Records.md)   
 [IMPORTSTREAM Function \(Media\)](../dynamics-nav/IMPORTSTREAM-Function--Media-.md)   
 [IMPORTFILE Function \(MediaSet\)](../dynamics-nav/IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](../dynamics-nav/IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](../dynamics-nav/MediaSet-Data-Type.md)   
 [EXPORTSTREAM Function \(Media\)](../dynamics-nav/EXPORTSTREAM-Function--Media-.md)   
 [EXPORTFILE Function \(Media\)](../dynamics-nav/EXPORTFILE-Function--Media-.md)