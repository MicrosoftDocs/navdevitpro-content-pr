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
SENDTRACETAG(Tag, Category, Verbosity, Message)  
```  
  
#### Parameters  
*Tag*  
Type: Text or code  
  
Specifies an identifier of the trace event. The tag can consist of letters, numbers, and special characters. For example, system telemetry events use an auto-generated 7-character tag, such as 000002Q. Try to make your tags unique, for example, by using a prefix.  
  
*Category*  
Type: Text or code  
  
Specifies category for the telemetry trace.  
  
*Verbosity*  
Type: Verbosity  
  
Specifies the level of the event. You can set this parameter to either `Critical`, `Error`, `Warning`, `Normal`, or `Verbose`.   
  
*Message*  
Type: Text or code  
  
Specifies the descriptive message for the telemetry trace event. 
  
## Remarks 
You use the SENDTRACETAG function as part instrumenting an application for telemetry. When the SENDTRACETAG function called, a telemetry event is emitted and recorded in the event log. For more information, see [Instrumenting an Application for Telemetry](instrumenting-application-for-telemetry.md).

## Example 
The following code defines simple telemetry events for the five different severity levels. 
```  
SENDTRACETAG('MyCo-0001', 'Action', VERBOSITY::Critical, 'This is a critical message.');
SENDTRACETAG('MyCo-0002', 'Action', VERBOSITY::Error, 'This is an error message.');
SENDTRACETAG('MyCo-0003', 'Action', VERBOSITY::Warning, 'This is a warning message.');
SENDTRACETAG('MyCo-0004', 'Action', VERBOSITY::Normal, 'This is an informational message.');
SENDTRACETAG('MyCo-0005', 'Action', VERBOSITY::Verbose, 'This is a verbose message. ');
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)