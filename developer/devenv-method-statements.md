---
title: "AL Method Statements"
ms.custom: na
ms.date: 06/21/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 65df44e6-e734-43c8-bb31-4b7afe749cbd
caps.latest.revision: 6
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# AL Method Statements
You use method statements to execute either built-in system method or user-defined method. Method calls may include parameters, which are passed to the method.  

 If you assign the return value of a method call to a variable, then you use the method statement as part of an assignment statement.  

 Triggers are AL elements that consist of an event and a method. Triggers execute a method when a certain event occurs. For more information, see [Triggers Overview](devenv-triggers-overview.md) and [Triggers](Triggers.md).  

## Example  
 The following example calls the [INIT Method (Record)](methods/devenv-init-method-record.md) on a record variable. This example requires that you create the following variable.  

|Name|DataType|Subtype|  
|----|--------|-------|  
|CustomerRecord|Record|Customer|  

```  
CustomerRecord.INIT;  
```  

## Example  
 The following example calls the [CALCDATE Method (Date)](methods/devenv-calcdate-method-date.md) and assigns the return value to a variable. The CALCDATE function has two parameters. This example uses the DateExpression and ReferenceDate variables in the function call. The values of the variables are passed to the CALCDATE function.  

 This example requires that you create the following variables.  

|Name|DataType|Length|  
|----------|--------------|------------|  
|DateExpression|Text|30|  
|ReferenceDate|Date||  
|NewDate|Date||  

```  
DateExpression := '<-7D>'  
ReferenceDate := 112509D;  
NewDate := CALCDATE(DateExpression, ReferenceDate);  
```  

 After you run the code in this example, the NewDate variable represents the date November 18, 2009.  

## See Also  
 [AL Methods](methods/devenv-al-methods.md)   
 [Triggers](triggers/devenv-triggers.md)   
 [AL Simple Statements](devenv-al-simple-statements.md)
