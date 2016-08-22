---
title: "ISSESSIONACTIVE Function (Debugger)"
author: edupont04
manager: edupont04
ms.custom: na
ms.date: 08/22/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
---
# ISSESSIONACTIVE Function (Debugger)
Tests if a web service session is active on the [!INCLUDE[nav_server](includes/nav_server_md.md)].  

## Syntax  

```  
Ok := ISSESSIONACTIVE   
```  

## Property Value\/Return Value  
Type: Boolean  

**true** if a session with a specified ID is active on the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance; otherwise, **false**.  

Use this function to test if a session has completed or is still active, for example if you want to enable full SQL tracing but want to make sure that there are no active web service sessions.  

## See Also  
[Debugging](Debugging.md)
[Debugger](Debugger.md)
[Web Services](Web-Services.md)
