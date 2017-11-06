---
author: jswymer
title: "Writing extensions installation code"
description: "Describes how to add code to run to initialize data when an extension is installed."
ms.custom: na
ms.date: 11/10/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
---
# Sample Extension Using Extension Objects
The extension in this example uses objects and extension objects to extend base application with a rewards feature for customers. 

The extension enables the ability to assign one of three reward levels to customers, Customers are then given a discount that is based on the reward level.

The sample is includes install and upgrade code.

## Reward Table Object
The following code adds a new table **50100 Reward** for storing the reward levels for customers. 

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

## Reward Card Page Object
The following code adds a new page **50101 Reward Card** for specifying the different reward levels that are stored in the new **Rewards** table.

```
page 50101 "Reward Card"
{
    PageType = Card;
    SourceTable = Reward;

    layout
    {
        area(content)
        {

            {
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

## Reward List Page Object
The following code adds a new page **50102 Rewards List** for displaying the reward levels that are stored in the new **Rewards** table. Selecting a record in the list will open the **Reward Card** page for editing.

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

## Customer Table Extension Object
The following code extends the Customer table with the field `Reward ID`.

```
tableextension 50103 "Customer Ext" extends Customer
{
    fields
    {
        field(50100;"Reward ID";Code[30])
        {
            TableRelation = Reward."Reward ID";
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

## Customer Card Page Extension Object

The following code extends the Customer Card page display the `Reward ID` field. The code also adds an action to open the Rewards List page.

```
pageextension 50100 "Customer Card Ext" extends "Customer Card"
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
```


## Install Code
The following codeunit is run when the extension is first installed or re-installed.

```
codeunit 50103 RewardsInstallCode
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
        InsertRewardLevel('BRONZE', 'Bronze Level', 5);
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


## Upgrade Code
The following codeunit is used to upgrade to the new version.

```
codeunit 50105 RewardsUpgradeCode
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

## See Also  
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md) 
[How to: Publish and Install an Extension](devenv-how-publish-and-install-an-extension-v2.md)  
[Converting Extensions V1 to Extensions V2](devenv-upgrade-v1-to-v2-overview.md)  
