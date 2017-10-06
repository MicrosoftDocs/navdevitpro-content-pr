---
title: "OnBeforeTestRun Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: SusanneWindfeldPedersen
ms.prod: "dynamics-365-financials"
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnBeforeTestRun Trigger
Executed before a test  of a test codeunit is run.  

## Syntax  

```  

OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];MethodName : Text[128]) Ok : Boolean  
```  

#### Parameters  
 *CodeunitID*  
 Type: Integer  

 Specifies the ID of the codeunit to be run.  

 *CodeunitName*  
 Type: Text  

 The name of the test codeunit to be run.  

 *MethodName*  
 Type: Text  

 Specifies the name of the test  to be run.  

> [!NOTE]  
>  This parameter is empty when the **OnBeforeTestRun** trigger is called for the entire test codeunit.  

*Permissions*

Type: TestPermissions

Specifies the permission set level to use on the test run. The value is retrieved from the [TestPermissions Property](../properties/devenv-testpermissions-property.md) of the test codeunit or test  that is run. The parameter accepts the following values:

*   **Disabled**
*   **Restrictive**
*   **NonRestrictive**
*   **InheritFromTestCodunit** - Specifies that a test the  uses the **TestPermissions** property setting of the test codeunit to which it belongs.

<!-- For more information, see [Testing With Permission Sets](../devenv/testing-permissionsets.md). -->

## Return Value  
 *Ok*  
 Type: Boolean  

 **True** to run the test ; otherwise, **false**. This value is checked after each  call.  

## Applies To  
 Test runner codeunits. Test runner codeunits have the [SubType Property \(Codeunit\)](../properties/devenv-subtype-property-codeunit.md) set to **TestRunner**.  

> [!NOTE]  
>  This trigger is optional and not available on a test runner codeunit by default. To implement this trigger, you must manually add it as a .  

## Remarks  
 A test runner codeunit manages the execution of test codeunits that are run from its **OnRun** . When a test codeunit runs, it executes each test  in the codeunit, one at a time. The **OnBeforeTestRun** trigger is called before the test codeunit, the **OnRun** , and each test .  

  You can use the **OnBeforeTestRun** triggers to perform preprocessing, such as general initialization and logging, or to automate tests by integrating the test runner codeunit with a test management framework.  
  
  By using the *TestPermissions* parameter, you can add code to control which permission sets, if any, to test.
  
  The **OnBeforeTestRun** trigger is run in its own database transaction.  

 <!-- For more information, see [Testing the Application](../devenv-testing-the-application.md) and [How to: Create a Test Runner Codeunit](../devenv-how-to-create-a-test-runner-codeunit.md).  -->

## Example  
 The following **OnBeforeTestRun** trigger code initializes a logging variable and returns **true** to indicate that the test  should execute. This example requires that you create the following global variable.  

|Name|DataType|  
|----------|--------------|  
|Before|DateTime|  

```  
Before := CURRENTDATETIME;  
EXIT(true);  
```  

## See Also  
<!--
 [Testing the Application](../devenv-testing-the-application.md)  
 [How to: Create a Test Runner Codeunit](../devenv-how-to-create-a-test-runner-codeunit.md)   
 [How to: Create Test Codeunits and Test Methods](../devenv-how-to-create-test-codeunits-and-test-methods.md)  
 [How to: Create Handler Methods](../devenv-how-to-create-handler-methods.md)   
 [Walkthrough: Testing Purchase Invoice Discounts](../devenv-walkthrough-testing-purchase-invoice-discounts.md)   
 -->
 [Triggers](devenv-triggers.md)  
 [TestPermissions Property](../properties/devenv-testpermissions-property.md)  
 [Codeunit Triggers](devenv-codeunit-triggers.md)  
 [OnAfterTestRun Trigger](devenv-onaftertestrun-trigger.md)  
 [Triggers](devenv-triggers.md)  
