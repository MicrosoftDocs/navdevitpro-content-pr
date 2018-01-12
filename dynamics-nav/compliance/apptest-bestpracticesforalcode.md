---
title: "Best Practices for AL code"
description: "Document the Best Practices for AL Code."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 11/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Best Practices for AL Code/Extensions 
This page defines the best practices to follow when writing AL extensions.

## Extension Structure 

An extension is fully contained in a single folder. This folder can contain an app.json file, a BuildMetadata.xml file, an image file representing the extension's logo, a "src", and a "test" folder. The extension does not need to follow a flat structure,  which means that, depending on the amount of application files, additional folders can be used in the "src" or "test" folders to group objects based on their functionality.   
<!--The structure of an extension has app.json in root folder, BuildMetadata.xml and the extension logo. Additional folders such as src and test are used to group objects based on the functionality and the amount of files. 

What does it mean?
Res for resources -->

## ID Range 
Extensions that are applicable for multiple countries are included in the W1 range. In case W1 range is too small, it is extended to extension range. However, extensions for only one country stay in the local country range. 

For more information on number ranges in different countries, see [Number Ranges](../Number-Ranges-for-Text-Constants.md).

<!-- 
Table Extensions that belong to W1 range, new start with the beginning of the extension range

pageextension 1857 PurchaseInvoiceForecastExt extends "Purchase Invoice" 
add file PAGEXT1857.TXT in App\BaseApp.
-->
> [!REMEMBER]  
> Block the ID in BaseApp for W1, Extension range IDs or in the country folder for country extensions by adding an empty file in the required folder. The ID should be blocked also when you do your tests. 

## File Naming 

Each file name starts with the corresponding type and ID, followed by a dot for full objects or a dash for extensions. The name of the object is written only with characters [A-Za-z0-9] and dot al is used for the file type. 

### Structure 

|Full objects|Extensions|
|------|---------------------------|
|`<Type><Id>.<ObjectName>.al`|`<Type><BaseId>-Ext<ObjectId>.<ObjectName>.al`|

### Type map

|Object|Abbreviation|
|------|---------------------------|
|Page|Pag|
|Page Extension|PageExt|
|Codeunit|Cod|
|Table|Tab|
|Table Extension|TabExt|
|XML Port|Xml|
|Report|Rep|
|Query|Que|

### Example

|Object name|File name|
|------|---------------------------|
|codeunit 1000 "Job Calculate WIP"|Cod1000.JobCalculateWIP.al|
|page 21 "Customer Card"|Pag21.CustomerCard.al|
|page 1234 "MyPag" extends "Customer Card"|Pag21-Ext1234.MyPag.al|


## Formatting

It is recommended to keep your AL code properly formatted as it follows:
- Use all lowercase letters for reserved language keywords. Built-in functions and types are not included in this rule because they are written in the PascalCase style. 
- Use four spaces for indentation. 
- Curly braces are always on a new line. If there is one property, put it in a single line. 
<!-- Curly braces: Curly braces are always on new line, expect if there is zero or one property, put it in a single line.  
-->

```
page 123 PageName

{

    actions

    {

        area(Processing)

        {

            action(ActionName)

            {

                trigger OnAction()

                begin

                end;

            }

        }

    }



    var

        TempCustomer: temporary Record Customer;

    [EventSubscriber(ObjectType::Page, Page::"Item Card", 'OnAfterGetCurrRecordEvent', '', false, false)]

    local procedure OnOpenItemCard(var rec: Record Item)

    var

        OnRecord: Option " ", Item, Contact;

    begin

        EnablePictureAnalyzerNotification(rec."No.", OnRecord::Item);

    end;

}

```

The AL Language extension offers users the option to automatically format their source code. For more information on how to use it, see [AL Formatter](../developer/devenv-al-formatter.md).

## Line Length
There is no line length restriction, but code can become unreadable due to this issue.<!-- In this case, remind the coder in CodeReview that it must be fixed.  -->

## Object Naming
All object names are not prefixed. They start with feature/group name, followed by the logical name as in these two examples: `Intrastat extension validation codeunit for Denmark`, `codeunit 123 "IntrastatDK Validation"`


> [!NOTE]  
> "MS - " prefix is not required. 

## File Structure 

The file structure for all objects is as follows:
1. Properties
2. Object specific constructs such as:
    *  Table fields
    *  Page layout
    *  Actions
3. Global variables
    * Labels (old Text Constants)
    * Global variables
4. Functions


## Referencing 

Objects are referenced by name, not by ID. 


### Example
```
Page.RunModal(Page::"Customer Card", ...)
 
var

Customer: Record Customer;
```
## Variable Naming 

All variables remain unchanged when they are named. This means that they are named using PascalCase style, temporary variables have the Temp prefix, and objects must include the object name in the name. 

 
### Example 
```
TempCustomer: temporary Record Customer;

Vendor: Record Vendor; 
```

## Function Declaration 
To declare a function, follow the guidelines below: 
- Include a space after a semicolon when declaring multiple arguments. 
- Semicolons are not used at the end of a function header. 
- Functions are named as variables using PascalCase style. 
- There should always be a blank line between function declarations. 

### Example
 
```
local procedure MyProcedure(Customer: Record Customer; Int: Integer)
begin

end

// space

local procedure MyProcedure2(Customer: Record Customer; Int: Integer)

begin

end
```

## Function Calling 
When calling a function, include one space after each command if multiple parameters are passed. Parenthesis are needed for a function call and also for system calls such as: Init(), Modify(), Insert() etc. 

### Example:
```
MyProcedure();

MyProcedure(1);

MyProcedure(1, 2); 
```

## Type Definition (colon)
When declaring a variable or a parameter, the name of that variable or parameter must be immediately followed by a colon, by a single space, and by the type of the variable/parameter.

```
Var

Number: Integer;

local procedure MyProcedure(a: Integer; b: Integer): Integer 
```