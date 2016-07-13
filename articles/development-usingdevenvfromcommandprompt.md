<properties
                pageTitle="Using the Development Environment from the Command Prompt" | Dynamics NAV"
                description="Describes the how to use finsql.exe."
                services=""
                documentationCenter=""
                authors="jswymer"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="06/16/2016"
    ms.author="jswymer" />

<!-- The content in this article supports Madeira task 169219, which adds a new parameter (showalldesignercolumns) to the finsql.exe. The content should be added to the Using the Development Environment from the Command Prompt article as described.-->

<!-- Change 1: In the "Finsql.exe Command Syntax" section, update the code to include the showalldesignercolumns as follows:-->

```
Finsql.exe [command=<command> | designobject=<object type> <object ID>,] [servername=<server>,] [database=<database>,] [collationname=<collation>,] [file=<file>,] [filter=<filter>], [importaction=<default|overwrite|skip|0|1|2>,] [langid=<ID>,] [logfile=<logfile>,] [navservername=<name>,] [navserverinstance=<instance>,] [navservermanagementport=<port>,] [ntauthentication=<yes|no|0|1>,] [objectcache=<cache>,] [password=<password>,] [temppath=<path>,] [tenant=<tenant ID>,] [username=<user name>,] [synchronizeschemachanges=<yes|no|force>, ] [useoldeditor=<yes|no>,] [showalldesignercolumns=<yes|no|0|1>]
```

<!-- Change 2: In the "Parameters" section, add a row for the "showalldesignercolumns" parameter as follows:-->

|  showalldesignercolumns |  Specifies whether to hide or show the **Visible** and **ApplicationArea** columns in Page Designer. The possible values are: **no**, **0**, **yes**, and **1**.</br></br>
**no** or **0** - Hides the columns. This is the default setting.</br></br>
**yes** or **1** - Shows the column.
</br></br>**Note** This parameter is only relevant the very first time the development environment is opened for a new installation. If the development environment has been opened before, this parameter is ignored, and the  column setup parameters are retrieved from the fin.zup file that is used by the development environment. By default, the fin.zup file is located in the  C:\Users\jswymer\AppData\Roaming folder.

|  All|

<!-- Change 3: In the introduction change the path of the finsql.exe as follows:-->

By default, finsql.exe is located at C:\Program Files (x86)\Microsoft Dynamics NAV\91\RoleTailored Client\.
