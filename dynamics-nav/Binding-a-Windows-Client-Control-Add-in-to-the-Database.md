---
title: "Binding a Windows Client Control Add-in to the Database"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 6a587bf8-4eeb-40e9-809a-95643842e90f
caps.latest.revision: 24
manager: edupont
---
# Binding a Windows Client Control Add-in to the Database
Similar to other field controls on a page, a [!INCLUDE[nav_windows](includes/nav_windows_md.md)] control add-in can bind with data in the [!INCLUDE[navnow](includes/navnow_md.md)] database. This lets you create control add-ins that can display and update data in the database. Data binding is accomplished through [!INCLUDE[nav_server](includes/nav_server_md.md)] with the [SourceExpr Property](SourceExpr-Property.md) of the field control that is applied with the control add-in, as shown in the following illustration.  

 ![RoleTailored client control add&#45;in data binding](media/NAVRTCContolAddinDataBinding.png "NAVRTCContolAddinDataBinding")  

 The control add-in must implement the [Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition) interface that exposes the [IValueControlAddInDefinition.Value](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition.Value) property as shown in the following example for a DateTime data type.  

```c#  
[ControlAddInExport("MyControlAddIn")]  
public class MyControlAddIn : IValueControlAddInDefinition<DateTime>  
{  
    ...  
}  

```  

 When a control add-in is instantiated on a page, the **SourceExpr** property value is passed to the control add-in [IValueControlAddInDefinition.Value](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition.Value) property. The **SourceExpr** property can be a field or row in a database table or a C/AL global variable.  

> [!NOTE]  
>  The **SourceExpr** property value can be passed to the [IValueControlAddInDefinition.Value](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition.Value) property multiple times as long as a page is open, depending on application code or state in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)].  

 For more information about how to implement the [Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition) interface, see [How to: Create a Windows Client Control Add-in](How-to--Create-a-Windows-Client-Control-Add-in.md).  

 For more information about how to set the **SourceExpr** property for a control add-in, see [How to: Set Up a Windows Client Control Add-in on a Page](How-to--Set-Up-a-Windows-Client-Control-Add-in-on-a-Page.md).  

## Supported Data Types  
 A control add-in can bind with several data types from the database. Each data type in C/AL maps to a corresponding .NET Framework data type in the control add-in as listed in the following table.  

|C/AL data type|Control add-in data type|  
|---------------------|-------------------------------|  
|BigInteger|[Int64](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Int64)|  
|BigText|[String](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.String)|  
|BLOB|[Object](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Object)|  
|Boolean|[Boolean](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Boolean)|  
|Byte|[Byte](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Byte)|  
|Char|[Char](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Char)|  
|Code|[System.String](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.String)|  
|Date|[DateTime](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.DateTime)|  
|DateFormula|[String](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.String)|  
|DateTime|[DateTime](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.DateTime)|  
|Decimal|[Decimal](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Decimal)|  
|Duration|[TimeSpan](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.TimeSpan)|  
|Guid|[Guid](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Guid)|  
|Integer|[Int32](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Int32)|  
|Option|[Int32](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.Int32)|  
|RecordID|[String](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.String)|  
|Text|[String](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.String)|  
|Time|[DateTime](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=System.DateTime)|  

## Data Mapping and Multiple Data Types  
 The mapping between the C/AL data type of the page control and the .NET Framework data type occurs when the control add-in is instantiated on a page in the [!INCLUDE[nav_windows](includes/nav_windows_md.md)]. For example, if a page contains a control that uses a Date data type in C/AL and the control add-in implements the Boolean data type \(`IValueControlAddInDefinition<Boolean>`\), then an error occurs.  

 A control add-in can support multiple .NET Framework data types by implementing the [Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition](https://docs.microsoft.com/search/index?dataSource=previousVersions&search=Microsoft.Dynamics.Framework.UI.Extensibility.IValueControlAddInDefinition) interface for each data type. For example, to support both a string and an integer data type, include the following code.  

```c#  
public class MyControlAddIn : IValueControlAddInDefinition<String>, IValueControlAddInDefinition<Int32>  

```  

## See Also  
 [Developing Windows Client Control Add-ins](Developing-Windows-Client-Control-Add-ins.md)   
 [Client Extensibility API Overview](Client-Extensibility-API-Overview.md)   
 [How to: Create a Windows Client Control Add-in](How-to--Create-a-Windows-Client-Control-Add-in.md)   
 [Exposing Events and Calling Respective C/AL Triggers from a Windows Client Control Add-in](Exposing-Events-and-Calling-Respective-C-AL-Triggers-from-a-Windows-Client-Control-Add-in.md)   
 [Installing and Configuring Windows Client Control Add-ins on Pages](Installing-and-Configuring-Windows-Client-Control-Add-ins-on-Pages.md)   
 [Windows Client Control Add-in Overview](Windows-Client-Control-Add-in-Overview.md)
