<properties
                pageTitle="OnAfterTestRun Trigger | Dynamics NAV"
                services=""
                description="Describes the OnAfterTestRun trigger on test runner codeunits in Dynamics NAV"
                documentationCenter=""
                authors="jswymer"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="06/16/2016"
    ms.author="jswymer" />

# OnAfterTestRun Trigger
Executed after a test function of a test codeunit has been run.

```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; FunctionTestPermissions : TestPermissions; Success : Boolean)
```

## Parameters
*CodeunitID*

Type: Integer

The ID of the codeunit that has run.

*CodeunitName*

Type: Text

The name of the test codeunit that has run.

*FunctionName*

Type: Text

The name of the test function that has run.

**Note:**  This parameter is empty when the OnAfterTestRun trigger is called for the whole test codeunit.

*TestPermissions*

Type: TestPermissionse

The value of the **TestPermissions** property of the test function for determining which permission sets to test. The parameter accepts the following values:

*   **Disabled**
*   **Restrictive**
*   **NonRestrictive**
*   **InheritFromTestCodunit** - Specifies that a test the function uses the **TestPermissions** property setting of the test codeunit to which it belongs.

*Success*

Type: Boolean

**true** indicates that the test function run succeeded; otherwise, **false** indicates that the test function run failed.

## Applies to
Test runner codeunits. Test runner codeunits have the **SubType** property set to **TestRunner**.

**Note**: This trigger is optional and not available on a test runner codeunit by default. To implement this trigger, you must manually add it as a function.  

## Remarks
A test runner codeunit manages the execution of test codeunits that are run from its **OnRun** function. When a test codeunit runs, it executes each test function one at a time in the codeunit. When implemented, the **OnAfterTestRun** trigger is called after each test function has run and after all of the test codeunit has run.

*   The **OnAfterTestRun** trigger suppresses the automatic display of the results message after the test codeunit runs.

    **Note:**  To return the error message for a failed test function run, use the GETLASTERRORTEXT function.

*   You can use the **OnAfterTestRun** trigger to perform post-processing, such as logging, or to automate tests by integrating the test runner codeunit with a test management framework.

*   The *TestPermissions* parameter, enables you can control how to handle applied permission sets, if any, after the test is run. For more information about testing with permision sets, including an example, see [Testing With Permission Sets](testing-permissionsets.md).

*   The **OnAfterTestRun** trigger is run in its own database transaction.

##  Example
The following **OnAfterTestRun** trigger code logs test results to a test reporting system. This example requires that you create a record variable named log.

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
[TestPermissions Property](property-testpermissions.md)  
[OnBeforeTestRun Trigger](trigger-onbeforetestrun.md)  
[Testing With Permission Sets](testing-permissionsets.md)  
[Testing the Application](testing-testingapplication.md)  
[How to: Create a Test Runner Codeunit](testing-howcreatetestrunnercodeunit)  
[How to: Create Test Codeunits and Test Functions](testing-howcreatetestcodeunitsfunctions.md)  
[How to: Create Handler Functions](howcreatehandlerfunctions.md)  
[Walkthrough: Testing Purchase Invoice Discounts](testing-walkthroughtestingpurchaseinvoice.md)  
