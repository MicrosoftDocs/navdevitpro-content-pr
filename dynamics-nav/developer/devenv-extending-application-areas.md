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
ms.prod: "dynamics-nav-2018"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: solsen
caps.latest.revision: 18
redirect_url: /dynamics365/business-central/dev-itpro/developer/devenv-extending-application-areas
---

 

# Extending Application Areas 
Application area represents a feature in the system that offers developers, administrators, and users the ability to define differentiated user experiences.
Application areas are mapped to controls to show or hide them on page objects to enable more or less business scenarios.   

## Extending application areas and the experience tier 
In this example you will: 
- Add a new application area in the **Application Area Setup** Table. 
- Enable the application Area in the **OnInstallAppPerCompany**.
- Extend the experience tier in the **OnGetExperienceAppArea**.
- Modify the experience tier (optional).
- Validate the application area in the **OnValidateApplicationAreas**.

> [!IMPORTANT]
> The code used in this example is still under active development and might be subject to change in the future. 


The following example extends the **Customer List** page. The field **ExampleField** is added and it is followed by a series of properties. The **ApplicationArea** property sets the application areas that apply to the control and in this code, **ExampleAppArea** is assigned to it. 

> [!IMPORTANT]  
> If your extension fails to use **ApplicationArea** in any controls or actions, they will not be visible when you use an experience tier. 

The **OnOpenPage** trigger will display the message only if **ApplicationArea** is enabled.  

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

## Adding an application area 
To add an application area, the **Application Area Setup** table must be extended. A new boolean field is added and the name of this field will be used in the attribute that you want to be tagged with this application area. This particular case, in the code below, is an exception, because space is used inside it. Usually, spaces are omitted in the application area attribute. At this point, the extension has an application area but it still needs to be enabled. 


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

The codeunit **Install Example Extension** is of the subtype Install and it enables the application area inside the **OnInstallAppPerCompany** trigger. 

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

The registration of the application area inside an experience tier is made inside the **OnGetEssentialExperienceAppArea**. There are different versions of this event, one for each experience tier and in this case, the Essential is chosen. This will make the extension visible inside the Essential experience and the event exposes an **Application Area Setup** temporary record, **TempApplicationAreaSetup**, to the **Application Area Setup** table. At this point, to enable the application area, this must be set to true.




> [!NOTE]  
> This event is important because it is called every single time an experience tier is reset, which can happen because of many reasons. 

Another thing that is possible inside these methods is to modify the experience tier. You can also modify other application areas, such as creating an extension that extends the Fixed Assets. 
By subscribing to **OnValidateApplicationAreas** the application area inside an experience tier is validated. **OnValidateApplicationAreas** is guaranteed to be executed after the events in the OnGet*ExperienceAppArea family. The validation is necessary in the presence of extensions concurrently manipulating the same application areas.

In case a needed application area is not enabled, the suggested action is to show an error and disable the extension to avoid unintended behavior. However, if the functionality controlled by this application area is of secondary importance and its loss does not affect the rest of the extension, it is also appropriate to keep the extension enabled.


```
codeunit 50100 "Enable Example Extension"
{
    // Extend and Modify Essential Experience Tier with "Example App Area"
    [EventSubscriber(ObjectType::Codeunit, Codeunit::"Application Area Mgmt.", 'OnGetEssentialExperienceAppAreas', '', false, false)]
    local procedure RegisterExampleExtensionOnGetEssentialExperienceAppAreas(var TempApplicationAreaSetup: Record "Application Area Setup" temporary)
    begin
        TempApplicationAreaSetup."Example App Area" := true;
        // Modify other application areas here...
    end;

    // Validate that application areas needed for the extension are enabled
    [EventSubscriber(ObjectType::Codeunit, Codeunit::"Application Area Mgmt.", 'OnValidateApplicationAreas', '', false, false)]
    local procedure VerifyApplicationAreasOnValidateApplicationAreas(ExperienceTierSetup: Record "Experience Tier Setup"; TempApplicationAreaSetup: Record "Application Area Setup" temporary)
    begin
        if ExperienceTierSetup.Essential then
            if not TempApplicationAreaSetup."Example App Area" then
                Error('Example App Area should be part of Essential in order for the Example Extension to work.');
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
        if ExperienceTierSetup.Get(CompanyName()) then; 
        if not ExperienceTierSetup.Essential then
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
If you decide to code application areas as an extension, there are some aspects that must be considered. Application areas enable hiding entire business scenarios and you can have the same code base, which makes it possible to quickly modify the UI for different business scenarios or audiences. However, tagging errors as missing tags or incorrect tags will occur and every single control will need to be tagged. 

## See Also
[ApplicationArea Property](properties/devenv-applicationarea-property.md)  
[APPLICATIONAREA Method](methods/devenv-applicationarea-method.md)  
[AccessByPermission Property](properties/devenv-accessbypermission-property.md)     
[Properties](properties/devenv-properties.md)
 
