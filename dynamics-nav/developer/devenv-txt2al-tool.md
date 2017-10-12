---
title: "The Txt2Al Conversion Tool"
description: "Description of the converter tool."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 06/07/2017
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

# The Txt2Al Conversion Tool
The Txt2Al conversion tool allows you to take existing Dynamics NAV objects that have been exported in .txt format and convert them into the new .al format. The .al format is used when developing extensions for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. Converting the objects consists of following two steps:

1. Exporting the objects from C/SIDE in a cleaned format.
2. Converting the objects to the new syntax.

## To run the Txt2Al conversion tool
To run the Txt2Al conversion tool, follow the steps outlined below.

1. Start with a clean Dynamics NAV database and make an export of **all the baseline objects** in the command line using the following syntax:
```finsql.exe Command=ExportToNewSyntax, File=<filename.txt>, Database="<databasename>", ServerName=<servername> ,Filter=Type=table;ID=<tableID>```. The following example exports the table **225** from the Demo Database NAV 10-0 database:  
  ```finsql.exe Command=ExportToNewSyntax, File=exportedObjects.txt, Database="Demo Database NAV (10-0)", ServerName=.\NAVDEMO ,Filter=Type=table;ID=225```
2. Import your solution using the import option in C/SIDE.
3. Export all **new and/or modified** objects using the following syntax:
```finsql.exe Command=ExportToNewSyntax, File=<filename.txt>, Database="<databasename>", ServerName=<servername> ,Filter=Type=table;ID=<tableID>```. The following example exports the table **225** from the Demo Database NAV 10-0 database:  
  ```finsql.exe Command=ExportToNewSyntax, File=exportedObjects.txt, Database="Demo Database NAV (10-0)", ServerName=.\NAVDEMO ,Filter=Type=table;ID=225```
5. Create .delta files using the Compare-NAVApplicationObject powershell script. For more information, see [How to: Develop an Extension v1.0](https://msdn.microsoft.com/en-us/library/mt574395(v=nav.90).aspx).
6. Go to the *\Program Files(x86)\DynamicsNAV\100\RoleTailored Client* folder and locate the **txt2al.exe** converter tool. 
7. Run the tool from the command line using the following syntax:  
```txt2al --source --target --rename --type --extensionStartId```

|Parameter   |Description|
|------------|-----------|
|--source=Path |Required. The path of the directory containing the .delta  files.|
|--target=Path |Required. The path of the directory into which the converted AL files will be placed.|
|--rename |Rename the output files to prevent clashes with the source .txt files.|
|--type=ObjectType |The type of object to convert. Allowed values: Codeunit, Table, Page, Report, Query, XmlPort|
|--extensionStartId |The starting numeric ID of the extension objects (Default: 70000000). It will be incremented by 1 for each extension object.|
|--help |Show help screen.|

> [!NOTE] 
> It is recommended to only use the conversion tool for export. Importing objects that have been exported can damage your application.

## See Also
[Developing Extensions](devenv-dev-overview.md)  
[Developer Reference](devenv-reference-overview.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Report Object](devenv-report-object.md)  
[Page Properties](properties/devenv-page-property-overview.md)