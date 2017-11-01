---
title: "Working with Translation Files"
ms.custom: na
ms.date: 11/01/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6e0ff568-9cad-4b0f-bd97-b8ac5690a470
caps.latest.revision: 26
ms.author: solsen
author: SusanneWindfeldPedersen
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Working with Translation Files
[!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] is multilanguage enabled, which means that you can display the user interface (UI) in different languages. To add a new language to the extension you have built, you must first enable the generation of .xliff files. The .xliff file contains the strings that are specified in properties like Caption and Tooltip.

> [!NOTE] 
> The support for using the ML properties, such as **CaptionML** and **TooltipML**, is being deprecated, so it is recommended to refactor your extension to use the corresponding **Caption** or **Tooltip** property, which is being picked up in the .xliff file.

## Generating the .xliff files
In the app.json file of your extension, you must add the following line:

```
  "features": "TranslationFile"
```

Now, when you run the build command (Ctrl+Shift+B) in Visual Studio Code, a new `\Translations` folder will be generated populated with the .xliff files that contain all the labels, label properties, and report labels that you are using in the extension. The generated .xliff file can now be translated.


## See Also
[Multilanguage Development](devenv-multilanguage-development.md)  