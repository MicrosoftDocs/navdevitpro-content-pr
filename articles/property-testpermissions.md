<properties
                pageTitle="TestPermissions Property | Dynamics NAV"
                description="Describes the TestPermissions property on codeunits in Dynamics NAV"
                services=""
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

# TestPermissions Property
Specifies a value that can be used to determine which permission sets are used on tests that are run by test codunits or test functions.

## Applies to
*  Test codeunits

    Test codeunits are codeunits that have the **SubType** property set to **Test**.
*  Test functions

    Test functions are functions that have the **FunctionType** property set to **Test**.

## Property values
The property has the following values:

*   **Disabled**
*   **Restrictive**
*   **NonRestrictive**
*   **InheritFromTestCodunit** - This value is only relevant for test functions; not test codeunits. It specifies that a test function uses the TestPermissions property setting of the test codeunit to which it belongs. If you use this value on a test codunit, the property will resolve to **Restrictive** at runtime.

Apart from **InheritFromTestCodunit**, the values themselves do not perform any operations. Instead, you programmatically define what each value does and the permissions sets it applies at runtime by adding code in a test runner codeunit.

## Remarks
The TestPermissions property works together with the **OnBeforeTestRun** and **OnAfterTestRun** triggers in test runner codeunits. The value of of this property is passed as a parameter to the test runner triggers. The permission sets that are used during a test are determined by code that you add to the triggers. Typically, you use the **OnBeforeTestRun** trigger to apply permissions sets and the **OnAfterTestRun** trigger to clear permissions sets.

## See Also
[OnAfterTestRun Trigger](trigger-onaftertestrun.md)  
[OnBeforeTestRun Trigger](trigger-onbeforetestrun.md)  
[Testing With Permission Sets](testing-permissionsets.md)  
[Testing the Application](testing-testingapplication.md)  
[How to: Create a Test Runner Codeunit](testing-howcreatetestrunnercodeunit)  
[How to: Create Test Codeunits and Test Functions](testing-howcreatetestcodeunitsfunctions.md)  
[How to: Create Handler Functions](howcreatehandlerfunctions.md)  
[Walkthrough: Testing Purchase Invoice Discounts](testing-walkthroughtestingpurchaseinvoice.md)  
