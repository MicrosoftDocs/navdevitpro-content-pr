---
title: "IMPORTFILE Function (Media)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: aeffd2de-fe20-4900-9253-de23b58e7696
caps.latest.revision: 6
manager: edupont
---
# IMPORTFILE Function (Media)
Adds a media type, such as a jpeg image, from a file to a **Media** data type field of a record for displaying the media with the record in the client. The media file is imported to the application database and a reference to the media is included in the **Media** data type field.  
  
## Syntax  
  
```  
  
[GUID] := ]Record.Media.IMPORTFILE(FileName ,Description[, MimeType])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that you want to add the media to.  
  
 Media  
 Type: Media  
  
 Specifies the field that you want to add the media to. This field has the **Media** data type.  
  
 *FileName*  
 Type: Text  
  
 Specifies the full path and name of the media file to be added.  
  
 *Description*  
 Type: Text  
  
 Specifies text that can be used in the client to describe the media.  
  
 *MimeType*  
 Type: Text  
  
 Specifies the content type of the media file. The *MimeType* value must be a two\-part string that consists of a type and subtype, such as *image\/jpeg*, *image\/gif*, or *video\/mpeg*. For more information, see [Supported Media Types](Working-With-Media-on-Records.md#SupportedMediaTypes).  
  
 If this parameter is not specified, the IMPORTFILE function will deduct the MIME type from the file extension. For example the MIME type for a .jpg file is image\/jpeg.  
  
## Property Value\/Return Value  
 Type: GUID  
  
 The unique ID assigned to this media instance in the database. You can also get the ID by using the [MEDIAID Function \(Media\)](MEDIAID-Function--Media-.md).  
  
## Remarks  
 You use this function to upload a media file, which you want to associate with a record, to the database. For example, you can upload an image of all items in table **27 Item**. When a media file is imported, it is assigned a unique identifier \(GUID\) and stored in the system table **2000000183 Tenant Media** of the application database. The GUID is then included in the **Media** data type field as a reference to the media file.  
  
 If you import a media file into a record that already has a media object, and the modify operation is performed, the previous media object will be permanently deleted, unless there are other references to the media object in the same table field.  
  
## Example  
 This example uses the IMPORTFILE function to add images to records in table **27 Item** of the [!INCLUDE[demolong](includes/demolong_md.md)]. After the images are imported, they will be displayed with items on page **31 Item List**, when the page is opened in the [!INCLUDE[nav_web](includes/nav_web_md.md)] and viewed in a brick layout. The example uses C\/AL code to iterate over records in the **Items** table and import an image file for records from a local folder. To support the example code that follows, you have to complete these tasks:  
  
-   Create the item image files and save them on the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)] instance.  
  
     Save the images as .jpg type, and give them names that correspond to item numbers \(as specified by the **No.** field\), such as, 1000.jpg, 1001.jpg, 1100.jpg, and so on. For this example, save the files in the folder *C:\\images*.  
  
-   In the **Item** table, add a new field that has the data type **Media**.  
  
     For this example, name the field **itemPicture**. To make the media field visible in the [!INCLUDE[nav_web](includes/nav_web_md.md)], include the field in the table field group that is named **Brick**.  
  
-   In the **Item List** page, add a column for the **Media** field.  
  
 With these tasks in place, you can add and run the following C\/AL code to import the images. For this code example, create a codeunit and add the code to the OnRun trigger. But, you could also add the code other places instead, such as on an action in the **Item List** page.  
  
 The code requires that you create the following variables:  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
|FileName|Text||  
  
 This code iterates over records in the **Items** table. For each record, it looks in the *C:\\images* folder for a file whose name matches the No. field of the record. If there is a match the file is imported; otherwise, nothing happens.  
  
```  
IF Item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    FileName := 'C:\images\' + FORMAT(Item."No.") + '.jpg';  
    IF FILE.EXISTS(FileName) THEN BEGIN  
      Item.itemPicture.IMPORTFILE(fileName, 'Demo image for item ' + FORMAT(Item."No."));  
      Item.MODIFY;  
    END;  
  UNTIL Item.NEXT < 1;  
END;  
  
```  
  
## See Also  
 [IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md)   
 [IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)   
 [EXPORTFILE Function \(Media\)](EXPORTFILE-Function--Media-.md)