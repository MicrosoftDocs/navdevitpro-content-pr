---
title: "TASKEXISTS Method"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-365-for-financials"
ms.assetid: 0d76d61f-c6c7-4e4e-bd21-3a239221a571
caps.latest.revision: 3
manager: edupont
---
# TASKEXISTS Method
Checks whether a specific task exists.  

## Syntax  

```  
Exists := TASKEXISTS(Task)  
```  

#### Parameters  
 *Task*  
 Type: GUID  

 The unique identifier of the task. The unique identifier is returned by the CREATETASK method.  

## Property Value/Return Value  
 Type: Boolean  

 **true** if a task exists; otherwise, **false**.  

## Remarks  
 Scheduled tasks are recorded in table **2000000175 Scheduled Task**. To see an example of CANCELTASK in use, refer to AL code of table **472 Job Queue Entry**.  

 For more information about tasks and TASKSCEDULER data type methods, see managing tasks [Task Scheduler](../devenv-task-scheduler.md).  

## See Also  
 [Task Scheduler](../devenv-task-scheduler.md)  
 [TaskScheduler Data Type](../datatypes/devenv-TaskScheduler-Data-Type.md)   
 [CREATETASK Method](devenv-CREATETASK-Method.md)   
 [CANCELTASK Method](devenv-CANCELTASK-Method.md)   
 [SETTASKREADY Method](devenv-SETTASKREADY-Method.md)
