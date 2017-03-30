---
title: "Resolving Codeunit 1410 Doc. Exch. Service Mgt. Error When Converting a Database"
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
manager: edupont
---

# Resolving Codeunit 1410 Doc. Exch. Service Mgt. Error When Converting a Database
Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the **DotNet** data type variables of the local function **Initialize** to the use Microsoft.Dynamics.Nav.OAuth version 10.0.0.0 assembly, as shown in the following table.

|  Variable  |  DatType  |  Subtype  |
|------------|-----------|-----------|
|OAuthAuthorization|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.OAuthAuthorization.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
|OAuthConsumer|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Consumer.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
|OAuthToken|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Token.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|

<!--
## <a name="TestRunnerTriggers"></a>Resolving OnBeforeTestRun and OnAfterTestRun trigger errors

Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the signature of the C/AL OnBeforeTestRun and OnAfterTestRun trigger functions of the test runner codeunits to include the *TestPermissions* parameter.

OnBeforeTestRun trigger before change:
```
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];) Ok : Boolean)
```
OnBeforeTestRun trigger after change:
```
OnBeforeTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];FunctionTestPermissions : TestPermissions) Ok : Boolean)
```
OnAfterTestRun trigger before change:
```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];Success : Boolean)
```
OnAfterTestRun trigger after change:
```
OnAfterTestRun(CodeunitID : Integer;CodeunitName : Text[30];FunctionName : Text[128];FunctionTestPermissions : TestPermissions;Success : Boolean)
```
If you do not change the signature, you will get errors when you compile these objects.
-->
<!--
## <a name="DOL"></a>Resolving Dynamics Online Payment Service related errors
These errors occur because Dynamics Online Payment Service has been discontinued in [!INCLUDE[nav2017](includes/nav2017.md)]. To resolve these errors and other issues related Dynamics Online Payment Services, replace the codeunits that are listed in the table with mock codeunits that are available from the provided links.

|  Codunit  |  Mock Code  |
|-----------|-------------|
|824|[Mock Code for Codeunit 824 DO Encryption Mgt.](Mock-Code-CU824-DO-Encryption-Mgt.md)|
|825|[Mock Code for Codeunit 825 DO Payment Mgt.](Mock-Code-CU825-DO-Payment-Mgt.md)|
|826|[Mock Code for Codeunit 826 DO Payment Integration Mgt.](Mock-Code-CU826-DO-Payment-Integration-Mgt.md)|
|827|[Mock Code for Codeunit 827 DO Payment Card Validation](Mock-Code-CU827-DO-Payment-Card-Validation.md)|
|829|[Mock Code for Codeunit 829 DO Payment Trans. Log Mgt.](Mock-Code-CU829-DO-Payment-Trans-Log-Mgt.md)|
-->
## See Also  
 [Converting a Database](Converting-a-Database.md)  
 [Resolving Compilation Errors When Converting a Dynamics NAV 2016 Database](Resolve-Compile-Errors-When-Converting-Dynamics-NAV-2016-Database.md)  
