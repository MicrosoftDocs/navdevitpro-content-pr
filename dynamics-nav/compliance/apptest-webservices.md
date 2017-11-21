---
title: "Pages and code units that are designed to be exposed as web services must not generate any UI that would cause an exception in the calling code"
description: "Describing the steps you must go through to successfully submit your app to AppSource."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/09/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: rweigel
caps.latest.revision: 18
---

# Pages and code units that are designed to be exposed as Web services must not generate any UI that would cause an exception in the calling code

**SUMMARY AND INTENT**: When writing code for web services, you must not use end-user confirmation dialog boxes, message boxes, or any other page constructs in the code. Because a web service runs independently of a user interface, running this type of code causes the code to throw an exception. The exception can be caught and handled, but the Web service will not complete.

**RESOURCES**: For more information, see [Microsoft Dynamics NAV Web Services](http://go.microsoft.com/fwlink/?LinkId=252362) in the Microsoft Dynamics NAV Developer and IT Pro Documentation.

**HOW TO COMPLY**: Ensure that code for pages and code units that are being exposed as Web services do not use any end-user confirmation dialog boxes or message boxes.

**TEST METHODOLOGY**: To verify this requirement, the following tests will be performed:
1. Identify the pages and code units that are exposed as Web services during the installation of the extension
2. Using code inspection, verify that functions from the following table are not used by the pages and code units published by the installation without conditional code that is based on GUIALLOWED=FALSE or CurrFieldNo=0 circumventing their call

|AL Function|Applies to|
|-----------|----------|
|CONFIRM|Codeunit/page|
|STRMENU|Codeunit/page|
|(Form RunModal)|Page|
|Page of type Confirmation Dialog|Page|
|(Request form)|Page|
|ERROR|Codeunit/page|
|BEEP|Codeunit/page|
|YIELD|Codeunit/page|

Additionally, when running the page or code unit as a Web service, the following exception should never occur:

*Microsoft.Dynamics.Nav.Types.Exceptions.NavNCLCallbackNotAllowedException: Callback functions are not allowed.*
