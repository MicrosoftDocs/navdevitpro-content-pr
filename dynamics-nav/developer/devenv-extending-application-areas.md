---
title: "Extending Application Areas"
description: "Document the extension of Application Areas."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 12/11/2017
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
# Extending Application Areas 

Application area represents a feature in the system that offers developers, administrators, and users the ability to define differentiated user experiences. The user experience determines how much of the core functionality is available when you use [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. Application areas are used to map the controls and actions to the various experience that will change existing page objects to match more scenarios that are part of this process.   


## Extending application areas and experience tier 
 In this example you will: 
- Add a new application area in the `Application Area Setup` Table. 
- Enable the application Area in the `OnInstallAppPerCompany`.
- Extend the experience tier in the `OnGetExperienceAppArea`.
- Modify the experience tier (optional).
- Validate the application area in the `OnValidateApplicationAreas`.

<!-- OR  
In this example you will: 
- Add and enable a new application area.
- Extend the experience tier.
- Validate the application area. -->



The following example extends the `Customer List` page. The field `ExampleField` is added and it is followed by a series of properties. The `ApplicationArea` property sets the application areas that apply to the control and in this code, `ExampleAppArea` is assigned to it. 

>[!IMPORTANT]  
>If your extension fails to use `ApplicationArea` in any controls or actions, they will not be visible when you use an experience tier. 

The `OnOpenPage` trigger will display the message only if `ApplicationArea` is enabled.  

```
pageextension 50100 CustomerListExt extends "Customer List"
{
    layout
    {
        addafter(Name)
        {
            field(ExampleField; "Name 2")
            {
                Caption = 'Example Field';
                ApplicationArea = ExampleAppArea;
                ToolTip = 'This is a field added by an example extension';
                Importance = Promoted;
            }
        }
    }

    trigger OnOpenPage()
    var
        EnableExampleExtension : Codeunit "Enable Example Extension";
    begin
        if EnableExampleExtension.IsExampleApplicationAreaEnabled() then
            Message('App published: Example Extension');
    end;
}
```

## How to add an application area 
To add an application area, the `Application Area Setup` table needs to be extended. A new boolean field is added and the name of this field will be used in the attribute that you want to be tagged with this application area. This particular case, in the code below, is an exception, because space is used inside it. Normally, spaces are omitted in the application area attribute.   
At this point, the extension has an application area and it needs the codeunit to enable it. 


```
tableextension 50100 "Application Area Setup" extends "Application Area Setup"
{
    fields
    {
        // Spaces in field name are omitted in the ApplicationArea attribute
        // e.g. ApplicationArea = ExampleAppArea;
        field(50100;"Example App Area";Boolean)
        {
        }
    }
}
```

The codeunit `Install Example Extension` is of subtype `Install` and it enables the application area inside the `OnInstallAppPerCompany` trigger. To make the extension work, the application area has to be registered inside an experience tier. 

```
codeunit 50101 "Install Example Extension"
{
    Subtype = Install;

    trigger OnInstallAppPerCompany()
    var
        EnableApplicationArea : Codeunit "Enable Example Extension";
    begin
        if(EnableApplicationArea.IsExampleApplicationAreaEnabled()) then
            exit;

        EnableApplicationArea.EnableExampleExtension();

        // Add your code here
    end;
}
```

The registration of the application area inside an experience tier is made inside the `OnGetSuiteExperienceAppArea`. There are different versions of this event, one for each experience tier and in this case, the Suite is chosen. This will make the extension visible inside the Suite experience and the event shows a `TempApplicationAreaSetup` Record to the `Application Area Setup` table. At this point, to enable the application area, this has to be set to true.

>[!NOTE]  
>This event is important because it is called every single time when an experience tier is reset, which can happen because of many reasons. 

Another thing that is possible inside these methods is to modify the experience tier. You can also modify other application areas, such as creating an extension that extends the `Fixed Assets`. 
By subscribing to `OnValidateApplicationAreas` the application area inside an experience tier is validated. This is needed as there is no guarantee of the order of events execution.  
To avoid this, you check the presence of Suite and if the application area is not enabled, an error will be displayed. 

```
codeunit 50100 "Enable Example Extension"
{
    // Extend and Modify Suite Experience Tier with "Example App Area"
    [EventSubscriber(ObjectType::Codeunit, Codeunit::"Application Area Mgmt.", 'OnGetSuiteExperienceAppAreas', '', false, false)]
    local procedure RegisterExampleExtensionOnGetSuiteExperienceAppAreas(var TempApplicationAreaSetup: Record "Application Area Setup" temporary)
    begin
        TempApplicationAreaSetup."Example App Area" := true;
        // Modify other application areas here...
    end;

    // Validate that application areas needed for the extension are enabled
    [EventSubscriber(ObjectType::Codeunit, Codeunit::"Application Area Mgmt.", 'OnValidateApplicationAreas', '', false, false)]
    local procedure VerifyApplicationAreasOnValidateApplicationAreas(ExperienceTierSetup: Record "Experience Tier Setup"; TempApplicationAreaSetup: Record "Application Area Setup" temporary)
    begin
        if ExperienceTierSetup.Suite then
            if not TempApplicationAreaSetup."Example App Area" then
                Error('Example App Area should be part of Suite in order for the Example Extension to work.');
    end;

    // Helpers ................................................................
    procedure IsExampleApplicationAreaEnabled() : Boolean
    var
        ApplicationAreaSetup: Record "Application Area Setup";
        ApplicationAreaMgmtFacade: Codeunit "Application Area Mgmt. Facade";
    begin
        if ApplicationAreaMgmtFacade.GetApplicationAreaSetupRecFromCompany(ApplicationAreaSetup, CompanyName()) then
            exit(ApplicationAreaSetup."Example App Area");
    end;

    procedure EnableExampleExtension()
    var
        ApplicationAreaSetup: Record "Application Area Setup";
        ExperienceTierSetup: Record "Experience Tier Setup";
        ApplicationAreaMgmtFacade: Codeunit "Application Area Mgmt. Facade";
    begin
        if ExperienceTierSetup.Get(CompanyName()) then; //CRONUS International Ltd. //TODO remove
        if not ExperienceTierSetup.Suite then
            exit;

        if ApplicationAreaMgmtFacade.GetApplicationAreaSetupRecFromCompany(ApplicationAreaSetup, CompanyName()) then begin
            ApplicationAreaSetup."Example App Area" := true;
            ApplicationAreaSetup.Modify();

            // Without this line the app area is enabled only at the next login
            ApplicationAreaMgmtFacade.SetupApplicationArea();
        end;
    end;
}
```

## Application areas advantages and disadvantages

If you decide to code application areas as an extension, there are some aspects that need to be considered. Application areas enable hiding entire business scenarios and you can have the same code base, which makes possible to quickly modify the UI for different business scenarios or audiences. However, tagging erros as missing tags or incorrect tags will occur and every single control must be tagged. 



## See Also
[ApplicationArea Property](properties/devenv-applicationarea-property.md)  
[APPLICATIONAREA Method](methods/devenv-applicationarea-method.md)  
[AccessByPermission Property](properties/devenv-accessbypermission-property.md)     
[Properties](properties/devenv-properties.md)
 
