---
title: "IMPORTFILE Function (MediaSet)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 59f38aea-d525-4df8-ba51-9375b2697761
caps.latest.revision: 5
---
# IMPORTFILE Function (MediaSet)
Adds a media file, such as a jpeg image, to the **MediaSet** data type field of a record for displaying the media with the record in the client. The media is imported to the database and included in a MediaSet for the record. The MediaSet defines a collection of media.  
  
## Syntax  
  
```  
  
[GUID] := ]Record.Media.IMPORTFILE(FileName ,Description[, MimeType])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that you want to add the media to.  
  
 MediaSet  
 Type: MediaSet  
  
 Specifies the field that you want to add the media to. The field has the **MediaSet** data type.  
  
 *FileName*  
 Type: Text  
  
 Specifies the full path and name of the media file to be imported.  
  
 *Description*  
 Type: Text  
  
 Specifies text that can be used in the client describe the media.  
  
 *MimeType*  
 Type: Text  
  
 Specifies the media content type. MIME type is used by browsers, and is an Internet standard to describe the contents of a file. The *MimeType* value must be a two\-part string that consists of a type and subtype, such as *image\/jpeg*, *image\/gif*, or *video\/mpeg*.  
  
 If this parameter is not specified, the IMPORTFILE function will deduct the MIME type from the file extension. For example the MIME type for a .jpg file is image\/jpeg.  
  
## Property Value\/Return Value  
 Type: GUID  
  
 The unique ID assigned to the MediaSet of the record. This ID can be retrieved by using the [MEDIAID Function \(MediaSet\)](MEDIAID-Function--MediaSet-.md).  
  
## Remarks  
 You can use this function to upload a media file as part of a collection of media files that you want to associate with a record. For example, you can upload images of items in table **27 Item**. The function is similar to the [IMPORTFILE Function \(Media\)](IMPORTFILE-Function--Media-.md) except that this function enables you to import multiple media files for the same record.  
  
 When a media file is imported, it is assigned a unique identifier \(GUID\) and stored in the system table **2000000181 Tenant Media** of the application database. In addition, the media file is assigned to a MediaSet GUID. This GUID is included in the MediaSet data type field as a reference to the media files. The MediaSet GUID is created with the first file that you import. All additional media files for the record are then associated with the same MediaSet GUID. This information is stored in table **2000000183 Tenant Media Set**.  
  
## Example  
 This example uses the IMPORTFILE function to add images to records in table **27 Item** of the [!INCLUDE[demolong](includes/demolong_md.md)]. To support the example code that follows, you also have to complete these tasks:  
  
-   Add item image files for records of table 27 Item.to the and save them on the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)] instance  
  
     Save the images as .jpg type, and give them names that correspond to item numbers \(as specified by the **No.** field\), such as, 1000\-v1.jpg, 1000\-v2.jpg, 1001\-v1.jpg, 1001\-v2.jpg and so on. For this example, save the files in the folder *C:\\images*.  
  
-   In the **Item** table, add a new field that has the data type **MediaSet**.  
  
-   In the **Item List** page, add a column for the **MediaSet** field.  
  
 With these tasks in place, you can add and run the following C\/AL code to import the images. For this code example, create a codeunit and add the code to the OnRun trigger. But, you could also add the code other places instead, such as on an action in the **Item List** page.  
  
 The code requires that you create the following variables:  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|item|Record|Item|  
|fileName|Text||  
  
 This code iterates over records in the **Items** table. For each record, it looks in the *C:\\images* folder for a file whose name matches the **No.** field of the record. If there is a match the file is imported.  
  
```  
IF item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    fileName := 'C:\images\' + FORMAT(item."No.") + '.jpg';  
    IF FILE.EXISTS(fileName) THEN BEGIN  
      item.MediaSet.IMPORTFILE(fileName, 'Demo image for item ' + FORMAT(item."No."));  
      item.MODIFY;  
    END;  
  UNTIL item.NEXT < 1;  
END;  
  
```  
  
## See Also  
 [IMPORTSTREAM Function \(MediaSet\)](IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)