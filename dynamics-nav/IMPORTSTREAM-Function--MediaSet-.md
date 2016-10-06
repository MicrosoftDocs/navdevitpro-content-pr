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
Adds a media file, such as a JPEG image, from an InStream object to the MediaSet of record for displaying in the client. The media is imported to the database and included in a MediaSet for the record.

## Syntax  

```  
[Guid := ]Record.MediaSetField.IMPORTSTREAM(InStreamObject, Description[, MimeType])  
```  

#### Parameters  
 *Record*  
 Type: Record  

 Specifies the record that you want to add the media to.  

 *MediaSetField*  
  Type: MediaSet  

  Specifies the field that you want to add the media to. The field must have the **MediaSet** data type.  

 *InStreamObject*  
 Type: InStream  

 Specifies the InStream object that contains the media that you want to use on the record.  

 *Description*  
 Type: Text  

 Specifies text that can be used in the client to describe the media files.  

 *MimeType*  
 Type: Text  

 [!INCLUDE[mimetype](includes/MimeType.md)]

## Property Value/Return Value  
 Type: GUID  

 The unique ID assigned to the MediaSet of the record. You can also retrieve the ID by using the [MEDIAID Function \(MediaSet\)](MEDIAID-Function--MediaSet-.md).  

## Remarks  
 You can use this function to upload a media objects, which you want to associate with a record, to the database. For example, you can upload  media objects to items in table **27 Item**. The function is similar to the [IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md) except that this function enables you to import multiple media objects on the same record.  

When a media is imported, it is assigned a unique identifier \(GUID\) and stored in the system table **2000000181 Tenant Media** of the application database.

In addition, the media object is assigned to a MediaSet which also has a specific GUID. This GUID is included in the MediaSet data type field as a reference to the media objects. The MediaSet and its GUID are created with the first media that is imported, and the information is stored in table **2000000183 Tenant Media Set**. All additional media objects for the record are then associated with the same MediaSet GUID.

## Example  
 This example uses the IMPORTSTREAM function to add images to records in table **27 Item** of the [!INCLUDE[demolong](includes/demolong_md.md)]. To support the example code that follows, you also have to complete these tasks:  

-   Add item image files for records of table **27 Item** to a folder on the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)] instance  

     Save the images as .jpg type, and give them names that correspond to item numbers \(as specified by the **No.** field\), such as, 1000-v1.jpg, 1000-v2.jpg, 1001-v1.jpg, 1001-v2.jpg and so on. For this example, save the files in the folder *C:\\images*.  

-   In the **Item** table, add a new field that has the data type **MediaSet**.  

-   In the **Item List** page, add a column for the **MediaSet** field.  

With these tasks in place, you can add and run the following C/AL code to import the images. For this code example, create a codeunit and add the code to the OnRun trigger. But, you could also add the code other places instead, such as on an action in the **Item List** page.  

The code requires that you create the following variables and text constant:  

|  Variable name  |  DataType  |  Subtype  |  
|-----------------|------------|-----------|  
|item|Record|Item|  
|inStreamObject|InStream||  
|importFile|File||
|count|Integer||  
|mediasetId|GUID||  

|  Text constant name  |  ConstValue  |  
|----------------------|--------------|  
|Text000|The files have been imported. Item %1 has %2 pictures in MediaSet: %3|

```  
item.GET('1155');

fileName := 'C:\images\1000-v1.jpg';
importFile.OPEN(fileName);  
importFile.CREATEINSTREAM(inStreamObject);  
item.Picture.IMPORTSTREAM(inStreamObject, 'Demo image for item ' + FORMAT(item."No."));  
item.MODIFY;  
importFile.CLOSE;  

fileName := 'C:\images\1000-v2.jpg';
importFile.OPEN(fileName);  
importFile.CREATEINSTREAM(inStreamObject);  
item.Picture.IMPORTSTREAM(inStreamObject, 'Demo image for item ' + FORMAT(item."No."));  
item.MODIFY;  
importFile.CLOSE;

count := (item.Picture.COUNT);
mediasetId := item.Picture.MEDIAID;  
MESSAGE(Text000,item."No.",count,mediasetId);  
```  
If you run system table **2000000181 Tenant Media** from the  [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)], you should see the new images in the list.

## See Also  
 [Working With Media on Records](Working-With-Media-on-Records.md)  
 [Working With Media on Records](Working-With-Media-on-Records.md)  
 [IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)
