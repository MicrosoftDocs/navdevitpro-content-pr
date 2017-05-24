---
title: "Page Extension Object"
description: "Description of the page extension object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 01/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---
 

# Page Extension Object
The page extension object extends a [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] page object and adds or overrides the functionality.

The structure of a page is hierarchical and breaks down in to three sections. The first block contains metadata for the overall page; the type of the page and the source table it is showing data from. The next section; the layout, describes the visual parts on the page. The final section details the actions that are published on the page.

In the ```layout``` section, you can use the following functions to place page fields and groups on the page. Similarly, in the ```actions``` section, you use these functions to place actions in the ribbon.   

|Function example|Applies to...|
|--------|-------------|
|```addfirst(General)```|Groups only|
|```addlast(General)```|Groups only|
|```addafter(AddressDetails)```|Fields and groups|
|```addbefore(AddressDetails)```|Fields and groups|
|```movefirst(General)```|Groups only|
|```movelast(General)```|Groups only|
|```moveafter(AddressDetails)```|Fields and groups|
|```movebefore(AddressDetails)```|Fields and groups|

If you want to modify existing fields and groups on a page, you use the ```modify()``` function. See the code example below for syntax.

For more information about changes, see [Differences in the Dynamics NAV Development Environments](devenv-differences.md).

## Snippet support
Typing the shortcut ```tpageext``` will create the basic layout for a table object when using the AL Extension in Visual Studio Code.

## Page Extension examples
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
                    CaptionML = ENU='Hello!';

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

You can reference Report and XMLPort objects and use these objects in the **RunObject** property, as well as, declare variables of the types **Report** and **XMLPort** and call AL functions on them. This page extension object extends the Customer List page object by adding two actions; the first action calls the **Customer - List** report, the second action calls the **Export Contact** xmlport.

```
pageextension 70000030 AddCustomerReport extends "Customer List"
{
    actions
    {
        AddLast("&Customer")
        {
            action("Customer List Report")
            {
                trigger OnAction();
                var
                    rep : Report "Customer - List";
                begin
                    rep.Run;
                end;
            }

            action("Export Contact List")
            {
                trigger OnAction();
                var
                    xml : XmlPort "Export Contact";
                begin
                    xml.Run;
                end;
            }
        }
    }
}
```

## Applies To  
Pages  

## See Also  
[Page Object](devenv-page-object.md)  
[Developer Reference](devenv-reference-overview.md)  
[Page Extension Properties](devenv-page-property-overview.md)  
[Pages](Pages.md)   
[Page Properties](page-properties.md)
