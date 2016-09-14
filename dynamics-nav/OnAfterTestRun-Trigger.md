---
title: "OnAfterTestRun Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 3900632d-03d8-4b47-9e19-4907bf418380
caps.latest.revision: 14
manager: edupont
---
# OnAfterTestRun Trigger
Executed after a test function of a test codeunit has been run.  
  
## Syntax  
  
```  
  
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];Success : Boolean)  
```  
  
#### Parameters  
 *CodeunitID*  
 Type: Integer  
  
 The ID of the codeunit that has run.  
  
 *CodeunitName*  
 Type: Text  
  
 The name of the test codeunit that has run.  
  
 *FunctionName*  
 Type: Text  
  
 The name of the test function that has run.  
  
> [!NOTE]  
>  This parameter is empty when the **OnAfterTestRun** trigger is called for the whole test codeunit.  
  
 *Success*  
 Type: Boolean  
  
 **true** indicates that the test function run succeeded; otherwise, **false** indicates that the test function run failed.  
  
## Applies To  
 Test runner codeunits. Test runner codeunits have the [SubType Property \(Codeunit\)](SubType-Property--Codeunit-.md) set to **TestRunner**.  
  
> [!NOTE]  
>  This trigger is optional and not available on a test runner codeunit by default. To implement this trigger, you must manually add it as a function.  
  
## Remarks  
 A test runner codeunit manages the execution of test codeunits that are run from its **OnRun** function. When a test codeunit runs, it executes each test function one at a time in the codeunit. When implemented, the **OnAfterTestRun** trigger is called after each test function has run and after all of the test codeunit has run.  
  
 The **OnAfterTestRun** trigger suppresses the automatic display of the results message after the test codeunit runs.  
  
> [!NOTE]  
>  To return the error message for a failed test function run, use the [GETLASTERRORTEXT Function](GETLASTERRORTEXT-Function.md).  
  
 You can use the **OnAfterTestRun** trigger to perform post-processing, such as logging, or to automate tests by integrating the test runner codeunit with a test management framework.  
  
 The **OnAfterTestRun** trigger is run in its own database transaction.  
  
 For more information, see [Testing the Application](Testing-the-Application.md) and [How to: Create a Test Runner Codeunit](How-to--Create-a-Test-Runner-Codeunit.md).  
  
## Example  
 The following **OnAfterTestRun** trigger code logs test results to a test reporting system. This example requires that you create a record variable named *log*.  
  
```  
log.INIT;  
log.UnitId := CodeunitId;  
log.Unit := CodeunitName;  
log.Func := FunctionName;  
log.Before := Before;  
log.After := CURRENTDATETIME;  
If Success THEN  
  log.Status := log.Status::Success  
ELSE BEGIN  
  log.Status := log.Status::Failure;  
  IF FunctionName <> '' THEN  
    log.Message := GETLASTERRORTEXT;  
END  
log.INSERT(true);  
```  
  
 The GETLASTERRORTEXT function returns the text that was contained in the last error message.  
  
## See Also  
 [Testing the Application](Testing-the-Application.md)   
 [How to: Create a Test Runner Codeunit](How-to--Create-a-Test-Runner-Codeunit.md)   
 [How to: Create Test Codeunits and Test Functions](How-to--Create-Test-Codeunits-and-Test-Functions.md)   
 [How to: Create Handler Functions](How-to--Create-Handler-Functions.md)   
 [Walkthrough: Testing Purchase Invoice Discounts](Walkthrough:-Testing-Purchase-Invoice-Discounts.md)   
 [OnBeforeTestRun Trigger](OnBeforeTestRun-Trigger.md)