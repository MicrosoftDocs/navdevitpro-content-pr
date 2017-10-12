---
title: "Checklist for Submitting Your App"
description: "Describing the steps you must go through to successfully submit your app to AppSource."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---


# Checklist for Submitting Your App

The following is a checklist of all requirements that you must meet before submitting an extension for validation. If you do not meet these mandatory requirements, your extension will fail validation. 

|Requirement|Example/Guidance|
|-----------|----------------|
|Develop your extension in Visual Studio Code.|[Developing AL Language Extensions](devenv-dev-overview.md)|
|The app.json file has mandatory settings that you must include.|[Mandatory app.json settings](devenv-json-files.md)|
|Coding of `Date` must follow a specific format (no longer region specific)|Use the format `yyyymmddD`. For example, `20170825D`.|
|Your extension must use the assigned object range provided to you by Microsoft Dynamics Sales Operations|More detail to come|
|Remote services (including all Web Services calls) can use either HTTP or HTTPS. However, HTTP calls are only possible by using the HttpRequest AL type|[Guidance on HTTP use](devenv-restapi-overview.md).|
|Only JavaScript based Web client add-ins are supported.|The zipping process is handled automatically by the compiler. Simply include the new AL `controladdin` type, JavaScript sources, and build the app.|
|The .app file must be digitally signed.|More detail to come|
|The user scenario document must contain detailed steps for all setup and user validation testing.|Refer to Appendix C for example of an acceptable user scenario doc|
|Set the application areas that apply to your controls. Failure to do so will result in the control not appearing in D365|[Application Area guidance](properties/devenv-applicationarea-property.md)|
|Permission set(s) must be created by your extension and when marked, should give the user all setup and usage abilities. A user must not be required to have SUPER permissions for setup and usage of your extension|[Managing Permission Sets](../Managing-Permissions-and-Permission-Sets.md), [How to: Export Permission Sets](../How-to--Import-Export-Permission-Sets-Permissions.md), [Packaging the Permission Set](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.tools/new-navapppackage?view=dynamicsnav-ps-2017)|
|Before submitting for validation, ensure that you can publish/sync/install/uninstall/reinstall your extension. This must be done on a Dynamics 365 environment.|[How to publish your app](devenv-how-publish-and-install-an-extension-v2.md)|
|Fully test your extension using the partner Dynamics 365 environment (via local deployment, sandbox, or Docker). Instructions for environment setup can be found [here](https://connect.microsoft.com/continue.aspx?pageType=2&regType=2&cru=%2FDynamicsCustomerEngagement%2FInvitationUse.aspx%3FProgramID%3D9343%26InvitationID%3Disvb-GD3P-9PJ3&cu=)|Refer to Appendix D for more detail|
|Ensure you are not using `OnBeforeCompanyOpen` or `OnAfterCompanyOpen`|Alternative methods must be used in their place and that information can be found in Appendix E
|Make sure that your code can be upgraded.|More detail to come|
|Pages and code units that are designed to be exposed as web services must not generate any UI that would cause an exception in the calling code|More detail to come|
|You must include all translations of countries your extension is supporting|Set the CaptionML in source code. For example, ENU = English US, ENG = English UK, DAN = Danish for DK|

## See Also