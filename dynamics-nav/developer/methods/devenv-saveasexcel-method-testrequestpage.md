---
title: "SAVEASEXCEL Method (TestRequestPage)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-financials
ms.assetid: 817a0e1e-8b69-4bd8-894a-2a26f11d28aa
caps.latest.revision: 10
manager: edupont
---

[!INCLUDE[newdev_dev_preview](../includes/newdev_dev_preview.md)]

# SAVEASEXCEL Method (TestRequestPage)
Saves a report as a Microsoft Excel \(.xls\) file.  
  
## Syntax  
  
```  
  
TestRequestPage.SAVEASEXCEL(Filename)  
```  
  
#### Parameters  
 *TestRequestPage*  
 Type: TestRequestPage  
  
 The TestRequestPage from which you want to test saving the report as an Excel file.  
  
 *Filename*  
 Type: Text  
  
 The path and file name to which the report is saved. The file name extension should be .xls.  
  
## Remarks  
 All filters and options that have been set on the TestRequestPage are respected in the saved report.  
  
 After you run this method, you cannot continue to interact with the *TestRequestPage*. If you want to continue to use the *TestRequestPage* variable, you must run a report again.  
  
## Example  
 The following example shows the code for a test method to run a report and a request page handler method to test the request page. This example requires that you create the following:  
  
-   A test codeunit called SaveAsExcel. <!--Links For more information, see [How to: Create Test Codeunits and Test Methods](devenv-How-to--Create-Test-Codeunits-and-Test-Methods.md).-->  
  
-   A test method in the test codeunit called TestSaveAsExcel. <!--Links For more information, see [How to: Create Test Codeunits and Test Methods](devenv-How-to--Create-Test-Codeunits-and-Test-Methods.md). --> 
  
-   A handler method of type RequestPageHandler called ReqPageHandler. This handler method has one parameter called RequestPage of Type TestRequestPage and Subtype Customer – Top 10 List. The RequestPage parameter is specified as VAR and is passed by reference to the handler method. <!--Links For more information, see [How to: Create Handler Methods](devenv-How-to--Create-Handler-Methods.md).-->  
  
 This example also requires that you create the following global variable of the SaveAsExcel codeunit.  
  
|Variable name|DataType|  
|-------------------|--------------|  
|Filename|Text|  
  
```  
//Test method: TestSaveAsExcel  
Filename := TEMPORARYPATH + 'MyRep.xls';  
MESSAGE(Filename);  
IF NOT FILE.ERASE(Filename) THEN  
  ERROR('Cannot erase %1',Filename);  
REPORT.RUN(111);  
IF NOT FILE.EXISTS(Filename) THEN  
  ERROR('File should exist!');  
  
//Request Page Handler method  
RequestPage.Customer.SETFILTER("No.", '20000');  
RequestPage.ChartType.VALUE('Pie chart');  
RequestPage.SAVEASEXCEL(Filename);  
  
```  
  
## See Also  
 <!--Links [Testing the Application](Testing-the-Application.md) -->  
 [SAVEASPDF Method \(TestRequestPage\)](devenv-SAVEASPDF-Method-TestRequestPage.md)   
 [SAVEASWORD Method \(TestRequestPage\)](devenv-SAVEASWORD-Method-TestRequestPage.md)