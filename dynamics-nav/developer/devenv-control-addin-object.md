---
title: "Control Addin Object"
description: "Description of the control addin object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 09/27/2017
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

# Control Add-In Object
The control add-in object allows you to add custom functionality to [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)]. A control add-in is a custom control, or visual element, for displaying and modifying data on [!INCLUDE[d365fin_md](includes/d365fin_md.md)] pages. Control add-ins can exchange data with the [!INCLUDE[d365fin_md](includes/d365fin_md.md)] server on various data types and can respond to user interaction to raise events that execute additional AL code.


## Snippet support
Typing the shortcut ```t??``` will create the basic layout for a control add-in object when using the AL Extension in Visual Studio Code.

## Control add-in example
The following control add-in object example defines a chart that can show how customers are represented per country on a map. The control add-in is implemented as a `usercontrol` on a page called CustomersMapPage.

```
// The controladdin type declares the new add-in. 

controladdin CustomersPerCountryChart 
{ 
    // The Scripts property can reference both external and local scripts. 
    Scripts = 'https://code.jquery.com/jquery-2.1.0.min.js', 
              'js/main.js'; 
    
    // The StartupScript is a special script that the webclient calls once the page is loaded. 
    StartupScript = 'js/chart.js'; 
    
    // Images and StyleSheets can be referenced in a similar fashion. 

    // The layout properties define how control add-in are displayed on the page. 
    VerticalShrink = true; 
    
    // The procedure declarations specify what JavaScript methods could be called from AL. 
    // In JavaScript code, there should be a global function LoadData(data) {} 
    procedure LoadData(Data : JsonArray); 
    
    // The event declarations specify what callbacks could be raised from JavaScript by using webclient API: 
    // Microsoft.Dynamics.NAV.InvokeExtensibilityMethod('CountryClicked', [{country: 'M}]) 
    event CountryClicked(Country: JsonObject); 
}
page 50100 CustomersMapPage 
{ 
    layout 
    { 
        area(Content) 
        { 
            // The control add-in can be placed on the page using usercontrol keyword. 

            usercontrol(ControlName; CustomersPerCountryChart) 
            {
                // The control add-in events can be handled by defining a trigger with a corresponding name. 

                trigger CountryClicked(Country : JsonObject) 
                var Data : JsonArray; 
                begin 
                    
                    // The control add-in methods can be invoked via a reference to the usercontrol. 
                    
                    CurrPage.ControlName.LoadData(Data); 
                end;                  
            } 
        }
    }
} 



```

## See Also  
[Developer Reference](devenv-reference-overview.md)  
[Developing Extensions](devenv-dev-overview.md)  
[Pages Overview](devenv-pages-overview.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Page Customization Object](devenv-page-customization-object.md)
