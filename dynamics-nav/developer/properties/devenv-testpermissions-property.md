---
title: "TestPermissions Property"
ms.custom: na
ms.date: 06/19/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.author: jswymer
ms.prod: "dynamics-nav-2017"
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# TestPermissions Property
Specifies a value that can be used to determine which permission sets are used on tests that are run by test codunits or test methods.

## Applies to
*  Test codeunits

    Test codeunits are codeunits that have the **SubType** property set to **Test**.
*  Test methods

    Test methods are methods that have the **MethodType** property set to **Test**.

## Property values
The property has the following values: 

*   **Disabled**
    
*   **Restrictive**
    
*   **NonRestrictive**
    
*   **InheritFromTestCodunit**
    
      **InheritFromTestCodunit** is only relevant for test methods; not test codeunits. It specifies that a test method uses the TestPermissions property setting of the test codeunit to which it belongs. If you use this value on a test codunit, the property will resolve to **Restrictive** at runtime.

Apart from **InheritFromTestCodunit**, the values themselves do not perform any operations or have any specific behavior. Instead, you programmatically define what each value does, and the permissions sets it applies at runtime, by adding code in a test runner codeunit.

## Remarks
The TestPermissions property works together with the **OnBeforeTestRun** and **OnAfterTestRun** triggers in test runner codeunits. The value of of the TestPermissions property is passed as a parameter to the test runner codeunit triggers. The permission sets that are used during a test are determined by the code that you add to the triggers. Typically, you use the **OnBeforeTestRun** trigger to apply permissions sets and the **OnAfterTestRun** trigger to clear permissions sets.
<!--
## See Also
[Testing With Permission Sets](../devenv-testing-permissionsets.md)  
[Testing the Application](../devenv-Testing-the-Application.md)  
[How to: Create a Test Runner Codeunit](../devenv-How-to-Create-a-Test-Runner-Codeunit.md)  
[How to: Create Test Codeunits and Test Methods](../methods/devenv-How-to-Create-Test-Codeunits-and-Test-Methods.md)  
[How to: Create Handler Methods](../methods/devenv-How-to-Create-Handler-Methods.md)  
[Walkthrough: Testing Purchase Invoice Discounts](../Walkthrough--Testing-Purchase-Invoice-Discounts.md)  
[OnAfterTestRun Trigger](../triggers/devenv-trigger-onaftertestrun.md)  
[OnBeforeTestRun Trigger](../triggers/devenv-trigger-onbeforetestrun.md)  -->