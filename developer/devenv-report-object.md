---
title: "Report Object"
description: "Description of the report object."
author: SusanneWindfeldPedersen
ms.custom: na
ms.date: 03/06/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: a0ac492d-e3c8-4a76-87b4-b469e08c58e7
ms.author: SusanneWindfeldPedersen
caps.latest.revision: 18
---

[!INCLUDE[newdev_dev_preview](includes/newdev_dev_preview.md)]

# Report Object
Reports are used to print or display information from a database. You can use a report to structure and summarize information, and to print documents, such as sales quotes and invoices.

Creating a report for [!INCLUDE[d365fin_long_md](includes/d365fin_long_md.md)] consists of two primary tasks; the first task is to create the underlying data model and the next is to define the visual layout that displays the data. The report object defines the underlying data model and specifies which database tables and fields to pull data from. When the report is run, that data is displayed in a specified layout; the visual layout, which determines the content and format of a report when it is viewed and printed.

You build the layout of a report by arranging data items and columns, and specifying the general format, such as text font and size. There are two types of report layouts; client report definition, also called RDCL layouts and Word layouts. RDLC layouts are defined in Visual Studio Report Designer or Microsoft SQL Server Reporting Services Report Builder. Word layouts are created using Word. Word layouts are based on a Word document that includes a custom XML part representing the report dataset.

## Snippet support
Typing the shortcut ```treport``` will create the basic layout for a report object when using the AL Extension in Visual Studio Code.

## Report example
The following example is a report that prints the list of customers. The report object defines a dataset of columns from the Customer table. For more information on creating a report, see [How to: Create a Report](devenv-howto-report-layout.md).

```
report 70010101 "Customer List"
{
  CaptionML=ENU='Customer List';
  RDLCLayout = 'Customer List Report.rdlc'; // if Word use WordLayout property
  dataset
  {
    dataitem(Customer;Customer)
    {
      RequestFilterFields="No.","Search Name","Customer Posting Group";
      column(COMPANYNAME;COMPANYNAME)
      {
      }
      column(CurrReport_PAGENO;Customer."no.")
      {
      }
      column(Customer_TABLECAPTION_CustFilter;TABLECAPTION + ': ' + CustFilter)
      {
      }
      column(CustFilter;CustFilter)
      {
      }
      column(Customer_No;"No.")
      {
      }
      column(Customer_Customer_Posting_Group;"Customer Posting Group")
      {
      }
      column(Customer_Customer_Disc_Group;"Customer Disc. Group")
      {
      }
      column(Customer_Invoice_Disc_Code;"Invoice Disc. Code")
      {
      }
      column(Customer_Customer_Price_Group;"Customer Price Group")
      {
      }
      column(Customer_Fin_Charge_Terms_Code;"Fin. Charge Terms Code")
      {
      }
      column(Customer_Payment_Terms_Code;"Payment Terms Code")
      {
      }
      column(Customer_Salesperson_Code;"Salesperson Code")
      {
      }
      column(Customer_Currency_Code;"Currency Code")
      {
      }
      column(Customer_Credit_Limit_LCY;"Credit Limit (LCY)")
      {
        DecimalPlaces=0:0;
      }
      column(Customer_Balance_LCY;"Balance (LCY)")
      {
      }
      column(CustAddr_1;CustAddr[1])
      {
      }
      column(CustAddr_2;CustAddr[2])
      {
      }
      column(CustAddr_3;CustAddr[3])
      {
      }
      column(CustAddr_4;CustAddr[4])
      {
      }
      column(CustAddr_5;CustAddr[5])
      {
      }
      column(Customer_Contact;Contact)
      {
      }
      column(Customer_Phone_No;"Phone No.")
      {
      }
      column(CustAddr_6;CustAddr[6])
      {
      }
      column(CustAddr_7;CustAddr[7])
      {
      }
      column(Customer_ListCaption;Customer_ListCaptionLbl)
      {
      }
      column(CurrReport_PAGENOCaption;CurrReport_PAGENOCaptionLbl)
      {
      }
      column(Customer_NoCaption;FIELDCAPTION("No."))
      {
      }
      column(Customer_Customer_Posting_GroupCaption;Customer_Customer_Posting_GroupCaptionLbl)
      {
      }
      column(Customer_Customer_Disc_GroupCaption;Customer_Customer_Disc_GroupCaptionLbl)
      {
      }
      column(Customer_Invoice_Disc_CodeCaption;Customer_Invoice_Disc_CodeCaptionLbl)
      {
      }
      column(Customer_Customer_Price_GroupCaption;Customer_Customer_Price_GroupCaptionLbl)
      {
      }
      column(Customer_Fin_Charge_Terms_CodeCaption;FIELDCAPTION("Fin. Charge Terms Code"))
      {
      }
      column(Customer_Payment_Terms_CodeCaption;Customer_Payment_Terms_CodeCaptionLbl)
      {
      }
      column(Customer_Salesperson_CodeCaption;FIELDCAPTION("Salesperson Code"))
      {
      }
      column(Customer_Currency_CodeCaption;Customer_Currency_CodeCaptionLbl)
      {
      }
      column(Customer_Credit_Limit_LCYCaption;FIELDCAPTION("Credit Limit (LCY)"))
      {
      }
      column(Customer_Balance_LCYCaption;FIELDCAPTION("Balance (LCY)"))
      {
      }
      column(Customer_ContactCaption;FIELDCAPTION(Contact))
      {
      }
      column(Customer_Phone_NoCaption;FIELDCAPTION("Phone No."))
      {
      }
      column(Total_LCY_Caption;Total_LCY_CaptionLbl)
      {
      }

      trigger OnAfterGetRecord();
      begin
        CALCFIELDS("Balance (LCY)");
        FormatAddr.FormatAddr(
          CustAddr,Name,"Name 2",'',Address,"Address 2",
          City,"Post Code",County,"Country/Region Code");
      end;

      trigger OnPreDataItem();
      begin
        CurrReport.CREATETOTALS("Balance (LCY)");
      end;
    }
  }

  requestpage
  {
    SaveValues=true;

    layout
    {
    }

    actions
    {
    }
  }

  labels
  {
  }

  trigger OnPreReport();
  var
    CaptionManagement : Codeunit 42;
  begin
    CustFilter := CaptionManagement.GetRecordFiltersWithCaptions(Customer);
  end;

  var
    FormatAddr : Codeunit 365;
     CustFilter : Text;
    CustAddr : ARRAY [8] OF Text[50];
    Customer_ListCaptionLbl : TextConst ENU='Customer - List';
    CurrReport_PAGENOCaptionLbl : TextConst ENU='Page';
    Customer_Customer_Posting_GroupCaptionLbl : TextConst ENU='Customer Posting Group';
    Customer_Customer_Disc_GroupCaptionLbl : TextConst ENU='Cust./Item Disc. Gr.';
    Customer_Invoice_Disc_CodeCaptionLbl : TextConst ENU='Invoice Disc. Code';
    Customer_Customer_Price_GroupCaptionLbl : TextConst ENU='Price Group Code';
    Customer_Payment_Terms_CodeCaptionLbl : TextConst ENU='Payment Terms Code';
    Customer_Currency_CodeCaptionLbl : TextConst ENU='Currency Code';
    Total_LCY_CaptionLbl : TextConst ENU='Total (LCY)';
}


```

## See Also
[Developing Extensions Using the New Development Environment](devenv-dev-overview.md)  
[Developer Reference](devenv-reference-overview.md)  
[How to: Create a Report](devenv-howto-report-layout.md)  
[Page Extension Object](devenv-page-ext-object.md)  
[Pages](pages.md)  
[Tables](tables.md)  
[Page Properties](page-properties.md)
