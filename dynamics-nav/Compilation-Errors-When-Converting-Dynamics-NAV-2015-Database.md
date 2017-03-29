---
title: "Compilation Errors When Converting a Microsoft Dynamics NAV 2016 Database"
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
# Resolving Compilation Errors When Converting a Dynamics NAV 2016 Database
When you convert a [!INCLUDE[navcorfu](includes/navcorfu_md.md)] database, you will receive compilation errors in several standard [!INCLUDE[navnow](includes/navnow_md.md)] objects. This artile descibes how to resolve these errors.

## Compilation Errors
The following table lists the compilation errors that might occur when build the server application objects during the database conversion, with a link to a solution for fixing the problem.

|  Object Type  |  Object ID  |  Object Name  |  Function/Trigger  |  Error Message  |  Solution  |
|---------------|-------------|---------------|--------------------|------------|------------|
|Table|5330|CRM Connection Setup|CreateOrganizationService|You have specified an unknown variable. CrmServiceClient Define the variable under 'Global C/AL symbols'.|You must update the C/AL code of Table 5330 to support the latest Microsoft Dynamics CRM Software Development KIT (SDK). To do this, import the code from the article [Updated Table 5330 CRM Connection Setup](Updated-Code-Table5330-CRM-Connection-Setup.md) as a text (.txt type) file to the database. |
|Codeunit|824|DO Encryption Mgt.|Encrypt|You have specified an unknown variable. KeyExists Define the variable under 'Global C/AL symbols'.|See [Resolving Dynamics Online Payment Service related errors](#DOL).|
|Codeunit|826|DO Payment Integration Mgt.|RefreshTransactionStatus|You have specified an unknown variable. Payment Define the variable under 'Global C/AL symbols'.|See [Resolving Dynamics Online Payment Service related errors](#DOL).|
|Codeunit|829|DO Payment Trans. Log Mgt.|CompleteTransLogEntry|You have specified an unknown variable. IsSuccess Define the variable under 'Global C/AL symbols'.|See [Resolving Dynamics Online Payment Service related errors](#DOL).|
|Codeunit|1410|Doc. Exch. Service Mgt.|Initialize|You have specified an unknown variable. Consumer Define the variable under 'Global C/AL symbols'.|See [Resolving Codeunit 1410 Doc. Exch. Service Mgt. Error.](#CU1410).|
|Codeunit|130400|CAL Test Runner|OnBeforeTestRun|The OnBeforeTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun trigger errors](#TestRunnerTriggers).|
|Codeunit|130400|CAL Test Runner|OnAfterTestRun|The OnAfterTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun trigger errors](#TestRunnerTriggers).|
|Codeunit|130402|CAL Test Runner|OnBeforeTestRun|The OnBeforeTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun trigger errors](#TestRunnerTriggers).|
|Codeunit|130402|CAL Command Line Test Runner|OnAfterTestRun|The OnAfterTestRun trigger signature is not valid.|See [Resolving OnBeforeTestRun and OnAfterTestRun trigger errors](#TestRunnerTriggers).|

## <a name="CU1410"></a>Resolving Codeunit 1410 Doc. Exch. Service Mgt. error  
Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the **DotNet** data type variables of the local function **Initialize** to the use Microsoft.Dynamics.Nav.OAuth version 10.0.0.0 assembly, as shown in the following table.

|  Variable  |  DatType  |  Subtype  |
|------------|-----------|-----------|
|OAuthAuthorization|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.OAuthAuthorization.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
|OAuthConsumer|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Consumer.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|
|OAuthToken|DotNet|Microsoft.Dynamics.Nav.OAuthHelper.Token.'Microsoft.Dynamics.Nav.OAuth, Version=10.0.0.0'|

## <a name="TestRunnerTriggers"></a>Resolving OnBeforeTestRun and OnAfterTestRun trigger errors

Use the [!INCLUDE[nav_dev_short_md](includes/nav_dev_short_md.md)] to change the signature of the C/AL OnBeforeTestRun and OnAfterTestRun trigger functions of the test runner codeunits to include the *TestPermission* parameter.

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

## <a name="DOL"></a>Resolving Dynamics Online Payment Service related errors
These errors occur because Dynamics Online Payment Service has been discontunied in [!INCLUDE[nav2017](includes/nav2017.md)]. To resolve these errors and other issues related Dynamics Online Payment Services, replace the codunits that are listed in the table with mock codunits  that is available from the link.

|  Codunit  |  Mock Code  |
|-----------|-------------|
|824|[Mock Code for Codeunit 824 DO Encryption Mgt.](Mock-Code-CU824-DO-Encryption-Mgt.md)|
|825|[Mock Code for Codeunit 825 DO Payment Mgt.](Mock-Code-CU825-DO-Payment-Mgt.md)|
|826|[Mock Code for Codeunit 826 DO Payment Integration Mgt.](Mock-Code-CU826-DO-Payment-Integration-Mgt.md)|
|827|[Mock Code for Codeunit 827 DO Payment Card Validation](Mock-Code-CU827-DO-Payment-Card-Validation.md)|
|829|[Mock Code for Codeunit 829 DO Payment Trans. Log Mgt.](Mock-Code-CU829-DO-Payment-Trans-Log-Mgt.md)|

## Resolving My Settings errors
After the database conversion, you will have to mocThe following table describes the before and after code that will help you resolve the warnings that you receive when you compile codeunit 43 **LanguageManagement**.
1. In the C/AL code of codunit 1 Application Management, add a global function  
1. In the C/AL code for page 9176 My Settings, and replace the code on the

|||  
|-|-|  
|Before|`Language.SETRANGE("STX File Exist",TRUE);`|  
|After|`Language.SETRANGE("Localization Exist",TRUE);`|  

## See Also  
 [Converting a Database](Converting-a-Database.md)
