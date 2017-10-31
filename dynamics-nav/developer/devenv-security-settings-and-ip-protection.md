---
title: Security Settings and IP Protection
description: This topic explains how to set the security settings and IP protection against downloading or debugging into extension to see the source code.
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 10/31/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Security Settings and IP Protection

This topic contains the information about the security settings and IP protection against downloading or debugging into extension to see the source code in both the extensions V1 and extensions V2.

## Default Security Settings
When you start a new project in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], the app.json file is generated automatically, which contains information about the extension that you are building on. The ``app.json`` file contains build-in security settings in controls called ``showMyCode``, which manages whether it is possible to debug into the extension when taken as a dependency. The default value of the Control ``showMyCode`` is set to **false**, meaning, debugging into extension to view the code is disallowed. Thus, the code is protected against viewing or downloading.

> [!NOTE]  
> The control settings for ``showMyCode`` is not displayed in the ``app.json`` file. 

## Add control settings

It is possible to debug into extension to view the source code by adding the control setting in the ``app.json`` file. In order to allow accessing the source code, add the ``showMyCode`` control in the manifest and set the property value to **true**, as shown below.

```
"showMyCode": true
```

## See Also  

[JSON Files](devenv-json-files.md)  
[Developer Reference](devenv-reference-overview.md)  