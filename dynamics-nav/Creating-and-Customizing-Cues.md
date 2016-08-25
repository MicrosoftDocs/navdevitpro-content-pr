---
title: "Creating and Customizing Cues"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms-prod: "dynamics-nav-2017"
ms.assetid: 3b95ce45-d4c5-45e4-8463-8fc2cbe668f8
caps.latest.revision: 11
manager: edupont
---
# Creating and Customizing Cues
This topic provides an overview of Cues and the tasks involved in creating and customizing a Cue for displaying on a page the [!INCLUDE[navnow](includes/navnow_md.md)] clients.  
  
 This topic contains the following sections:  
  
-   [Cue Design Overview](Creating-and-Customizing-Cues.md#CueDesign)  
  
-   [Creating a Table for Cue Data](Creating-and-Customizing-Cues.md#CreateTable)  
  
-   [Creating a Page for the Cues](Creating-and-Customizing-Cues.md#CreatePage)  
  
-   [Specifying an Image on the Cue](Creating-and-Customizing-Cues.md#SpecifyImage)  
  
-   [Setting up a Drill Down Page on the Cue](Creating-and-Customizing-Cues.md#DrillDown)  
  
-   [Formatting the Data in the Cue](Creating-and-Customizing-Cues.md#FormatData)  
  
-   [Adding an Action to the Cue](Creating-and-Customizing-Cues.md#AddAction)  
  
-   [Setting up Colored Indicators on Cues](Creating-and-Customizing-Cues.md#SetupIndicator)  
  
> [!NOTE]  
>  For step\-by\-step instructions on many of the tasks discussed in this topic, see [Walkthrough: Creating a Cue Based on a FlowField](Walkthrough:%20Creating%20a%20Cue%20Based%20on%20a%20FlowField.md) and [Walkthrough: Creating a Cue Based on a Normal Field and a Query](Walkthrough:%20Creating%20a%20Cue%20Based%20on%20a%20Normal%20Field%20and%20a%20Query.md).  
  
##  <a name="CueDesign"></a> Cue Design Overview  
 The implementation of a Cue involves the following elements:  
  
-   A table object with a field that holds the data that is contained in the Cue at runtime.  
  
-   A page object that contains the table field and displays the Cue in the [!INCLUDE[navnow](includes/navnow_md.md)] client.  
  
-   Logic that calculates the data to display in the Cue at runtime.  
  
     The logic can consist of a combination of C\/AL and [!INCLUDE[navnow](includes/navnow_md.md)] objects, such as tables, queries, and codeunits. How and where you implement the logic will depend on whether the Cue is based on a FlowField or Normal field and what you want to achieve.  
  
### Supported Data Types  
 You can only base Cues on integer and decimal data types. Other data types are not supported and will not display in a Cue.  
  
### FlowFields versus Normal Fields  
 A Cue can be based on a FlowField or Normal field. If you base the Cue on a FlowField, then you add the logic that calculates the data for the Cue to the [CalcFormula Property](CalcFormula-Property.md) of the FlowField. If you use a Normal field, then you will typically add the logic that calculates the Cue data to a C\/AL trigger or function. Unlike a FlowField, where data is extracted from tables, a Normal field enables you to extract data from other objects such as queries.  
  
##  <a name="CreateTable"></a> Creating a Table for Cue Data  
 The first thing that you must do is to create a table that contains fields that will hold the calculated data to display in the Cues at runtime.  
  
> [!NOTE]  
>  If you already have a table for your Cues, then you can just add a new field to the existing table.  
  
### Adding a Field for the Cue Data  
 For each Cue that you want to display on the page, you must add a **Field** control in the table. When you add the **Field** control, specify the following properties.  
  
1.  Set the [Data Type Property](Data-Type-Property.md) to **Decimal**, **Integer**, or **Text**, depending on the type of data the Cue will display.  
  
2.  Set the [FieldClass Property](FieldClass-Property.md) to **FlowField** or **Normal**.  
  
     If field is a FlowField, then set the [CalcFormula Property](CalcFormula-Property.md) to calculate the Cue data. For more information, see and [How to: Create, View, and Edit a Calculation Formula](How%20to:%20Create,%20View,%20and%20Edit%20a%20Calculation%20Formula.md).  
  
### Adding a Primary Key Field for FlowFields  
 A table must have at least one data field. Because a **FlowField** is based on a calculation, it not considered an actual data field. Therefore, if the Cue table only includes FlowFields, you must add "dummy" primary key field that does not yield any data.  
  
 To add primary key, for example, add a field with the name **Primary Key**, and then set its data type to **Code**.  
  
##  <a name="CreatePage"></a> Creating a Page for the Cues  
 After you have a table for holding the Cue data, you create a page that you associate the table, and then add fields on the page for the Cues. Typically, you will create Card Part type page that will be part of the Role Center page.  
  
### Adding the Cue Fields  
 To setup the Cues on a page, you add a **CueGroup** control, and then for each Cue that you want to display, you add a **Field** control. The following figure illustrates the Page Designer for a page that contains two Cues.  
  
 ![Page Designer showing cues](media/NAV_PageDesigner_SalesThisMonthCue_Clip.png "NAV\_PageDesigner\_SalesThisMonthCue\_Clip")  
  
### Initializing the Cue Fields  
 You must initialize the Cue fields on the page. To do this, for example, you can add the following C\/AL code to the [OnOpenPage Trigger](OnOpenPage-Trigger.md).  
  
```  
RESET;  
IF NOT GET THEN BEGIN  
  INIT;  
  INSERT;  
END;  
```  
  
## Customizing a Cue  
 This section contains information about how you can change the appearance of the Cues.  
  
###  <a name="SpecifyImage"></a> Specifying an Image on the Cue  
 You can specify an image to display on the Cue or you can choose not to display an image at all.  You can select from several available images.  
  
 For more information, see [How to: Set Up an Image on a Cue](How%20to:%20Set%20Up%20an%20Image%20on%20a%20Cue.md).  
  
###  <a name="DrillDown"></a> Setting up a Drill Down Page on the Cue  
 You can set up a Cue to link to a page that displays details about the transactions that make up the data in the Cue. This page is referred to as a *drill down page*. For example, if the Cue displays the number of open sales orders, then you can set up the Cue to link to list page that includes the sales orders. The page opens when a user selects the Cue.  
  
 To set up a drill down page, you can do one of the following:  
  
-   Set the [DrillDown Property](DrillDown-Property.md) of the Cue field on the page to the ID of the page that you want to open from the Cue.  
  
-   You can add code to the [OnDrillDown Trigger](OnDrillDown-Trigger.md) of the Cue field on the page that contains the Cue.  
  
     The OnDrillDown trigger takes precedent over the DrillDown property.  
  
> [!NOTE]  
>  When the Cue is on a Role Center page type, an item that links to the drill down page will automatically appear in the navigation pane of the Role Center under **Home** if the navigation pane contains an entity of the same type. For example, if you have a Cue named **Sales Return Orders – Open**, this item will be added to the **Sales Return Orders** in the navigation pane.  
  
###  <a name="FormatData"></a> Formatting the Data in the Cue  
 If the data type on the Cue is a decimal, then you can change how the data is displayed, including converting amounts and unit amounts to another currency, specifying the number of decimal places and thousand separator, and adding characters before or after the value.  
  
 For more information, see the [Formatting the Data in a Field](Formatting-the-Data-in-a-Field.md).  
  
###  <a name="AddAction"></a> Adding an Action to the Cue  
 When the Cue is displayed in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] client, you can add an action next to the Cue that opens a related task. For example, if the Cue displays the open sales orders, then you can add an action the opens the Sale Order card page for creating a new sales order.  
  
 To set up an action, open the page that contains the Cue in the [!INCLUDE[nav_dev_short](includes/nav_dev_short_md.md)], and then add a **Control** action on the **CueGroup** control that contains the Cue field. Set the [RunObject Property](RunObject-Property.md) of the action to the object, such as a page, that you want to target.  
  
> [!NOTE]  
>  This is not supported in the [!INCLUDE[nav_web](includes/nav_web_md.md)] or [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)].  
  
###  <a name="SetupIndicator"></a> Setting up Colored Indicators on Cues  
 You can set up Cues to include a colored bar along the top border, which changes color based on the data in the Cue.  
  
 For more information, see [Setting Up Colored Indicators on Cues](Setting-Up-Colored-Indicators-on-Cues.md).  
  
## See Also  
 [Setting Up Cues](Setting-Up-Cues.md)   
 [FlowFields](FlowFields.md)