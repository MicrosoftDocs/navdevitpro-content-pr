---
title: "The Txt2Al Conversion Tool"
description: "Description of the converter tool."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 04/25/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

## The Txt2Al Conversion Tool
The Txt2Al conversion tool allows you to take existing Dynamics NAV objects that have been exported in .txt format and convert them into the new .al format. The .al format is used when developing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. Converting the objects consists of following two steps:

1. Exporting the objects from C/SIDE in a cleaned format.
2. Converting the objects to the new syntax.

## To run the Txt2Al conversion tool
To run the Txt2Al conversion tool, follow the steps outlined below.

1. Export the objects using the command line; the following example exports the table **225**  
```finsql.exe Command=ExportToNewSyntax, File=exportedObjects.txt, Database="Demo Database NAV (10.0)", ServerName=.\NAVDEMO ,Filter=Type=table;ID=225```

2. Go to the *\Program Files(x86)\DynamicsNAV\100\RoleTailored Client* folder and locate the **txt2al.exe** converter tool. 
3. Run the tool from the command line using the following syntax:  
```txt2al --source --target --rename --type```

|Parameter|Description|
|---------|-----------|
|--source |Required. The path of the directory containing the TXT files.|
|--target|Required. The path of the directory into which the converted AL files will be placed.|
|--rename|Rename the output files to prevent clashes with the source .txt files.|
|--type|The type of object to convert. Allowed values: Codeunit, Table, Page, Report, Query, XmlPort|
|--help|Show help screen.|

> NOTE: It is recommended to only use the conversion tool for export. Importing objects that have been exported can damage your application.

## See Also
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)  
[Developer Reference](newdev-reference-overview.md)  
[Page Extension Object](newdev-page-ext-object.md)  
[Report Object](newdev-report-object.md)  
[Pages](pages.md)  
[Tables](tables.md)  
[Page Properties](page-properties.md)