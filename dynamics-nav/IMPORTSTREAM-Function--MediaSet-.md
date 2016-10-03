---
title: "IMPORTSTREAM Function (MediaSet)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 88c17900-5351-40db-a39c-a9322e5f5256
caps.latest.revision: 4
---
# IMPORTSTREAM Function (MediaSet)
Adds a media file, such as a jpeg image, from an InStream object to the MediaSet of record for displaying in the client. The media is imported to the database and included in a MediaSet for the record. The MediaSet defines a collection of media.  

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

 Specifies text that can be used in the client to describe the media files.  

 *MimeType*  
 Type: Text  

 Specifies the content type of the media. MIME type is used by browsers, and is an Internet standard to describe the contents of a file. The *MimeType* value must be a two-part string that consists of a type and subtype, such as *image/jpeg*, *image/gif*, or *video/mpeg*.  

 If this parameter is not specified, the IMPORTFILESTREAM function will deduct the MIME type from the file extension. For example the MIME type for a .jpg file is image/jpeg.  

## Property Value/Return Value  
 Type: GUID  

 The unique ID assigned to the MediaSet of the record. ID can be retrieved by using the [MEDIAID Function \(MediaSet\)](MEDIAID-Function--MediaSet-.md).  

## Remarks  
 You can use this function to upload a media file, which you want to associate with a record, to the database. For example, you can upload an image of all items in table **27 Item**. The function is similar to the [IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md) except that this function enables you to import multiple media files for the same record.  

 When a media file is imported, it is assigned a unique identifier \(GUID\) and stored in the system table **2000000181 Tenant Media** of the application database. In addition, the media file is assigned to a MediaSet GUID. This GUID is included in the **MediaSet** data type field as a reference to the media files. The MediaSet GUID is created with the first file that you import. Additional media files for the record are then associated with the same MediaSet GUID. This information is stored in table **2000000183 Tenant Media Set**.  

 If you import a media object into a record that already has a media object, and the modify operation is performed, the previous media object will be permanently deleted, unless there are other references to the media object in the same table field.  

## Example  
 This example uses the IMPORTSTREAM function to add images to records in table **27 Item** of the [!INCLUDE[demolong](includes/demolong_md.md)]. To support the example code that follows, you also have to complete these tasks:  

-   Add item image files for records of table **27 Item** to a folder on the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)] instance  

     Save the images as .jpg type, and give them names that correspond to item numbers \(as specified by the **No.** field\), such as, 1000-v1.jpg, 1000-v2.jpg, 1001-v1.jpg, 1001-v2.jpg and so on. For this example, save the files in the folder *C:\\images*.  

-   In the **Item** table, add a new field that has the data type **MediaSet**.  

-   In the **Item List** page, add a column for the **MediaSet** field.  

 With these tasks in place, you can add and run the following C/AL code to import the images. For this code example, create a codeunit and add the code to the OnRun trigger. But, you could also add the code other places instead, such as on an action in the **Item List** page.  

 The code requires that you create the following variables:  

|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|item|Record|Item|  
|myIinStream|InStream||  

 This code iterates over records in the **Items** table. For each record, it looks in the *C:\\images* folder for a file whose name matches the **No.** field of the record. If there is a match the file, an InStream object is created for the file, and then imported into the record.  

```  
IF item.FINDFIRST() THEN  
BEGIN  
  REPEAT  
    fileName := 'C:\images\' + FORMAT(item."No.") + '.jpg';  

    IF FILE.EXISTS(fileName) THEN BEGIN  
        importFile.OPEN(fileName);  
        importFile.CREATEINSTREAM(myInStream);  
        item.MediaSet.IMPORTSTREAM(myInStream, 'Demo image for item ' + FORMAT(item."No."));  
      item.MODIFY;  
      importFile.CLOSE;  

    END;  
  UNTIL item.NEXT < 1;  
END;  
```  

## See Also  
 [Working With Media on Records](Working-With-Media-on-Records.md)  
 [Working With Media on Records](Working-With-Media-on-Records.md)  
 [IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)
