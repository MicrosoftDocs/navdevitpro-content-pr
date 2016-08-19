<properties
                pageTitle="ExtendedDataType Property | Dynamics NAV"
                description="Partial migration of topic for the ExtendedDataType property."
                services=""
                documentationCenter=""
                authors="edupont04"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="08/11/2016"
    ms.author="edupont04" />

# ExtendedDataType Property
Sets the extended data type of a control.  

## Applies To  

-   Page Fields  

-   Table Fields  

## Remarks  
 The value of this property overrides the value of the table field and it converts a text field into one of the following:  

-   None  
-   Phone number  
-   Email address  
-   URL  
-   Filter \(used on reports\)  
-   Ratio \(to monitor the progress bar\)
-   Masked \(displays the value as dots\)
-   Person \(displays a media field value as a round picture\) 
-   Resource \(The client will use the field content as a bitmap resource name from which it will load a brick icon\)

 This property affects the layout and behavior of controls on a page. Use it to e.g. add an icon next to an input field to indicate whether the field relates to a telephone number, email address, or URL. This property applies validation to the field.  

<!-- ## See Also  
 [Properties](Properties.md)-->
