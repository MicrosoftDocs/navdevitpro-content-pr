---
title: "Debugging"
description: "Overview of debugging in AL"
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 08/15/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 9cfc02d2-2211-466f-b5e9-8178bdc79311
ms.author: solsen
---

# Debugging
The process of finding and correcting errors is called *debugging*. With Visual Studio Code and the AL Language extension you get an integrated debugger to help you inspect your code to verify that your application can run as expected. You start a debugging session by pressing F5. For the preview, there are a number of limitations to be aware of:

- No support yet of watch or conditional breakpoints
- No breakpoints can be set in "external code" such as base application objects, though you can step through them
- Not all AL types yet show helpful debugging
- Each file must contain only one application object for the breakpoints to be evaluated correctly
- The debugger launches a new client instance each time you press F5. If you close the debugging session, and then start a new session, this new session will rely on a new client instance. We recommend that you close the Web client instances when you close a debugging session.  
- If you stop at a breakpoint and then walk the call stack, you risk seeing duplicate stack traces. This is an issue in VS Code, and we are working with them to get this resolved.
- And finally, using the debugger with the online sandbox signup and AAD authentication method is not yet supported.

## Breakpoints  
The basic concept in debugging is the *breakpoint*, which is a mark that you set on a statement. When the program flow reaches the breakpoint, the debugger stops execution until you instruct it to continue. Without any breakpoints, the code runs without interruption when the debugger is active. <!-- For more information, see [Breakpoints](Breakpoints.md).  -->

## Debugging Shortcuts

|Keystroke    |Action         |
|-------------|---------------|
|F5           |Start debugging|
|Ctrl+F5      |Start without debugging|
|Shift+F5     |Stop debugging|
|Ctrl+Shift+F5|Restart debugging|
|F10          |Step over|
|F11          |Step into|
|Shift+F11    |Step out|

## See Also  
[Developing Extensions](devenv-dev-overview.md)  

