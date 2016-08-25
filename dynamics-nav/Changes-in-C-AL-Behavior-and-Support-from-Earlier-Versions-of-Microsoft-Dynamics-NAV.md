---
title: "Changes in C-AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 786f53bd-ded3-4273-9b3a-b76ab9d1ce61
caps.latest.revision: 89
manager: edupont
---
# Changes in C-AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV
The following table provides an overview of the new, removed, or changed C/AL data types, functions, properties, and triggers in [!INCLUDE[navnowlong](includes/navnowlong_md.md)] since the previous version of [!INCLUDE[navnow](includes/navnow_md.md)]. For more information about the changes, see the specific topic about the data type, function, property, or trigger.  
  
## C/AL Data Types  
 The following table lists the new data types in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
|Data Type|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|---------------|---------------------------------------|  
|Media|A complex type that encapsulates media \(such as images\) in the application database for displaying the media with associated records. The data type can be used on table fields and supports the following functions:<br /><br /> -   ImportFile<br />-   ImportInStream<br />-   MEDIAID<br />-   HASVALUE<br />-   EXPORTFILE<br />-   EXPORTSTREAM<br /><br /> See the C/AL Functions section for a description of these functions.|  
|MediaSet|A complex type that encapsulates media files, such as images, in application database for displaying the media with associated records. The **MediaSet** data type enables you to include multiple media files as part of a collection on a record. The **MediaSet** data type can be used on table fields and supports the following functions:<br /><br /> -   ImportFile<br />-   ImportInStream<br />-   MEDIAID<br />-   COUNT<br />-   EXPORTMEDIASET<br /><br /> See the C/AL Functions section for a description of these functions.|  
  
## C/AL Functions  
 The following table lists the new, changed, and functions in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
||Function|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-|--------------|---------------------------------------|  
|New Functions|[APPLICATIONAREA Function](APPLICATIONAREA-Function.md)|Gets or sets the application areas for the current session.|  
||[CAPTIONCLASSTRANSLATE Function](CAPTIONCLASSTRANSLATE-Function.md)|Returns a translated version of the caption string. The string is translated to the current local language.|  
||[CHANGECOMPANY Function \(RecordRef\)](CHANGECOMPANY-Function--RecordRef-.md)|Redirects references to table data from one company to another.|  
||[COUNT Function \(MediaSet\)](COUNT-Function--MediaSet-.md)|Gets the number of media files that are included in a media set of a record.|  
||[EXPORTFILE Function \(Media\)](EXPORTFILE-Function--Media-.md)|Exports a media object that is set up on a record to a file.|  
||[EXPORTFILE Function](EXPORTFILE-Function.md)|Exports the media objects that included in a media set to individual files.|  
||[EXPORTSTREAM Function \(Media\)](EXPORTSTREAM-Function--Media-.md)|Exports a media object that is set up on a record to an OutStream object.|  
||[HASVALUE Function \(Media\)](HASVALUE-Function--Media-.md)|Detects whether a record has a media object in the **Media** data type field.|  
||[IMPORTFILE Function \(Media\)](IMPORTFILE-Function--Media-.md)|Adds media from a file to a media set of a record.|  
||[IMPORTFILE Function \(MediaSet\)](IMPORTFILE-Function--MediaSet-.md)|Adds media from a file to a media set of a record.|  
||[IMPORTSTREAM Function \(Media\)](IMPORTSTREAM-Function--Media-.md)|Adds media from an InStream object to a record.|  
||[IMPORTSTREAM Function \(MediaSet\)](IMPORTSTREAM-Function--MediaSet-.md)|Adds media from an InStream object to a media set of a record.|  
||[ISBYTE Function \(Variant\)](ISBYTE-Function--Variant-.md)|Indicates whether a C/AL variant contains a Byte variable.|  
||[ISTEXTCONSTANT Function \(Variant\)](ISTEXTCONSTANT-Function--Variant-.md)|Indicates whether a C/AL variant contains a text constant.|  
||[MEDIAID Function \(Media\)](MEDIAID-Function--Media-.md)|Get the ID that is assigned to media in the database.|  
||[MEDIAID Function \(MediaSet\)](MEDIAID-Function--MediaSet-.md)|Gets the ID that is assigned to the media set of a record.|  
|Changed Functions|||  
||||  
  
## C/AL Properties  
 The following table lists the new, changed, and removed properties in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
||Property|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-|--------------|---------------------------------------|  
|New Properties|[ApplicationArea Property](ApplicationArea-Property.md)|Sets the application areas that apply to the control.|  
||[PromotedOnly Property](PromotedOnly-Property.md)|Specifies whether a page action will appear only on the **Home** tab in the ribbon and not on the tab where it is defined.|  
|Changed Properties|||  
  
## C/AL Statements  
 The following table lists the new, changed, and removed C/AL statements in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  
  
||Statement|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|-|---------------|---------------------------------------|  
|New Statements|||  
|Changed Statements|||  
  
## See Also  
 [Functions Not Supported by Microsoft Dynamics NAV Web Client](Functions-Not-Supported-by-Microsoft-Dynamics-NAV-Web-Client.md)   
 [Page Properties Not Supported by Microsoft Dynamics NAV Web Client](Page-Properties-Not-Supported-by-Microsoft-Dynamics-NAV-Web-Client.md)