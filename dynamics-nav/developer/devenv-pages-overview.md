---
title: "Pages Overview"
ms.custom: na
ms.date: 06/07/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 0ba68a20-d83a-4e4c-9938-dac7fa8f5461
caps.latest.revision: 35
manager: edupont
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Pages Overview

In [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)], pages are the main way to display and organize data. Pages are the primary object that a user will interact with and have a different behavior based on the type of page that you choose. Pages are designed independently of the device they are to be rendered on, and in this way the same page can be reused across phone, tablet, and web clients.

A page is defined in code as an object composed of controls, properties, actions, and triggers. You can also use the in-client designer in [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] to create a page. For more information, see <>.

Whether you're creating a new page, or extending en existing page, you will add a new .al file to your project and describe the page object in code. The difference is basically that for a new page, you need to define the entire page, whereas when modifying an existing page, you only add the extra functionality or modify the existing. 

The structure of a page is hierarchical and breaks down in to three sections. The first block contains metadata for the overall page. The metadata describes the page type and the source table it is showing data from. The next section; the layout, describes the visual parts on the page. The final section details the actions that are published on the page.

Furthermore, the page has properties. Properties work in the same way for pages as they do for other [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] objects. For more information, see [Page Properties](properties/devenv-page-property-overview.md).  

## Page Metadata
For a new page object, you must at least specify the type of page; `PageType` and the data source; `SourceTable` of the page. And you can also set other metadata at the beginning of the declaration of the page object, such as:

```
page Id PageName
{
    PageType = List;
    SourceTable = TableName;
    ...
}
```
### Types of Pages  
Which page type you choose depends on the application task that you want to support, the content that you want to display, and how you want to display it. The Role Center page is the main or home page and it helps the user focus on the most important daily tasks and activities. Other types of pages, such as list pages or card pages are typically linked from the home page for easy access. The following page types are available:  

|Page type   |Description|
|------------|-----------|
|`RoleCenter`||
|`Card`||
|`CardPart`||
|`List`||
|`ListPart`||
|`ListPlus`||
|`Document`||
|`WorkSheet`||
|`ConfirmationDialog`||
|`StandardDialog`||
|`NavigatePage`||

## Page Layout
The page layout of the page object determines what the page will look like and is specified in the `layout` section. The `layout` contains one or more `area` sections that define a certain placement on the page. 

You can choose between the following `area` categories:

|Area type|Placement on the page|
|---------|-----------------|
|`Content`|The content area displays the content of a RoleCenter or List page.|
|`FactBoxes`|The factbox area is placed to the right-most side of a page. Displays content related to an item om the main content page.|
|`RoleCenter`|The RoleCenter is the main page of the application and is used for quick access to frequently used information and tasks.|

### Adding and moving
In the `layout` section, you can use the following methods to place and move fields and groups on the page. Similarly, in the `actions` section, which is described [below](#page-actions), you use these methods to place actions in the ribbon. 

|Method example         |Applies to |
|-----------------------|-------------|
|```addfirst(General)```|Groups only|
|```addlast(General)``` |Groups only|
|```addafter(AddressDetails)``` |Fields and groups|
|```addbefore(AddressDetails)```|Fields and groups|
|```movefirst(General)```|Groups only|
|```movelast(General)``` |Groups only|
|```moveafter(AddressDetails)``` |Fields and groups|
|```movebefore(AddressDetails)```|Fields and groups|

If you want to modify existing fields and groups on a page, you use the `modify` function. See the code example below for syntax.

### Page controls  
You can add the page controls to a page depending on the page type you have chosen. 
  
repeater
cuegroup
part

<!--
-   FactBoxes (area)  
  
-   FastTab  ??
  
-   CueGroup  
  
-   HomePart  
  
-   ChartPart  
  
-   PagePart  
  
-   SystemPart  
  
-   Ribbon  
  
-   Filter Pane  
-->
  
## Page actions
All pages contain menu items and navigation controls called actions. The ```actions``` section of the page describes what the user is able to do on a page and must be designed with the user's need for process support in mind. Actions are added to the ribbon or as activity buttons/cues. The following example creates a new group in the ribbon and places it last in the General group.

```
addlast(General)
        {
            group(MyActionGroup)
            {
                Action(MyAction1)
                {
                    CaptionML = ENU='Hello!';

                    trigger OnAction();
                    begin
                        Message('My message');
                    end;
                }
             }
         }   
        ...
```

For more information see, [Actions Overview](devenv-actions-overview.md).
  
## Best practices for designing pages  
We recommend that you simplify the user experience by reducing what users see by default. You can promote the information that the users most frequently need to see and hide the less important information. For example:  
  
-   Place common tasks in the ribbon  
  
-   Organize information pages under FastTabs and, by default, hide the FastTabs that are infrequently visited.  
  
-   Use one to three FactBoxes on a page to provide supplementary information and a place for adding notes.  
  
## See Also  
[Page Properties Overview](properties/devenv-page-property-overview.md)