---
title:"MEDIAID Function (Media)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod:"dynamics-nav-2017"
ms.assetid: 85a4d825-8fc7-4a79-988e-3b867283eefe
caps.latest.revision: 4
manager: edupont
---
# MEDIAID Function (Media)
Gets the unique identifier of a media file that is used on a record.  
  
## Syntax  
  
```  
Guid := Record.Media.MEDIAID  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 Specifies the record that uses the media.  
  
 *Media*  
 Type: Media  
  
 Specifies the field that contains the media. This field has the **Media** data type.  
  
## Property Value\/Return Value  
 Type: GUID  
  
 The GUID of media in the database.  
  
## Remarks  
 When a media file is imported into the record of a table by the [IMPORTFILE Function \(Media\)](IMPORTFILE-Function--Media-.md), the media is given a GUID and stored in the system table **2000000184 Tenant Media** of the application database. The GUID is then included in the **Media** data type field as a reference to the media in the database.  
  
## Example  
 This example uses the MEDIAID function to get the GUID of a media that is used on item **No. 1000** in the table **27 Item**.  
  
 This code requires you to create the following variable.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|item|Record|Item|  
|mediaGuid|GUID||  
  
 This code requires you to create the following text constant.  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|The GUID of media is: %1|  
  
```  
item.GET('1000');  
    mediaGuid := item.MediaSetField.MEDIAID;  
    MESSAGE(Text000, mediaGuid);  
```  
  
## See Also  
 [IMPORTFILE Function \(Media\)](IMPORTFILE-Function--Media-.md)   
 [IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md)   
 [Media Data Type](Media-Data-Type.md)