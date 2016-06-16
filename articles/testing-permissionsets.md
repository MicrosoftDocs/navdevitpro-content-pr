<properties
                pageTitle="Testing Permission Sets | Dynamics NAV"
                description="Describes how you can test permission sets that are used in the application."
                services=""
                documentationCenter="NAV"
                authors="jswymer"/>
<tags
    ms.service="dynamics-nav"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="NAV"
    ms.date="06/16/2016"
    ms.author="jswymer" />

# Testing With Permission Sets
You can write application tests in C/AL that use specific permission sets when the test is run. The permission sets define the access rights (such as read, write, and execute ) on tables, reports, functions, and other objects in the database. Without applying any permission sets, a test will run with full permissions, similar to the rights that are granted by the SUPER permission set.

To test with permission sets, you modify test codeunits or test functions and test runner codeunits.

-   Test codeunits and test functions

    Test codeunits and test functions include the **TestPermissions** property. This  property has the following values: **Disabled**, **Restrictive**, **NonRestrictive**, **InheritFromCodeunit**. At runtime, the property value is passed on to the **OnBeforeTestRun** and **OnAfterTestRun** triggers of test runner codeunits. The values alone do not do anything. You define which permission sets are applied to the test for each value by coding the **OnBeforeTestRun** and **OnAfterTestRun** triggers of a test runner codeunit.
*   Test runner codeunits

    You use test runner codeunits apply the permission sets to the test by adding code to the **OnBeforeTestRun** and **OnAfterTestRun** triggers. These triggers include the *FunctionTestPermissions* parameter (data type TestPermissions) that takes the value of the **TestPermissions** property that is passed on from the test codeunit or test function that is run. You add code on these triggers to define what permission sets to use for the test based on the value of the *FunctionTestPermissions* parameter.

    Typically, you code the **OnBeforeTestRun** trigger to assign the permission sets to the test, and the **OnAfterTestRun** trigger to clear the permission sets.

## Example
This simple code example illustrates how to test with permission sets. It uses a test runner code unit to apply permissions sets to test functions based on the different values of the **TestPermissions** property of the test function.

For applying permission sets, the code uses DotNet data type variable for **Microsoft.Dynamics.Nav.PermissionTestHelper** assembly. This assembly is provided as a server add-in with the Dynamics NAV Server installation.

The OnBeforeTestRun trigger will apply one of three permission sets, which have the Role IDs **O365 BASIC**, **O365 BUS FULL ACCESS**, and **SUPER**.

```
OBJECT Codeunit 90000 MyTestPermissionsTestRunner
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=Test Objects;
  }
  PROPERTIES
  {
    Subtype=TestRunner;
    OnRun=BEGIN
          END;

  }
  CODE
  {
    VAR
      PermissionTestHelper@1000 : DotNet "'Microsoft.Dynamics.Nav.PermissionTestHelper, Version=9.1.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Dynamics.Nav.Runtime.PermissionTestHelper";

    PROCEDURE OnBeforeTestRun@1102601000(CodeunitId@1102601000 : Integer;CodeunitName@1102601001 : Text[30];FunctionName@1102601002 : Text[128];Permissions@1000 : TestPermissions) : Boolean;
    BEGIN
      IF ISNULL(PermissionTestHelper) THEN
        PermissionTestHelper := PermissionTestHelper.PermissionTestHelper;

      PermissionTestHelper.Clear;

      CASE Permissions OF
        TESTPERMISSIONS::Restrictive:
          PermissionTestHelper.AddEffectivePermissionSet('O365 BASIC');
        TESTPERMISSIONS::NonRestrictive:
          PermissionTestHelper.AddEffectivePermissionSet('O365 BUS FULL ACCESS');
        TESTPERMISSIONS::Disabled:
          PermissionTestHelper.AddEffectivePermissionSet('SUPER');
      END;

      EXIT(TRUE);
    END;

    PROCEDURE OnAfterTestRun@1102601002(CodeunitId@1003 : Integer;CodeunitName@1002 : Text[30];FunctionName@1001 : Text[128];Permissions@1000 : TestPermissions;Success@1102601003 : Boolean);
    VAR
      PermissionTestHelper@1004 : DotNet "'Microsoft.Dynamics.Nav.PermissionTestHelper, Version=9.1.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Dynamics.Nav.Runtime.PermissionTestHelper";
    BEGIN
      IF ISNULL(PermissionTestHelper) THEN
        PermissionTestHelper := PermissionTestHelper.PermissionTestHelper;

      IF Permissions <> TESTPERMISSIONS::Disabled THEN
        PermissionTestHelper.Clear;
    END;

    BEGIN
    END.
  }
}

```
## See Also  
[TestPermissions Property](property-testpermissions.md)  
[OnBeforeTestRun](trigger-onbeforetestrun.md)  
[OnAfterTestRun](trigger-onaftertestrun.md)  
[Testing the Application](testing-testingapplication.md)  
[How to: Create a Test Runner Codeunit](testing-howcreatetestrunnercodeunit)  
[How to: Create Test Codeunits and Test Functions](testing-howcreatetestcodeunitsfunctions.md)  
[How to: Create Handler Functions](howcreatehandlerfunctions.md)  
[Walkthrough: Testing Purchase Invoice Discounts](testing-walkthroughtestingpurchaseinvoice.md)  
