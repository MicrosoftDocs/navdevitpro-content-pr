---
title: "SENDTRACETAG Function"
ms.custom: na
ms.date: 27/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
author: jswymer
---
# SENDTRACETAG Function
Sends a telemetry trace event to the event log.  
  
## Syntax  
  
```  
SENDTRACETAG(Tag, Category, Verbosity, Message[, DataClassification])  
```  
  
#### Parameters  
*Tag*  
Type: Text or code  
  
Specifies an identifier of the trace event. The tag can consist of letters, numbers, and special characters. [!INCLUDE[navnow_md](includes/navnow_md.md)] system telemetry events use an auto-generated, auto-incremented, 7-character tag that includes numbers and letters, such as 000002Q. and 000013P. Try to make your tags unique from these telemetry event tags by, for example, using at least 8 characters or a prefix, like Cronus-0001 and Cronus-0002. 
  
*Category*  
Type: Text or code  
  
Specifies category for the telemetry trace.  
  
*Verbosity*  
Type: Verbosity  
  
Specifies the level of the event. You can set this parameter to either `Critical`, `Error`, `Warning`, `Normal`, or `Verbose`.   
  
*Message*  
Type: Text or code  
  
Specifies the descriptive message for the telemetry trace event. 

*DataClassification*  
Type: DataClassification  
  
Specifies a classification for the data in the telemetry trace event. The following values are supported:

|  Value  |  Description  |  Example  |
|---------|---------------|-----------|
|CustomerContent|Content directly provided/created by admins and users. This is the default when no value has been specified.||
|EndUserIdentificationInformation|(EUII) Data that identifies or could be used to identify the user of a Microsoft service. EUII does not contain Customer content. || 
|AccountData|Customer billing information and payment instrument information, including administrator contact information, such as tenant administrator’s name, address, or phone number.||  
|EndUsePseudonymousIdentifiers|(EUPI) An identifier created by Microsoft tied to the user of a Microsoft service. When EUPI is combined with other information, such as a mapping table, it identifies the end user. EUPI does not contain information uploaded or created by the customer (Customer content or EUII). ||
|OrganizationIdentifiableInformation|(OII) Data that can be used to identify a tenant, generally config or usage data. This data is not linkable to a user and does not contain Customer content.|| 
|SystemMetadata|Data generated in the course of running the service or program that is not linkable to a user or tenant. || 

These values correspond to values of the [DataClassification property](dataclassification-property.md) on table objects and fields. Like the DataClassification property, you can use the `DataClassification` parameter to comply with legistlative requirements, like GDPR, for gathering, storing, and using user personal information.

>[!IMPORTANT]
>If you do not set the `DataClassification`, the telemetry trace event is automatically classified as `CustomerContent`.

## Remarks 
You use the SENDTRACETAG function for instrumenting the application for telemetry. When the SENDTRACETAG function called, a telemetry trace event is emitted. The event can then be recorded in the Windows event log or collected by other event trace collection tools, like PerfView, Logman, and Performance Monitor. 

The telemetry trace  = 700;
        public const int Error = 701;
        public const int Informational = 702;
        public const int LogAlways = 703;
        public const int Verbose = 704;
        public const int Warning = 705;
        public const int ActivityTransfer = 706;

For more information, see [Instrumenting an Application for Telemetry](instrumenting-application-for-telemetry.md) and [Monitoring-Dynamics NAV Server Events](Monitoring-Microsoft-Dynamics-NAV-Server-Events.md). 


## Example 
The following code defines simple telemetry events for the five different severity levels. 
```  
SENDTRACETAG('MyCo-0001', 'Action', VERBOSITY::Critical, 'This is a critical message.', );
SENDTRACETAG('MyCo-0002', 'Action', VERBOSITY::Error, 'This is an error message.', );
SENDTRACETAG('MyCo-0003', 'Action', VERBOSITY::Warning, 'This is a warning message.', );
SENDTRACETAG('MyCo-0004', 'Action', VERBOSITY::Normal, 'This is an informational message.', );
SENDTRACETAG('MyCo-0005', 'Action', VERBOSITY::Verbose, 'This is a verbose message. ', );
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)