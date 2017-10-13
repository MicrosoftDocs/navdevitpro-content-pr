---
title: "Changes in C/AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
manager: edupont
author: jswymer
---
# Changes in C/AL Behavior and Support from Earlier Versions of Microsoft Dynamics NAV

**Applies to:** [!INCLUDE[nav2018_md](includes/nav2017.md)]. [See [!INCLUDE[nav2017](includes/nav2017.md)]](Changes-in-C-AL-Behavior-and-Support-from-Earlier-Versions-of-Microsoft-Dynamics-NAV-2017.md).

The following tables provide an overview of the new, removed, or changed C/AL data types, functions, properties, and triggers in [!INCLUDE[navnowlong](includes/navnowlong_md.md)] since the previous version of [!INCLUDE[navnow](includes/navnow_md.md)]. For more information about the changes, see the specific topic about the data type, function, property, or trigger.  

## C/AL Data Types  
 The following table lists the new data types in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

|Data Type|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|---------------|---------------------------------------|  
|Media|A complex type that encapsulates media (such as images) in the application database for displaying the media with associated records. The data type can be used on table fields and supports the following functions:<br /><br /> -   ImportFile<br />-   ImportInStream<br />-   MEDIAID<br />-   HASVALUE<br />-   EXPORTFILE<br />-   EXPORTSTREAM<br /><br />|  
|MediaSet|A complex type that encapsulates media files, such as images, in application database for displaying the media with associated records. The **MediaSet** data type enables you to include multiple media files as part of a collection on a record. The **MediaSet** data type can be used on table fields and supports the following functions:<br /><br /> -   ImportFile<br />-   ImportInStream<br />-   MEDIAID<br />-   COUNT<br />-   EXPORTMEDIASET<br /><br />|  
|Notification| A complex type for publishing and consuming notifications in the application. Notifications provide a programmatic way to send non-intrusive information to the user interface (UI). The **Notification** data type supports the following functions:<br /><br /> -   ADDACTION<br />-   GETDATA<br />-   ID<br />-   MESSAGE<br />-   RECALL<br />- SCOPE<br />- SEND<br />- SETDATA|  
See the C/AL Functions section that follows for a description of the data type functions.

## C/AL Functions  
### New functions
The following table lists the new functions in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

|Function|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|[CANCREATTASK\(TaskScheduler\)](cancreatetask-function.md)|Indicates whether a user has permissions to create or schedule a task.|  

### Changed functions
The following table lists the changed functions in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

|Function|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|TryFunction|By default, database write transactions in a try function are not allowed. For more information, see [Database write transactions in try functions](Handling-Errors-by-Using-Try-Functions.md#DbWriteTransactions).|  

## C/AL Properties  
 The following table lists the new properties in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

|Property|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|[ApplicationArea Property](ApplicationArea-Property.md)|Sets the application areas that apply to the control.|  
|[Gesture Property](property-gesture.md)|Specifies a gesture that runs the page action on a device with a touch interface.|
|[TestPermissions Property](property-testpermissions.md)|Specifies a value that can be used to determine which permission sets are used on tests that are run by test codunits or test functions.|
|[PromotedOnly Property](PromotedOnly-Property.md)|Specifies whether a page action will appear only on the **Home** tab in the ribbon and not on the tab where it is defined.|    

## C/AL Triggers  
 The following table lists the changed triggers in [!INCLUDE[navnowlong](includes/navnowlong_md.md)].  

|Trigger|[!INCLUDE[bp_tabledescription](includes/bp_tabledescription_md.md)]|  
|--------------|---------------------------------------|  
|[OnAfterTestRun Trigger](trigger-onaftertestrun.md)|Includes a TestPermissions data type parameter for running tests with permission sets.|
|[OnBeforeTestRun Trigger](trigger-onbeforetestrun.md)|Includes a TestPermissions data type parameter for running tests with permission sets.|    

## See Also  
 [Functions Not Supported by Microsoft Dynamics NAV Web Client](Functions-Not-Supported-by-Microsoft-Dynamics-NAV-Web-Client.md)   
 [Page Properties Not Supported by Microsoft Dynamics NAV Web Client](Page-Properties-Not-Supported-by-Microsoft-Dynamics-NAV-Web-Client.md)
