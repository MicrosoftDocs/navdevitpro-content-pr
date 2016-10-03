---
title: "MEDIAID Function (MediaSet)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 270d2955-8330-466e-b7d3-46eb0901d42d
caps.latest.revision: 4
---
# MEDIAID Function (MediaSet)
Gets the unique identifier that is assigned to a MediaSet of a record. The MediaSet is a collection of media files that are used on the record and can be displayed in the client.  

## Syntax  

```  
Guid := Record.MediaSet.MEDIAID  
```  

#### Parameters  
 *Record*  
 Type: Record  

 Specifies the record that includes the MediaSet.  

 *MediaSet*  
 Type: MediaSet  

 Specifies the field that includes the media. This field has the **MediaSet** data type.  

## Property Value/Return Value  
 Type: GUID  

 The GUID of MediaSet of the record.  

## Remarks  
 When a media file is imported into the record of a table by the [IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md), media is assigned to a MediaSet GUID as defined system table **2000000183 Tenant Media Set** of the application database. You can use this function to retrieve the MediaSet GUID. The media file is also assigned a GUID. To get the media file's GUID, you use the [MEDIAID Function \(Media\)](MEDIAID-Function--Media-.md).  

## Example  
 This example is gets the GUID of the MediaSet that is used on item No. 1000 in the **Item** table. The field in the **Item** table that is used for the MediaSet data type is **MediaSetField**.  

 This code requires you to create the following variables.  

|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|item|Record|Item|  
|mediaGuid|GUID||  

 This code requires you to create the following text constant.  

|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|The GUID of the MediaSet is: %1|  

```  
item.GET('1000');  
    mediaGuid := item.MediaSetField.MEDIAID;  
    MESSAGE(Text000, mediaGuid);  
```  

## See Also  
 [IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)   
 [IMPORTSTREAM Function \(MediaSet\)](IMPORTSTREAM-Function--MediaSet-.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)
