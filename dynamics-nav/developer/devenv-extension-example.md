---
author: jswymer
title: "Sample extension example that uses new objects and extension objects"
description: "Includes code for an example extension, complete with new objects, extension objects, and install and upgrade code."
ms.custom: na
ms.date: 11/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---

# Sample Extension With Extension Objects, Install Code, and Upgrade Code
This sample extension adds new objects and extension objects to the base application for a simple rewards feature for customers. The sample includes install, In-Client Designer and upgrade code. <!-- elaborate on the second line + proper naming Designer -->
<!-- proper mentioning of product Visual Studio Code -->
To get started, create an AL project in Visual Code. Create objects that use the sample code from the sections that follow, and build the extension package. Then, you can publish and install the extension on your tenants. 
 
<!-- Prerequisites section should go here - what do you need? How do you sign up? Use the getting started topic as pointer -->

## Rewards extension overview
The extension enables the ability to assign one of three reward levels to customers: Gold, Silver, and Bronze. Each reward level can be assigned a discount percentage. <!-- Can we add more of a story? -->

For the upgrade scenario, you will change the Bronze level to Aluminum. 

## Reward table object
The following code adds a new table **50100 Reward** for storing the reward levels for customers. The table consists of three fields: **Reward ID**, **Description**, and **Discount Percentage**.

<!-- add more code comments in the example below even though it seems to be stating the obvious. What does clustered mean? -->
```
table 50100 Reward
{
    fields
    {
        field(1;"Reward ID";Code[30])
        {
        }
        field(2;Description;Text[250])
        {
            // It specifies that a value in the selected field must be entered.
            NotBlank = true;
        }
        field(3;"Discount Percentage";Decimal)
        {
            MinValue = 0;
            MaxValue = 100;
            DecimalPlaces = 2;
        }
    }

    keys
    {
        key(PK;"Reward ID")
        {
            Clustered = true;
        }
    }
}
```

<!-- separate the TIP information, move the tip about the table up before you add the table object -->

>[!TIP]
> Type `ttable` followed by the Tab key. This snippet will create a basic layout for a table object. 
> Also, for more information about table properties, go to [Table Properties](properties/devenv-table-properties.md).

## Reward card page object
The following code adds a new page **50101 Reward Card** for specifying the different reward levels that are stored in the new **Rewards** table. <!-- it adds the user interface so that the user can enter information -->

<!-- add code comments -->

```
page 50101 "Reward Card"
{
    PageType = Card;
    SourceTable = Reward;

    layout
    {
        area(content)
        {
           // {
            group(GroupName)
            {
                field("Reward Id";"Reward ID")
                {
                    ApplicationArea = All;
                }
                field(Description;Description)
                {
                    ApplicationArea = All;
                }
                field("Discount Percentage";"Discount Percentage")
                {
                    ApplicationArea = All;
                }
            }
        }
    }
}
```
<!-- move the tip up before you create the table -->
> [!TIP]
> Use the snippet `tpage, Page of type card` to create the basic structure for the page object.

## Reward list page object
The following code adds a new page **50102 Rewards List** for displaying the reward levels that are stored in the new **Rewards** table. Selecting a record in the list will open the **Reward Card** page for editing.

<!-- add code comments - what does this code do more specifically? -->
```
page 50102 "Reward List"
{
    PageType = List;
    SourceTable = Reward;
    CardPageId = "Reward Card";

    layout
    {
        area(content)
        {
            repeater(Group)
            {
                field("Reward ID";"Reward ID")
                {
                    ApplicationArea = All;
                }
                field(Description;Description)
                {
                    ApplicationArea = All;
                }
                field("Discount Percentage";"Discount Percentage")
                {
                    ApplicationArea = All;
                }
            }
        }
    }
}
```
<!-- Move first line of tip up before creating the page -->
> [!TIP]
> Use the snippet `tpage, Page of type list` to create the basic structure for the page object. 
> After you create the page, update startupObjectId in the launch.json file to 50102 and select the F5 key to see the new page in the web client.
<!-- Take second line out of TIP structure, it is just information to get to the next step -->

## In-Client Designer 

The following code modifies the layout of a page as a WYSIWYG editor. Add two new fields to the Reward table in `RewardTable`.`al` file. 
<!-- use code tag around all of the file name -->

<!-- Just name it Designer. And how do you end up with this code? With the Designer you just drag and drop them, explain how you get back to the Visual Studio Code editor and see the code that Designer generated and how you need to add more logic in the next section. Explain why more. -->
```
  field(4;"Minimum Purchase";Decimal)
        {
            MinValue = 0;
            DecimalPlaces = 2;
        }
        field(5;"Last Modified Date";Date)
        {
            // It sets a value that indicates whether the field can be edited through the UI.
            Editable = false;
        }

```

Add the following code to keep the `Last Modified Date` accurate. For more information about triggers, see [Table and Field Triggers](triggers/devenv-table-and-field-triggers.md).

```
    trigger OnInsert();
    begin
        SetLastModifiedDate();
    end;

    trigger OnModify();
    begin
        SetLastModifiedDate();
    end;

    trigger OnDelete();
    begin
    end;
 
    trigger OnRename();
    begin
        SetLastModifiedDate();
    end;

    local procedure SetLastModifiedDate();
    begin
        Rec."Last Modified Date" := Today();
    end;
```
<!-- This next comment doesn't make sense to me here -->
If you want to modify the current extension, launch the Designer with the F6 key. If you want to create the new extension, launch the Designer from within the web client.

> [!TIP]
> For more information about In-Client Designer, go to [Designer](devenv-inclient-designer.md). <!-- name Designer -->

## Customer table extension object
<!-- Explain why we want to add a table extension object, now that we've created "clean" objects that aren't extensions, what is the need for an extension object? --> 
<!-- Dig into the code and add more useful code comments to the developer -->

The following code extends the Customer table with the `Reward ID` field.

```
tableextension 50103 "Customer Ext" extends Customer
{
    fields
    {
        field(50100;"Reward ID";Code[30])
        {
            TableRelation = Reward."Reward ID";
            // It sets whether to validate a table relationship.
            ValidateTableRelation = true;
           
            trigger OnValidate();
            begin
                if (Rec."Reward ID" <> xRec."Reward ID") and
                    (Rec.Blocked <> Blocked::" ") then
                begin
                    Error('Cannot update the rewards status of a blocked customer.')
                end;
            end;
        }
    }
}

```
<!-- Move this tip up before creating the table extension object -->
> [!TIP]
> Use the snippet `ttableext` to create a basic structure for the table extension object. 

## Customer card page extension object

The following code extends the Customer Card page display the `Reward ID` field. The code also adds an action to open the **Reward List** page. <!-- More description on why we use an extension object -->
<!-- plus code comments, why do we set these values? -->

```
pageextension 50104 "Customer Card Ext" extends "Customer Card"
    {
    layout
    {
        addlast(General)
        {
            field("Reward ID";"Reward ID")
            {
                ApplicationArea = All;
                Lookup = true;
            }
        }
    }

    actions
    {
        addfirst(Navigation)
        {
            action("Rewards")
            {
                ApplicationArea = All;
                RunObject = page "Reward List";
            }
        }
    }
}
```
<!-- Move the snippet tip up before the object. Take the next paragraph out of the tip structure, it's a follow up on the next step. --> 
> [!TIP]
> Use the shortcuts `tpageext` to create the basic structure for the page extension object.
> At this point, reward levels can be created and assigned to customers. To do that, update the startupObjectId value in launch.json to 21 and select the F5 key to start the debugger.

## Install code
To perform operations on the database to support the installation of an extension, you add code to an install codeunit. In this example, the following install codeunit initializes Customer records with the reward levels. The install codeunit will run when the extension is installed for the first time and when the same version is re-installed. For more information about install code, see [Writing Extension Install Code](devenv-extension-install-code.md).

<!-- Add information about this code unit - what does it do? Can you add code comments? Is there a snippet? Move that from under the code to up before the code -->

```
codeunit 50105 RewardsInstallCode
{
    Subtype = Install;
    
    trigger OnInstallAppPerCompany();
    var
        Reward : Record Reward;
    begin
        if Reward.IsEmpty() then begin
            InsertDefaultRewards();
        end;
    end;

    procedure InsertDefaultRewards();
    begin
        InsertRewardLevel('GOLD', 'Gold Level', 20);
        InsertRewardLevel('SILVER', 'Silver Level', 10);
        InsertRewardLevel('BRONZE', 'Bronze Level', 5); //
        // InsertRewardLevel('ALUMINUM', 'Aluminum Level', 5);
    end;

    procedure InsertRewardLevel(ID : Code[30]; Description : Text[250]; Discount : Decimal);
    var
        Reward : Record Reward;
    begin
        Reward.Init();
        Reward."Reward ID" := ID;
        Reward.Description := Description;
        Reward."Discount Percentage" := Discount;
        Reward.Insert();
    end;

}
```
> [!TIP]
> Use the shortcuts `tcodunit` and `ttrigger` to create the basic structure for the codeunit and trigger.

## Upgrade code
When you upgrade an extension to a newer version, if any modifications to the existing data are required to support the upgrade, you must write upgrade code in an upgrade codeunit. In this example, the following upgrade codeunit contains code that changes the **Bronze** reward level on customer records to **Aluminum**. The upgrade codeunit will run when you run the Upgrade-NAVApp cmdlet. For more information about writing and running upgrade code, see [Upgrading Extension](devenv-upgrading-extensions.md).

> [!IMPORTANT]
> Remember to increase the `version` number of the extension in the app.json file. <!-- Add link to the JSON Files topic -->

```
codeunit 50106 RewardsUpgradeCode
{
    Subtype = Upgrade;

    trigger OnUpgradePerCompany();
    var
        InstallCode : Codeunit InstallCode;
        Reward : Record Reward;
        Module : ModuleInfo;
    begin
        NavApp.GetCurrentModuleInfo(Module);
        if Module.DataVersion.Major = 1 then begin
            Reward.Get('BRONZE');
            Reward.Rename('ALUMINUM');
            Reward.Description := 'Aluminum Level';
            Reward.Modify();
        end;
    end;
}
```
<!-- Do a follow-up section. What have we achieved with the extension? What is the user now able to do? Is there something that he could do next? Any interesting readings? -->

## See Also  
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md)  
[How to: Publish and Install an Extension](devenv-how-publish-and-install-an-extension-v2.md)  
[Converting Extensions V1 to Extensions V2](devenv-upgrade-v1-to-v2-overview.md) 

