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
This walkthrough will guide you through all the steps that you must follow to create a sample extension in AL. New objects and extension objects will be added to the base application for a simple rewards feature for customers. Every section of this exercise includes code that serves for installing, customizing, or upgrading this sample extension. The final result can be published and installed on your tenants.

## About This Walkthrough
This walkthrough illustrates the following tasks:

- Setting up a sandbox environment

- Downloading and installing Visual Studio Code and the AL extension for Visual Studio Code.

- Developing a sample extension with a table, a card page, and a list page.

- Using the Designer to modify visual aspects of the extension. 

- Creating extension objects that can be used to modify page and table objects.

- Initializing the database during the installation of the extension.

- Upgrading and preserving data during the upgrade of the extension.

## Prerequisites
To complete this walkthrough, you will need: 

- A Dynamics 365 for Financials tenant.

- Visual Studio Code.

- The AL extension for Visual Studio Code.

For more information on how to get started with your first extension for Dynamics 365 for Financials, see [Getting Started](devenv-get-started.md).


## Story  
<!-- Is this the right persona? Where is the list of personas? -->
Viktor is a developer who has started working for a small-sized company that uses the NAV ERP system. His first task is to develop an extension that allows users to assign one of three reward levels to customers therefore enhancing the overall customer experience.
Viktor tries to create a sample extension using the AL language, but he needs more instructions.
<!-- Rephrase -->
He gradually learns about the type of objects that can be created in AL and how they are used to build an extension package. He learns to publish and install the extension on his tenants. 


<!-- OR
## Rewards extension overview
The extension enables the ability to assign one of three reward levels to customers: Gold, Silver, and Bronze. Each reward level can be assigned a discount percentage. The code used to install the extension will create the base for these levels, while the upgrade scenario will change the Bronze level to Aluminum. The update code is executed when data for an extension is older than the version being applied. Different types of objects available within the AL development environment will build the foundation of the user interface, allowing the user to edit the information.
 Can we add more of a story?  -->

## Reward table object
The following code adds a new table **50100 Reward** for storing the reward levels for customers. The table consists of three fields: **Reward ID**, **Description**, and **Discount Percentage**. 

Properties can be created for every field, depending on the scope. For example, the **Description** field must contain a value of type text and it cannot exceed the limit of 250 characters. The second field contains three properties that are used to set the range of the discount percentage assigned to every customer.

>[!TIP]
> Type `ttable` followed by the Tab key. This snippet will create a basic layout for a table object.

```
table 50100 Reward
{
    fields
    {
        // The "Reward ID" field represents the unique identifier 
        // of the reward and can contain up to 30 Code characters. 
        field(1;"Reward ID";Code[30])
        {
        }

        // The Description field can contain a string 
        // with up to 250 characters.
        field(2;Description;Text[250])
        {
            // This property specified that 
            // this field cannot be left empty.
            NotBlank = true;
        }

        // The "Discount Percentage" field is a Decimal numeric value
        // that represents the discount that will 
        // be applied for this reward.
        field(3;"Discount Percentage";Decimal)
        {
            // The MinValue property sets the minimum value for the "Discount Percentage" field.
            MinValue = 0;

            // The MaxValue property sets the maximum value for the "Discount Percentage" field.
            MaxValue = 100;
            
            // The DecimalPlaces property is set to 2 to display discount values with exactly 2 decimals.
            DecimalPlaces = 2;
        }
    }

    keys
    {
        // The field "Reward ID" is used as the primary key of this table.
        key(PK;"Reward ID")
        {
            // Create a clustered index from this key.
            Clustered = true;
        }
    }
}
```

For more information about table properties, go to [Table Properties](properties/devenv-table-properties.md).


## Reward card page object
The following code adds a new page **50101 Reward Card** for viewing and editing the different reward levels that are stored in the new **Reward** table. Pages are the primary object that a user will interact with and have a different behavior based on the type of page that you choose. The **Reward Card** page is of type card and it is used to view and edit one record or entity from the **Reward table**. 

> [!TIP]
> Use the snippet `tpage, Page of type card` to create the basic structure for the page object.

```
page 50101 "Reward Card"
{
    // The page will be of type "Card" and it will be displayed in the characteristic manner.
    PageType = Card;
    
    // The source table shows data from the Reward table.
    SourceTable = Reward;

    // The layout describes the visual parts on the page
    layout
    {
        area(content)
        {           
            group(Reward)
            {
                field("Reward Id";"Reward ID")
                {
                    // ApplicationArea sets the application area that 
                    // applies to the page field and action controls. 
                    // Setting the property to All means that the control 
                    // will always appear in the user interface.
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
For more information about the types of pages in AL, go to [Pages Overview](devenv-pages-overview.md).

## Reward list page object
The following code adds the **50102 Reward List** page that enables users to view the contents of the **Reward** table and edit specific records by selecting them and viewing them in the **Reward Card** page. 

> [!TIP]
> Use the snippet `tpage, Page of type list` to create the basic structure for the page object. 

```
page 50102 "Reward List"
{
    // Specify that this page will be a list page.
    PageType = List;

    // The data of this page is taken from the Reward table.
    SourceTable = Reward;

    // The CardPageId is set to the Reward Card previously created.
    // This will allow users to open records from the list in the "Reward Card" page.
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
After you have created the objects, update the startupObjectId in the launch.json file to 50102, the ID of the "Reward List" page and select the Ctrl+F5 shortcut to see the new page in the web client.
For more information, see [JSON Files](devenv-json-files.md).

## Designer 

Dynamics 365 for Finance and Operations, Business edition **Designer** works in the web client and allows modifying the current page. It enables users to add existing table fields, move fields around, or remove fields from the page. Users can make changes to display the information they need, where they need it by using drag-and-drop components.  
To show how the Designer changes the design of a page, you begin by adding two new fields to the **Reward** table. These fields will be used later on to exemplify the Designer's properties. 
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
The **Last Modified Date** field requires constant changes to remain accurate. To keep it updated, triggers will be used. Triggers are predefined methods that are executed when certain actions happen. 

```
    // OnInsert trigger executes when a new record is inserted into the table.
    trigger OnInsert();
    begin
        SetLastModifiedDate();
    end;

    // OnModify trigger executes when a record in the table is modified .
    trigger OnModify();
    begin
        SetLastModifiedDate();
    end;

    // OnDelete trigger executes when a record in the table is deleted.
    trigger OnDelete();
    begin
    end;

    // OnRename trigger executes when a record in a primary key field is modified.
    trigger OnRename();
    begin
        SetLastModifiedDate();
    end;

    // On the current record, the the value of the "Last Modified Date" field to the current date.
    local procedure SetLastModifiedDate();
    begin
        Rec."Last Modified Date" := Today();
    end;
```
For more information about triggers, see [Table and Field Triggers](triggers/devenv-table-and-field-triggers.md).

From this point, changes to the **Customer** card page can be done either manually by adding the code below in Visual Studio Code or by using the Designer's functions. Both ways lead to the same results, but the Designer speeds up the process. 


```
field("Minimum Purchase";"Minimum Purchase")
{
    ApplicationArea = All;
}

field("Last Modified Date";"Last Modified Date")
{
    ApplicationArea = All;
}

``` 
Using the F6 key shortcut in Visual Studio Code launches the browser and enters the Designer. Note that every time you start designing, you create a new extension and the changes you make in the Designer will apply to all users.   
To add the same fields, but without using any code, you start by hiding the **Last Modified Date** field on the list page. Clicking on the purple chevron to the right of the field and selecting **Remove** will do this for you.    
![Remove](media/last_modified_date.png)

<!-- Should I add images for these steps? -->
Follow the next steps to customize the card page:
- Navigate to the **Reward Card** page by clicking on **+ new**.  
- Select **More** from the Designer bar. 
- Select **Field** from the Designer bar to show the list of available fields. 
- Drag the **Minimum Purchase** and **Last Modified Date** fields from the list onto the page in the **General** group. 
- Click on **General** in the group caption to enable the value to be edited. Change the caption to **Info** and press **Enter**.

After making these adjustments, finish up your design by choosing Stop Designing, which allows you to name the extension with an option to download code, and save the extension for the tenant. If you choose not to download the code at the end, you can still pull the changes that via the Ctrl+F7 shortcut from Visual Studio Code. You can also uninstall the extension by opening the Extension Management page.  
For more information about Designer, go to [Designer](devenv-inclient-designer.md). 

## Customer table extension object

The **Customer** table, like many other tables, is part of the Dynamics 365 for Finance and Operations, Business edition service and it cannot be modified directly by developers. To add additional fields or to change properties on this table developers must create a new type of object, a table extension.
The following code creates a table extension for the Customer table and adds the `Reward ID` field. 

> [!TIP]
> Use the snippet `ttableext` to create a basic structure for the table extension object. 

```
tableextension 50103 "Customer Ext" extends Customer
{
    fields
    {
        field(50100;"Reward ID";Code[30])
        {
            // It sets links to the "Reward ID" from the Reward table.
            TableRelation = Reward."Reward ID";

            // It sets whether to validate a table relationship.
            ValidateTableRelation = true;
           
           // OnValidate executes when data is entered in a field.
            trigger OnValidate();
            begin        
            // NEED HELP from a developer!!
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


## Customer card page extension object

A page extension object can be used to add new functionality to pages that are part of the Dynamics 365 for Finance and Operations, Business edition service. The following page extension object extends the **Customer Card** page object by adding a field control, **Reward ID**, to the General group on the page. The field is added in the **layout** section, while in the **actions** section the code adds an action to open the **Reward List** page. 

> [!TIP]
> Use the shortcuts `tpageext` to create the basic structure for the page extension object.

```
pageextension 50104 "Customer Card Ext" extends "Customer Card"
{
    layout
    {   
        // The addlast construct adds the field control as the last // control in the General group.
        addlast(General)
        {
            field("Reward ID";"Reward ID")
            {
                ApplicationArea = All;
                
                // Lookup property is used to provide a lookup window for 
                // a text box. It is set to true, because a lookup for 
                // the field is needed.
                Lookup = true;
            }
        }
    }

    actions
    {
        // The addfirst construct will add the action as the first action
        // in the Navigation group
        addfirst(Navigation)
        {
            action("Rewards")
            {
                ApplicationArea = All;

                // RunObject sets the "Reward List" page as the object 
                // that will run when the action is activated.
                RunObject = page "Reward List";
            }
        }
    }
}
```

At this point, reward levels can be created and assigned to customers. To do that, update the startupObjectId value in launch.json to 21 and select the Ctrl+F5 key to open the page.

## Install code

After installing the extension, you can open the "Reward List" page and you will see that it is empty. This is due to the fact that the "Reward" table is empty. Data can be entered manually into the "Reward" table by creating new records from the "Reward List" page, but this is a tedious and time consuming task. Ideally, we would want the Reward table to be initialized with a standard number of reward levels when the extension is installed.
This goal can be achieved by using install codeunits. A codeunit is an object that can be used to encapsulate a set of related functionality represented by procedures and variables. An install codeunit is a codeunit with the Subtype property set to Install. This codeunit provides a set of triggers that are executed when the extension is installed for the first time and when the same version is re-installed. For more information about install code, see [Writing Extension Install Code](devenv-extension-install-code.md).
In this example, the following install codeunit initializes the Reward table with 3 records representing the 'GOLD', 'SILVER', and 'BRONZE' reward levels. 

> [!TIP]
> Use the shortcuts `tcodeunit` and `ttrigger` to create the basic structure for the codeunit and trigger.

```
codeunit 50105 RewardsInstallCode
{
    // Sets the codeunit to be an install codeunit. 
    Subtype = Install;
    
    // This trigger includes code for company-related operations. 
    trigger OnInstallAppPerCompany();
    var
        Reward : Record Reward;
    begin
        // If the Reward table is empty, insert the default rewards
        if Reward.IsEmpty() then begin
            InsertDefaultRewards();
        end;
    end;

    // Insert the GOLD, SILVER, BRONZE reward levels
    procedure InsertDefaultRewards();
    begin
        InsertRewardLevel('GOLD', 'Gold Level', 20);
        InsertRewardLevel('SILVER', 'Silver Level', 10);
        InsertRewardLevel('BRONZE', 'Bronze Level', 5);
    end;

    // Create and insert a reward level in the Reward table.
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

## Upgrade code
When you upgrade an extension to a newer version, if any modifications to the existing data are required to support the upgrade, you must write upgrade code in an upgrade codeunit. In this example, the following upgrade codeunit contains code that changes the **Bronze** reward level to customer records to **Aluminum**. The upgrade codeunit will run when you run the Upgrade-NAVApp cmdlet. For more information about writing and running upgrade code, see [Upgrading Extension](devenv-upgrading-extensions.md).

> [!IMPORTANT]
> Remember to increase the `version` number of the extension in the app.json file.

```
codeunit 50106 RewardsUpgradeCode
{
    // An upgrade codeunit includes AL methods for synchronizing changes to a table definition in an application with the business data table in SQL Server and migrating existing data.
    Subtype = Upgrade;

    // It is used to perform the actual upgrade.
    trigger OnUpgradePerCompany();
    var
        InstallCode : Codeunit InstallCode;
        Reward : Record Reward;

        // ModuleInfo is the current executing module. 
        Module : ModuleInfo;
    begin
        // Get information about the current module.
        NavApp.GetCurrentModuleInfo(Module);

        // If we need to upgrade, we change BRONZE reward level into the ALUMINUM reward level
        if Module.DataVersion.Major = 1 then begin
            Reward.Get('BRONZE');
            Reward.Rename('ALUMINUM');
            Reward.Description := 'Aluminum Level';
            Reward.Modify();
        end;
    end;
}
```

The Upgrade section provided the last code for your extension. So far, different objects were created to support what the user can do and how the user can edit the customer information. Publishing the sample extension on your tenants will allow you to visualize the way data is organized and what should be changed to improve it. 
<!-- Do a follow-up section. What have we achieved with the extension? What is the user now able to do? Is there something that he could do next? Any interesting readings? -->

## See Also  
[Developing Extensions](devenv-dev-overview.md)  
[Getting Started](devenv-get-started.md)  
[How to: Publish and Install an Extension](devenv-how-publish-and-install-an-extension-v2.md)  
[Converting Extensions V1 to Extensions V2](devenv-upgrade-v1-to-v2-overview.md) 

