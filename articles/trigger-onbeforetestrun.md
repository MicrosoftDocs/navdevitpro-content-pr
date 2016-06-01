<properties
                pageTitle="OnBeforeTestRun Trigger | Project “Madeira”"
                description="Describes the OnBeforeTestRun trigger on test runner codeunits in Project “Madeira”"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>

# OnBeforeTestRun Trigger
Executed before a test function of a test codeunit is run.

```
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128]; TestPermissions : Text) Ok : Boolean)

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

Type: TestPermissions

The value of the **TestPermissions** property of the test function for determining which permission sets to test. The parameter accepts the following values:

*   **Disabled**
*   **Restrictive**
*   **NonRestrictive**
*   **InheritFromTestCodunit** - Specifies that a test the function uses the **TestPermissions** property setting of the test codeunit to which it belongs.

## Return Value
*Ok*

Type: Boolean

**true** to run the test function; otherwise, **false**. This value is checked after each function call.

## Applies to
Test runner codeunits. Test runner codeunits have the **SubType** Property set to **TestRunner**.

**Note**: This trigger is optional and not available on a test runner codeunit by default. To implement this trigger, you must manually add it as a function.  

## Remarks
A test runner codeunit manages the execution of test codeunits that are run from its **OnRun** function. When a test codeunit runs, it executes each test function in the codeunit, one at a time. The **OnBeforeTestRun** trigger is called before the test codeunit, the OnRun function, and each test function.

You can use the **OnBeforeTestRun** trigger to perform preprocessing, such as general initialization and logging, or to automate tests by integrating the test runner codeunit with a test management framework.

By using the *TestPermissions* parameter, you can add code to control which permission sets, if any, to test.

The **OnBeforeTestRun** trigger is run in its own database transaction.

For more information, see Testing the Application and How to: Create a Test Runner Codeunit.

## Example
The following **OnBeforeTestRun** trigger code initializes a logging variable and returns true to indicate that the test function should execute. This example requires that you create the following global variable.

|Variable Name  |Data Type  |
|----------|-------------|
|Before|DateTime|

```
Before := CURRENTDATETIME;
EXIT(true);
```

## See Also  
[TestPermissions Property](property-testpermissions.md)  
[OnAfterTestRun Trigger](trigger-onaftertestrun.md)  
[Testing With Permission Sets](testing-permissionsets.md)  
[Testing the Application](testing-testingapplication.md)  
[How to: Create a Test Runner Codeunit](testing-howcreatetestrunnercodeunit)  
[How to: Create Test Codeunits and Test Functions](testing-howcreatetestcodeunitsfunctions.md)  
[How to: Create Handler Functions](howcreatehandlerfunctions.md)  
[Walkthrough: Testing Purchase Invoice Discounts](testing-walkthroughtestingpurchaseinvoice.md)  
