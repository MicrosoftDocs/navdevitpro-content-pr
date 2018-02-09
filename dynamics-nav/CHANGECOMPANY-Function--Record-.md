---
title: "CHANGECOMPANY Function (Record)"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: e50d0b45-9556-42a0-9efa-e23c88f1b152
caps.latest.revision: 9
manager: edupont
---
# CHANGECOMPANY Function (Record)
Redirects references to table data from one company to another.  
  
## Syntax  
  
```  
  
[Ok :=] Record.CHANGECOMPANY([CompanyName])  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record that you want to access from a table in another company.  
  
 *CompanyName*  
 Type: Text or code  
  
 The name of the company to which you want to change. If you omit this parameter, you change back to the current company.  
  
## Property Value/Return Value  
 Type: Boolean  
  
 **true** if the company was found; otherwise, **false**.  
  
 If you omit this optional return value and the company cannot be found, a run-time error occurs. If you include the return value, you must handle any errors.  
  
## Remarks  
 When executing this function, the user's access rights are respected. For example, a user cannot access data in *CompanyName* unless he already has the necessary access rights.  
  
 The **CHANGECOMPANY** function is not affected by the [RESET Function \(Record\)](RESET-Function--Record-.md). You can deselect a company by making a new call to **CHANGECOMPANY** or by using the [CLEAR Function](CLEAR-Function.md).  
  
 Global filters always belong to a specific company. If you use the following code to select the company named NewCompany, any filters assigned to *Record* will be transferred to *Record* in the new company.  
  
```  
Record.CHANGECOMPANY(NewCompany);  
```  
  
 Even if you run the **CHANGECOMPANY** function, triggers still run in the current company, not in the company that you specified in the **CHANGECOMPANY** function.  
  
## Example  
 This example shows how to use the **CHANGECOMPANY** function.  
  
```  
"G/L Account".CHANGECOMPANY('New Company');  
"G/L Account".GET('1000');  
"G/L Account".CALCFIELDS(Balance); // Calculates the balance  
// for account no. 1000 in 'New Company'  
"G/L Entry".CHANGECOMPANY('New Company');  
"G/L Entry".SETCURRENTKEY("Entry No.","Posting Date");  
"G/L Entry".SETRANGE("Entry No.",1000);  
"G/L Entry".SETRANGE("Posting Date",010196D,013196D);  
"G/L Entry".CALCSUMS(Amount); // Sums Amount from  
// all G/L entries on account no. 1000 within the specified range,  
// for 'New Company'  
"G/L Entry".RESET;  
"G/L Entry".FIND('+'); // Finds the largest "No." in the G/L Entry   
// table in 'New Company'  
"G/L Entry".DELETE; // Deletes this entry in 'New Company'  
```  
  
 This example shows that after the **CHANGECOMPANY** function has been called, all future references to the G/L Account and G/L Entry tables will refer to the table data in New Company.  
  
## Example  
 This example shows that CHANGECOMPANY only changes the company on a data level. Triggers and functions will still run in the context of the current company.  
  
```  
Rec.CHANGECOMPANY('B');  
Rec.FINDFIRST;  
Rec.MODIFY(TRUE);  
```  
  
 If you run the code in this example from Company A, it will modify Rec in Company B, but it will run the OnModify trigger in Company A.  
  
## See Also  
 [Record Data Type](Record-Data-Type.md)