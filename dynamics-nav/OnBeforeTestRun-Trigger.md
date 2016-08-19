---
title: "OnBeforeTestRun Trigger"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: be024339-53bf-4458-a67f-d0c0abeef80b
caps.latest.revision: 12
---
# OnBeforeTestRun Trigger
Executed before a test function of a test codeunit is run.  
  
## Syntax  
  
```  
  
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]) Ok : Boolean  
```  
  
#### Parameters  
 *CodeunitID*  
 Type: Integer  
  
 The ID of the codeunit to be run.  
  
 *CodeunitName*  
 Type: Text  
  
 The name of the test codeunit to be run.  
  
 *FunctionName*  
 Type: Text  
  
 The name of the test function to be run.  
  
> [!NOTE]  
>  This parameter is empty when the **OnBeforeTestRun** trigger is called for the entire test codeunit.  
  
## Return Value  
 *Ok*  
 Type: Boolean  
  
 **true** to run the test function; otherwise, **false**. This value is checked after each function call.  
  
## Applies To  
 Test runner codeunits. Test runner codeunits have the [SubType Property \(Codeunit\)](../dynamics-nav/SubType-Property--Codeunit-.md) set to **TestRunner**.  
  
> [!NOTE]  
>  This trigger is optional and not available on a test runner codeunit by default. To implement this trigger, you must manually add it as a function.  
  
## Remarks  
 A test runner codeunit manages the execution of test codeunits that are run from its **OnRun** function. When a test codeunit runs, it executes each test function in the codeunit, one at a time. The **OnBeforeTestRun** trigger is called before the test codeunit, the **OnRun** function, and each test function.  
  
 The **OnBeforeTestRun** trigger is run in its own database transaction.  
  
 You can use the **OnBeforeTestRun** triggers to perform preprocessing, such as general initialization and logging, or to automate tests by integrating the test runner codeunit with a test management framework.  
  
 For more information, see [Testing the Application](../dynamics-nav/Testing-the-Application.md) and [How to: Create a Test Runner Codeunit](../Topic/How%20to:%20Create%20a%20Test%20Runner%20Codeunit.md).  
  
## Example  
 The following **OnBeforeTestRun** trigger code initializes a logging variable and returns **true** to indicate that the test function should execute. This example requires that you create the following global variable.  
  
|Name|DataType|  
|----------|--------------|  
|Before|DateTime|  
  
```  
Before := CURRENTDATETIME;  
EXIT(true);  
```  
  
## See Also  
 [Testing the Application](../dynamics-nav/Testing-the-Application.md)   
 [How to: Create a Test Runner Codeunit](../Topic/How%20to:%20Create%20a%20Test%20Runner%20Codeunit.md)   
 [How to: Create Test Codeunits and Test Functions](../Topic/How%20to:%20Create%20Test%20Codeunits%20and%20Test%20Functions.md)   
 [How to: Create Handler Functions](../Topic/How%20to:%20Create%20Handler%20Functions.md)   
 [Walkthrough: Testing Purchase Invoice Discounts](../Topic/Walkthrough:%20Testing%20Purchase%20Invoice%20Discounts.md)   
 [OnAfterTestRun Trigger](../dynamics-nav/OnAfterTestRun-Trigger.md)