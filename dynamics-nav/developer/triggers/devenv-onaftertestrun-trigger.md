---
title: "OnAfterTestRun Trigger"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
manager: edupont
ms.prod: "dynamics-365-financials"
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# OnAfterTestRun Trigger
Executed after a test  of a test codeunit has been run.  

## Syntax  

```  

OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];MethodName : Text[128];Permissions : TestPermissions; Success : Boolean)  
```  

#### Parameters  
*CodeunitID*  
Type: Integer  

Specifies the ID of the codeunit that has run.  

*CodeunitName*  
Type: Text  

Specifies the name of the test codeunit that has run.  

*MethodName*  
Type: Text  

Specifies the name of the test  that has run.  

> [!NOTE]  
>  This parameter is empty when the **OnAfterTestRun** trigger is called for the whole test codeunit.  

*Permissions*

Type: TestPermissions

Specifies the permission set level to use on the test run. The value is retrieved from the [TestPermissions Property](../properties/devenv-testpermissions-property.md) of the test codeunit or test  that is run. The parameter accepts the following values:

*   **Disabled**
*   **Restrictive**
*   **NonRestrictive**
*   **InheritFromTestCodunit** - Specifies that a test the  uses the **TestPermissions** property setting of the test codeunit to which it belongs.

<!-- For more information, see [Testing With Permission Sets](testing-permissionsets.md).-->

 *Success*  
 Type: Boolean  

 **True** indicates that the test  run succeeded; otherwise, **false** indicates that the test  run failed.  

## Applies To  
 Test runner codeunits. Test runner codeunits have the [SubType Property (Codeunit)](../properties/devenv-subtype-property-codeunit.md) set to **TestRunner**.  

> [!NOTE]  
>  This trigger is optional and not available on a test runner codeunit by default. To implement this trigger, you must manually add it as a .  

## Remarks  
 A test runner codeunit manages the execution of test codeunits that are run from its **OnRun** . When a test codeunit runs, it executes each test  one at a time in the codeunit. When implemented, the **OnAfterTestRun** trigger is called after each test  has run and after all of the test codeunit has run.

The **OnAfterTestRun** trigger suppresses the automatic display of the results message after the test codeunit runs.

> [!NOTE]  
>  To return the error message for a failed test  run, use the [GETLASTERRORTEXT Method](../methods/devenv-getlasterrortext-method.md).  


You can use the **OnAfterTestRun** trigger to perform post-processing, such as logging, or to automate tests by integrating the test runner codeunit with a test management framework.

The *TestPermissions* parameter, enables you can control how to handle applied permission sets, if any, after the test is run. <!-- For more information about testing with permision sets, including an example, see [Testing With Permission Sets](../testing-permissionsets.md).

The **OnAfterTestRun** trigger is run in its own database transaction.


## Example  
 The following **OnAfterTestRun** trigger code logs test results to a test reporting system. This example requires that you create a record variable named *log*.  

```  
log.INIT;  
log.UnitId := CodeunitId;  
log.Unit := CodeunitName;  
log.Func := MethodName;  
log.Before := Before;  
log.After := CURRENTDATETIME;  
If Success THEN  
  log.Status := log.Status::Success  
ELSE BEGIN  
  log.Status := log.Status::Failure;  
  IF MethodName <> '' THEN  
    log.Message := GETLASTERRORTEXT;  
END  
log.INSERT(true);  
```  

 The GETLASTERRORTEXT  returns the text that was contained in the last error message.  

## See Also  
 <!--
 [Testing the Application](testing-the-application.md)   
 [How to: Create a Test Runner Codeunit](how-to-create-a-test-runner-codeunit.md)   
 [How to: Create Test Codeunits and Test Methods](how-to-create-test-codeunits-and-test-methods.md)   
 [How to: Create Handler Methods](../methods/devenv-how-to-create-handler-methods.md)   
 [Walkthrough: Testing Purchase Invoice Discounts](walkthrough-testing-purchase-invoice-discounts.md)   -->
 [OnBeforeTestRun Trigger](devenv-onbeforetestrun-trigger.md)
