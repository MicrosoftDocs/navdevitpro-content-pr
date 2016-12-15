---
title: "Page Extension Object"
description: "Description of the page extension object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/15/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---
[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Page Extension Object
The page extension object extends a [!INCLUDE[navnow_md](includes/navnow_md.md)] page object and adds or overrides the functionality. 

The structure of a page is hierarchical and breaks down in to three sections. The first block contains metadata for the overall page; the type of the page and the source table it is showing data from. The next section; the layout, describes the visual parts on the page. The final section details the actions that are published on the page.

In the ```layout``` section, you can use the following functions to place page fields and groups on the page. Similarly, in the ```actions``` section, you use these functions to place actions in the ribbon.   

|Function example|Applies to...|
|--------|-------------|
|```addfirst(General)```|Groups only|
|```addlast(General)```|Groups only|
|```addafter(AddressDetails; "Post Code")```|Fields and groups|
|```addbefore(AddressDetails; "Post Code")```|Fields and groups|
|```movefirst(General)```|Groups only|
|```movelast(General)```|Groups only|
|```moveafter(AddressDetails; "Post Code")```|Fields and groups|
|```movebefore(AddressDetails; "Post Code")```|Fields and groups|

If you want to modify existing fields and groups on a page, you use the ```modify()``` function. See the code example below for syntax. 

For more information about changes, see [Differences in the Dynamics NAV Development Environments](newdev-differences.md).

## Snippet support
Typing the shortcut ```tpageext``` will create the basic layout for a table object when using the AL Extension in Visual Studio Code.

## Page Extension example
The following page extension object extends the Customer Card page object by adding a field control ```ShoeSize``` to the ```General``` group on the page. The field control is added as the last control in the group using the ```addlast``` function. In the actions area, you can see what the syntax looks like for actions that execute triggers and actions that run objects. 

```
pageextension 70000020 CustomerCardExtension extends "Customer Card"
{
    layout
    {
        addlast(General)
        {
            field("Shoe Size"; ShoeSize)
            {
                CaptionML = ENU='ShoeSize';

                trigger OnValidate();
                begin
                    if ShoeSize < 10 then
                        Error('Feet too small');
                end;
            }
        }

        modify("Address 2")
        {
            CaptionML = ENU='New Address 2';
        }
    }

    actions
    {
        addlast(Creation)
        {
            group(MyActionGroup)
            {
                Action(MyAction1)
                {
                    CaptionML = ENU = 'Hello!';

                    trigger OnAction();
                    begin
                        Message('My message');
                    end;
                }

                Action(MyAction2)
                {
                    RunObject = codeunit "Activities Mgt.";
                }
            }
        }
    }

   var
        Msg : TextConst ENU='Hello from my method';

    trigger OnOpenPage();
    begin
        Message(Msg);
    end;
} 
``` 

## Applies To  
Pages  
  
## See Also  
[Page Object](newdev-page-object.md)  
[Developer Reference](newdev-reference-overview.md)  
[Pages](Pages.md)   
[Page Properties](page-properties.md)
