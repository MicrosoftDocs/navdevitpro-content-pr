---
title: "Security Settings and IP Protection"
description: This topic explains how to set the security settings and IP protection against downloading or debugging into extension to see the source code.
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/01/2017
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

This topic contains the information about the security settings and providing Intellectual Property (IP) protection against downloading or debugging into an extension to see the source code in the V2 extensions.

 The [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] extension development package provides a pre-configured setting for IP protection against viewing or downloading the code of the extensions. However, these settings can also be controlled in the manifest; the `app.json` file.

 ## Default IP Protection settings
When you start a new project in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], an ``app.json`` file is generated automatically, which contains information about the extension that you are building on. The ``app.json`` file contains a setting called ``showMyCode``, which controls whether it is possible to debug into the extension, when that extension is taken as a dependency. The default value of this property is set to **false**. This means that debugging into an extension to view the code is not allowed.

> [!NOTE]  
> The ``showMyCode`` setting is not displayed in the code, when the ``app.json`` file is generated.

## Change the IP Protection settings
Allow debugging into an extension to view the source code by adding a simple setting in the ``app.json`` file. Add the ``showMyCode`` property in the manifest and set the property value to **true**, as shown in the example below.

```
"showMyCode": true
```

By adding this setting, you enable debugging into an extension to view the source code when that extension is set as a dependency. 

## See Also  
[JSON Files](devenv-json-files.md)  
[Developer Reference](devenv-reference-overview.md)  