---
title: "CANCREATETASK Function"
ms.custom: na
ms.date: 11/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
author: jswymer
---
# CANCREATETASK Function
Indicates whether the user that has permission to create scheduld tasks.  

## Syntax  

```  
[Task =: ]CREATETASK  
```  

## Property Value/Return Value  
 Type: Boolean  

 **true** if creating scheduled tasks is permitted; otherwise, **false**.  

## Remarks  
 For more information about tasks and **TASKSCEDULER** data type functions, see managing tasks [Task Scheduler](Task-Scheduler.md).  

## Example  
 The following example creates a task, and then uses the SETTASKREADY function to set the task to ready.  

 The code requires that you create the following C/AL variable.  

|Variable|DataType|  
|--------------|--------------|  
|TaskID|GUID|  

```  
TaskID := TASKSCHEDULER.CREATETASK(CODEUNIT::"Job Queue Dispatcher", CODEUNIT::"Job Queue Error Handler");  
TASKSCHEDULER.SETTASKREADY(taskID);  
```  

## See Also  
 [Task Scheduler](Task-Scheduler.md)  
 [TaskScheduler Data Type](TaskScheduler-Data-Type.md)   
 [CREATETASK Function](CREATETASK-Function.md)   
 [CANCELTASK Function](CANCELTASK-Function.md)   
 [TASKEXISTS Function](TASKEXISTS-Function.md)
