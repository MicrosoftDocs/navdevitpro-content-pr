---
title: "Working With Media on Records"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 47fb1195-eaa1-4995-9013-5edc28b13132
caps.latest.revision: 7
manager: edupont
---
# Working With Media on Records
This topic describes how you can upload media, such as an image, to the database for displaying with records in the client. There are two ways that you can do this:  

-   Use a BLOB data type  

     You add media to a BLOB data type field on the record.  

-   Use a Media or MediaSet data type  

    This method enables you to store media in system tables of the database, and then reference the media from application records. For applications that are developed for the [!INCLUDE[nav_web](includes/nav_web_md.md)] and [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)], you can use this method to:
    -   Display media with records in list type pages, when the page is viewed in the Brick layout, or in a report.  
    -   Display media on a card type page for a record.
    -   Display media in a report.

Using the Media or MediaSet data type provides better performance than using a BLOB data type and is more flexible in its design. With a BLOB data type, each time the media is rendered in the client, it is retrieved from the SQL database server, which requires extra bandwidth and affects performance. With the Media and MediaSet data types, the client uses media ID to cache the media data, which in turn improves the response time for rendering the media in the user interface.  

## Using Media and Media Sets on Records  
Table fields support two data types for adding media to records: **Media** and **MediaSet**.  

-   The **Media** data type associates a record with a single media object.  

    For example, you can use this data type to display an image with each record in a list type page.  

-   The **MediaSet** data type associates a record with one or more media objects. This enables you to set up a collection or catalog of media for a record.  

     For example, you can use this data type to set up a slide show of images for a record in a card type page.

    If a **MediaSet** data type field is used in a report object, then only the first associated media file is displayed in the generated report.

> [!NOTE]  
>  Currently, only image media types, such as jpeg, png, or gif, are supported. For more information, see [Supported Media Types](Working-With-Media-on-Records.md#SupportedMediaTypes).  

 With a field set to **Media** or **MediaSet** data type, you can add media to the record. You can import the media directly from a file, or it can be passed to the record in an InStream object. Imported media is stored as an object in the system table **2000000184 Tenant Media** of the application database. Each media object is assigned a unique identifier \(ID\).  

-   If a media object is added to **Media** data type field, the field references the media object by its ID.  

-   If a media object is added to **MediaSet** data type field, the media object is assigned to a media set in the system table **2000000183 Tenant Media Set**. The media set is assigned a unique identifier, which is then referenced from the field. The media set is created with the first file media object that you add on the record. Any additional media objects for the record are then associated with the same media set.  

###  <a name="SupportedMediaTypes"></a> Supported Media Types  
The media type, sometimes referred to as the MIME type, is an Internet standard to describe the contents of a file. Internet browsers use the media types to determine how to handle the file. There are several media types, such as image, audio, and video. Currently, [!INCLUDE[navnow](includes/navnow_md.md)] only supports image types. More specifically, you can only use image types that are supported by the System.Drawing.Image class of the .NET Framework, which include:
-   BMP
-   EMF
-   EXIF
-   GIF
-   JPEG
-   PNG
-   TIFF
-   WMF

>[!Note]
>GIF type is not supported on reports. If you want to display an image on a report, use another supported type.

### General Procedure for Adding Media to Records  
The general procedure for setting up media on records is as follows:  

1.  Obtain the media file or files that you want to use on the record.  

2.  In the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)], modify the table object to include a field that has the data type **Media** or **MediaSet**.  

3.  Add C/AL code that imports the media on the field.  

     The **Media** and **MediaSet** data types support several C/AL functions that you can use to manage the media on records. See the next section for a complete list of functions with a link to more details, such as usage, parameters and sample code.  

     For example, you can create a codeunit that calls one of the import functions, or add a page action that calls one of the functions.  

### C/AL Functions  
The following table provides an overview of the C/AL functions that are related to the Media and MediaSet data types.  

**Media data type**

|  Function  |  Description  |  
|------------|- -------------|
|[IMPORTFILE Function \(Media\)](IMPORTFILE-Function--Media-.md)|Adds  media from a file to a record. The imported media object is stored in the application database.|  
|[IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md)|Adds a media from an InStream object to a record. The imported media object is stored in the application database.|  
|[HASVALUE Function \(Media\)](HASVALUE-Function--Media-.md)|Detects whether a record has a media object in the **Media** data type field.|  
|[MEDIAID Function \(Media\)](MEDIAID-Function--Media-.md)|Gets the unique identifier \(GUID\) that is assigned to the media object in the application database.|  
|[EXPORTFILE Function \(Media\)](EXPORTFILE-Function--Media-.md)|Exports a media object from a record to a file.|  
|[EXPORTSTREAM Function \(Media\)](EXPORTSTREAM-Function--Media-.md)|Exports a media object from a record to an OutStream object.|  

**MediaSet data type**

|  Function  |  Description  |  
|------------|- -------------|
|[EXPORTFILE Function \(MediaSet\)](EXPORTFILE-Function-MediaSet.md)|Exports the media objects that included in a media set to individual files.|  
|[IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)|Adds media from a file to a record, and assigns the imported media object to a media set. The media object is stored in the application database.|  
|[IMPORTSTREAM Function \(MediaSet\)](IMPORTSTREAM-Function--MediaSet-.md)|Adds media from an InStream object to a record. The imported media object is stored in the application database.|  
|[MEDIAID Function \(MediaSet\)](MEDIAID-Function--MediaSet-.md)|Gets the unique identifier \(GUID\) that is assigned to the media set on a record.|  
|[COUNT Function \(MediaSet\)](COUNT-Function--MediaSet-.md)|Gets the total number of media objects that are included in the media set on a record.|  


## See Also  
 [Media Data Type](Media-Data-Type.md)   
 [MediaSet Data Type](MediaSet-Data-Type.md)
