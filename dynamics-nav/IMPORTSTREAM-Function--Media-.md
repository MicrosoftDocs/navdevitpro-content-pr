---
title: "IMPORTSTREAM Function (Media)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1f7164b2-338b-4121-8a10-749a534c6188
caps.latest.revision: 8
manager: edupont
---
# IMPORTSTREAM Function (Media)
Adds a media type \(MIME\), such as jpeg image, from an InStream object to a **Media** data type field of a record for displaying the media with the record in the client. The media file is imported to the application database and a reference to the media is included in the **Media** data type field.  
  
## Syntax  
  
```  
[GUID] := ]Record.Media.IMPORTSTREAM(InStream ,Description[, MimeType])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that you want to add the media to.  
  
 *InStream*  
 Type: InStream  
  
 Specifies the InStream object that contains the media that you want to use on the record.  
  
 *Description*  
 Type: Text  
  
 Specifies text that can be used in the client to describe the media file.  
  
 *MimeType*  
 Type: Text  
  
 Specifies the media content type. The *MimeType* value must be a two\-part string that consists of a type and subtype, such as *image\/jpeg*, *image\/gif*, or *video\/mpeg*. For more information, see [Supported Media Types](../dynamics-nav/Working-With-Media-on-Records.md#SupportedMediaTypes).  
  
 If this parameter is not specified, the IMPORTFILESTREAM function will deduct the MIME type from the file extension. For example the MIME type for a .jpg file is image\/jpeg.  
  
## Property Value\/Return Value  
 Type: GUID  
  
 The unique ID assigned to this media file instance in the database table field. This ID can be retrieved by using the [MEDIAID Function \(Media\)](../dynamics-nav/MEDIAID-Function--Media-.md).  
  
## Remarks  
 You can use this function to upload a media file that is associated with a record to the database. For example, you can upload an image of all items in table **27 Item**. When a media is imported, the object is stored in the system table **2000000184 Tenant Media** of the application database.  
  
 If you import a media object into a record that already has a media object, and the modify operation is performed, the previous media object will be permanently deleted, unless there are other references to the media object in the same table field.  
  
## Example  
 This example uses the IMPORTSTREAM function to add images to records in table **27 Item** of the [!INCLUDE[demolong](../dynamics-nav/includes/demolong_md.md)]. After the images are imported, they will be displayed with items on page **31 Item List** when the page is opened in the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)] and viewed in a brick layout. The example uses C\/AL code to iterate over records in the **Items** table and import an image file for records from a local folder. To support the example code that follows, you also have to complete these tasks:  
  
-   Create the item image files and save them on the computer that is running [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance  
  
     Save the images as .jpg type, and give them names that correspond to item numbers \(as specified by the **No.** field\), such as, 1000.jpg, 1001.jpg, 1100.jpg, and so on. For this example, save the files in the folder *C:\\images*.  
  
-   In the **Item** table, add a new field that has the data type **Media**.  
  
     For this example, name the field **itemPicture**. To make the media field visible in the [!INCLUDE[nav_web](../dynamics-nav/includes/nav_web_md.md)], include the field in the table field group that is named **Brick**.  
  
-   In the **Item List** page, add a column for the **Media** field.  
  
 With these tasks in place, you can add and run the following C\/AL code to import the images. For this code example, create a codeunit and add the code to the OnRun trigger. But, you could also add the code other places instead, such as on an action in the **Item List** page.  
  
 The code requires that you create the following variables:  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
|InStream|InStream||  
|ImportFile|File||  
  
 This code iterates over records in the **Items** table. For each record, it looks in the *C:\\images* folder for a file whose name matches the **No.** field of the record. If there is a match the file, an InStream object is created for the file, and then imported into the record.  
  
```  
IF Item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    FileName := 'C:\images\' + FORMAT(Item."No.") + '.jpg';  
  
    IF FILE.EXISTS(fileName) THEN BEGIN  
        ImportFile.OPEN(fileName);  
        ImportFile.CREATEINSTREAM(InStream);  
        Item.ItemPicture.IMPORTSTREAM(InStream, 'Demo image for item ' + FORMAT(item."No."));  
      Item.MODIFY;  
      ImportFile.CLOSE;  
  
    END;  
  UNTIL Item.NEXT < 1;  
END;  
  
```  
  
## See Also  
 [IMPORTFILE Function \(Media\)](../dynamics-nav/IMPORTFILE-Function--Media-.md)   
 [IMPORTFILE Function \(MediaSet\)](../dynamics-nav/IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](../dynamics-nav/IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](../dynamics-nav/MediaSet-Data-Type.md)