---
title: "STOPSESSION Function (Sessions)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a49c867c-aec4-4d5f-9881-1a2442274a1a
caps.latest.revision: 11
manager: edupont
---
# STOPSESSION Function (Sessions)
Stops a [!INCLUDE[navnow](includes/navnow_md.md)] session.  
  
## Syntax  
  
```  
[OK :=] STOPSESSION(SessionID[,Comment]);  
```  
  
#### Parameters  
 *SessionID*  
 Type: Integer  
  
 The ID of the session that you want to stop.  
  
 The session can be any of the following:  
  
-   [!INCLUDE[nav_windows](includes/nav_windows_md.md)] session  
  
-   [!INCLUDE[nav_web](includes/nav_web_md.md)] session  
  
-   NAS services session  
  
-   SOAP web services client session  
  
-   OData web services client session  
  
-   Background session  
  
 *Comment*  
 Type: Text  
  
 An optional comment about the session event. The comment is stored in Table 2000000111, the Session Event table.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the session is stopped successfully and no errors occurred; otherwise **false**.  
  
 If you omit this optional return value and the session is not stopped successfully, then a run-time error occurs. If you include the return value, then you must handle any errors.  
  
## Remarks  
 The session that you want to stop and the session that calls STOPSESSION must be running on the same instance of [!INCLUDE[nav_server](includes/nav_server_md.md)]. The session is stopped before the next C/AL statement executes. Open transactions are rolled back.  
  
> [!NOTE]  
>  If the current executing statement is the **SLEEP** function, then the session is stopped immediately.  
  
 When a session is executing C/AL that does not interact with the server connection or the access lock used by the connection, STOPSESSION cannot terminate the connection. STOPSESSION can terminate connections that are inactive, idle, or using the database but not blocked.  
  
 You cannot stop the current, active session in which you are executing the **STOPSESSION** call.  
  
## Example  
 This example requires that you create the following variables, and assumes that you have a table named CacheStressTest that you use for testing.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|SessionId|Integer|Not applicable|  
|CacheStressTestRec|Record|CacheStressTest|  
  
```  
STARTSESSION(SessionId, CODEUNIT::"Cache Stress Test", COMPANYNAME, CacheStressTestRec);  
STOPSESSION(SessionId, 'Logoff cache stress test session');  
  
```