---
title: "ExportToNewSyntax flag"
description: "Description of the ExportToNewSyntax flag."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 06/12/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

# Delta files generated with ExportToNewSyntax Flag
## Description
The `Compare-NAVApplicationObject` has been used to create V1 extensions by generating delta files from two versions of a set of application objects. The `ExportToNewSyntax` switch was added to this commandlet to allow the generation of delta files that can be used to create V2 extensions. The purpose of this flag is to instruct the commandlet to generate delta files that contain additional information needed to generate the correct structure and layout of V2 extension objects.  

> [!IMPORTANT]  
> The Txt2Al conversion tool will reject delta files that were generated without using the -ExportToNewSyntax flag.

## Problem
Consider the following page layout:

```
GroupA 
{
	ActionA {}
}
GroupB 
{
}

```

On this page, a V1 extension will be created that adds a GroupC after GroupA.
```
GroupA 
{
	ActionA {}
}
GroupC {}
GroupB {}
```

The delta file generated without the `ExportToNewSyntax`switch will contain the following information:
```
InsertAfter ActionA -> GroupC level 1
```
If you want to convert this to a V2 page extension using the Txt2Al conversion tool, you will obtain a page extension containing the following layout:
```
...
layout
{
	addafter(ActionA)
	{
		group(C) {}
	}
}
...

``` 
The resulting V2 extension will have a different layout than the V1 extension. Using the `ExportToNewSyntax` switch for the `Compare-NAVApplicationObject` commandlet will prevent the described issue and produce a delta file that can be converted to a V2 extension where the page layout is identical to the V1 extension. 

## Flag
Specifies that the user will use the generated delta files with the Txt2Al conversion tool to convert to a V2 extension. 

|Parameter   |Description|
|------------|-----------|
|Type: |SwitchParameter|
|Aliases: |None|
|Position: |Named|
|Default value: |None|
|Accept pipeline input: |False|
|Accept wildcard characters: |False|

## Example

Compare-NAVApplicationObject -OriginalPath "C:\PageWith2Controls.txt" -ModifiedPath "C:\PageWith3Controls.txt" -ExportToNewSyntax
 

## See Also
[The Txt2Al Conversion Tool](devenv-txt2al-tool.md)  
[Developing Extensions](devenv-dev-overview.md)   
[Converting Extensions V1 to Extensions V2](devenv-upgrade-v1-to-v2-overview.md)

