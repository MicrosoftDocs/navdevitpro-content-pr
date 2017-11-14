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

The following is a checklist of all requirements that you **must meet before submitting** an extension for validation. If you do not meet these mandatory requirements, your extension will fail validation. 

|Requirement|Example/Guidance|
|-----------|----------------|
|Develop your extension in Visual Studio Code.|[Developing AL Language Extensions](devenv-dev-overview.md)|
|The app.json file has mandatory settings that you must include. Here you can also read more about dependency syntax and multiple countries per a single app syntax.|[Mandatory app.json settings](devenv-json-files.md)|
|Coding of `Date` must follow a specific format (**no longer region specific**)|Use the format `yyyymmddD`. For example, `20170825D`.|
|Remote services (including all Web services calls) can use either HTTP or HTTPS. However, HTTP calls are only possible by using the HttpRequest AL type.|[Guidance on HTTP use](devenv-restapi-overview.md)|
|Only JavaScript based Web client add-ins are supported.The zipping process is handled automatically by the compiler. Simply include the new AL `controladdin` type, JavaScript sources, and build the app.|[Control Add-Ins](devenv-control-addin-object.md)|
|The .app file must be digitally signed.|[Signing the App](https://github.com/Microsoft/AL/issues/720)|
|The user scenario document must contain detailed steps for all setup and user validation testing.|[User Scenario Documentation](../compliance/apptest-userscenario.md)|
|Set the application areas that apply to your controls. Failure to do so will result in the control not appearing in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]|[Application Area guidance](properties/devenv-applicationarea-property.md)|
|Permission set(s) must be created by your extension and when marked, should give the user all setup and usage abilities. A user must not be required to have SUPER permissions for setup and usage of your extension|[Managing Permission Sets](../Managing-Permissions-and-Permission-Sets.md), [How to: Export Permission Sets](../How-to--Import-Export-Permission-Sets-Permissions.md), [Packaging the Permission Set](https://docs.microsoft.com/en-us/powershell/module/microsoft.dynamics.nav.apps.tools/new-navapppackage?view=dynamicsnav-ps-2017)|
|Before submitting for validation, ensure that you can publish/sync/install/uninstall/reinstall your extension. **This must be done in a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] environment**.|[How to publish your app](devenv-how-publish-and-install-an-extension-v2.md)|
|Thoroughly test your extension in a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] environment.|[Testing Your Extension](../compliance/apptest-testingyourextension.md)|
|Do not use `OnBeforeCompanyOpen` or `OnAfterCompanyOpen`|[Replacement Options](../compliance/apptest-onbeforecompanyopen.md)|
|Include the proper upgrade code allowing your app to successfully upgrade from version to version.|[Upgrading Extensions](devenv-upgrading-extensions.md)|
|Pages and code units that are designed to be exposed as Web services must not generate any UI that would cause an exception in the calling code.|[Web Services Usage](../compliance/apptest-webservices.md)|
|You must include all translations of countries your extension is supporting.|[Translating Your Extension](devenv-work-with-translation-files.md)|
|You are required to prefix or suffix the **Name** property of your fields. This eliminates collision between apps.|[Prefix/Suffix Guidelines](../compliance/apptest-prefix-suffix.md)|

## See Also
[Developing AL Language Extensions](devenv-dev-overview.md)  
