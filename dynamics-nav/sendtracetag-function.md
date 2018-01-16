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
Defines a trace event.  
  
## Syntax  
  
```  
SENDTRACETAG(Tag, Category, Verbosity, Message)  
```  
  
#### Parameters  
*Tag*  
Type: Text or code  
  
Specifies the tag for the trace event.  
  
*Category*  
Type: Text or code  
  
Specifies a category for the trace event.  
  
*Verbosity*  
Type: Verbosity  
  
Specifies the level of the event as either: Critical, Error, Warning, Normal, Verbose.   
  
*Message*  
Type: Text or code  
  
Specifies the error message of the trace event. 
  
## Remarks 
The server instance setting will determine which level of telemetry events are logged
In Event Viewer, telemtry events are stored in the Common folder. The Admin folder contains the custom events set by this function. Event viewer will not show Verbose or Info messages, regardlesss of server setting. The operational log will list all system telemetry, based on the server setting.
## Example 
  
```  
SENDTRACETAG('My-0001', 'MyTest', VERBOSITY::Critical, 'My critical message');
SENDTRACETAG('My-0002', 'MyTest', VERBOSITY::Error, 'My error message');
SENDTRACETAG('My-0003', 'MyTest', VERBOSITY::Warning, 'My waarning message');
SENDTRACETAG('My-0002', 'MyTest', VERBOSITY::Normal, 'My informational message');
SENDTRACETAG('My-0002', 'MyTest', VERBOSITY::Verbose, 'My verbose message');
```  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)