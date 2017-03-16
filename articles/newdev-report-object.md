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

[!INCLUDE[dyn_fin_dev_preview](../dynamics-nav/includes/newdev_dev_preview.md)]

# Report Object
Reports are used to print or display information from a database. You can use a report to structure and summarize information, and to print documents, such as sales quotes and invoices.

Creating a report consists of two primary tasks; the first task is to create the underlying data model and the next is to define the visual layout that displays the data. The report object defines the underlying data model and specifies which database tables and fields to pull data from. When the report is run, that data is displayed in a specified layout; the visual layout, which determines the content and format of a report when it is viewed and printed.

You build the layout of a report by arranging data items and columns, and specifying the general format, such as text font and size. There are two types of report layouts; client report definition, also called RDCL layouts and Word layouts. RDLC layouts are defined in Visual Studio Report Designer or Microsoft SQL Server Reporting Services Report Builder. Word layouts are created using Word. Word layouts are based on a Word document that includes a custom XML part representing the report dataset.

## Snippet support
Typing the shortcut ```treport``` will create the basic layout for a report object when using the AL Extension in Visual Studio Code.

## Report example
The following example is a report that shows a summary of receivables for customers and payables for vendors. The report object defines a dataset of columns from the General Ledger Setup table. In the ```requestpage``` section, the layout and actions are defined. In this report there are three fields on the requst page; the starting date, the number of periods and period length. 

```
report 70000005 "Modern Receivables-Payables"
{
  CaptionML=ENU='Receivables-Payables';
  RDLCLayout = 'Receivables-Payables.rdlc';

  dataset
  {
    dataitem("General Ledger Setup";"General Ledger Setup")
    {
      DataItemTableView=sorting("Primary Key")
                        where("Primary Key" = const());
      column(CompanyName;COMPANYNAME)
      {
      }
      column(GLSetupCustBalancesDue;GLSetup."Cust. Balances Due")
      {
        AutoFormatType=1;
      }
      column(GLSetupVenBalancesDue;GLSetup."Vendor Balances Due")
      {
        AutoFormatType=1;
      }
      column(NetBalancesDueLCY;NetBalancesDueLCY)
      {
        AutoFormatType=1;
      }
      column(GLSetupCustVenBalancesDue;GLSetup."Cust. Balances Due" - GLSetup."Vendor Balances Due")
      {
        AutoFormatType=1;
      }
      column(BeforeCustBalanceLCY;beforeCustBalanceLCY)
      {
      }
      column(BeforeVendorBalanceLCY;beforeVendorBalanceLCY)
      {
      }
      column(VenBalancesDue_GLSetup;"Vendor Balances Due")
      {
      }
      column(CustBalancesDue_GLSetup;"Cust. Balances Due")
      {
      }
      column(CustVenBalancesDue_GLSetup;"Cust. Balances Due" - "Vendor Balances Due")
      {
        AutoFormatType=1;
      }
      column(PrimaryKey_GLSetup;"Primary Key")
      {
      }
      column(ReceivablesPayablesCaption;ReceivablesPayablesCaptionLbl)
      {
      }
      column(PageCaption;PageCaptionLbl)
      {
      }
      column(DueDateCaption;DueDateCaptionLbl)
      {
      }
      column(CustBalDueCaption;CustBalDueCaptionLbl)
      {
      }
      column(VendBalDueCaption;VendBalDueCaptionLbl)
      {
      }
      column(BalDateLCYCaption;BalDateLCYCaptionLbl)
      {
      }
      column(NetChangeLCYCaption;NetChangeLCYCaptionLbl)
      {
      }
      column(BeforeCaption;BeforeCaptionLbl)
      {
      }
      column(AfterCaption;AfterCaptionLbl)
      {
      }
      column(TotalCaption;TotalCaptionLbl)
      {
      }
      dataitem(PeriodLoop;Integer)
      {
        DataItemTableView=SORTING(Number);
        column(GLSetupDateFilter;GLSetup.GetFilter("Date Filter"))
        {
        }

        trigger OnAfterGetRecord();
        begin
          StartDate := EndDate + 1;
          EndDate := CalcDate(PeriodLength,StartDate) - 1;
          MultiplyAmounts;
        end;

        trigger OnPreDataItem();
        begin
          if StartDate <> 0D then begin
            EndDate := StartDate - 1;
            StartDate := 0D;
            MultiplyAmounts;
            beforeCustBalanceLCY := GLSetup."Cust. Balances Due";
            beforeVendorBalanceLCY := GLSetup."Vendor Balances Due";
          end;
          SetRange(Number,1,NoOfPeriods);
        end;
      }
    }
  }

  requestpage
  {
    SaveValues=true;

    layout
    {
      area(content)
      {
        group(Options)
        {
          CaptionML = ENU='Options';
          field(StartDate;StartDate)
          {
            ApplicationArea = Basic,Suite;
            CaptionML = ENU='Starting Date';
            NotBlank = true;
            ToolTipML = ENU='Specifies the date from which the report or batch job processes information.';
          }
          field(NoOfPeriods;NoOfPeriods)
          {
            ApplicationArea = Basic,Suite;
            CaptionML = ENU='No. of Periods';
            ToolTipML = ENU='Specifies how many accounting periods to include.';
          }
          field(PeriodLength;PeriodLength)
          {
            ApplicationArea = Basic,Suite;
            CaptionML = ENU='Period Length';
            ToolTipML = ENU='Specifies the length of each period, for example, enter "1M" for one month.';
          }
        }
      }
    }

    actions
    {
    }

    trigger OnOpenPage();
    begin
      if StartDate = 0D then
        StartDate := WORKDATE;
      if NoOfPeriods = 0 then
        NoOfPeriods := 1;
      if Format(PeriodLength) = '' then
        Evaluate(PeriodLength,'<1M>');
    end;
  }

  labels
  {
  }

  trigger OnInitReport();
  begin
    StartDate := WORKDATE;
    NoOfPeriods := 1;
    Evaluate(PeriodLength,'<1M>');
  end;

  var
    GLSetup : Record 98; //"General Ledger Setup";
    StartDate : Date;
    EndDate : Date;
    NoOfPeriods : Integer;
    PeriodLength : DateFormula;
    NetBalancesDueLCY : Decimal;
    beforeCustBalanceLCY : Decimal;
    beforeVendorBalanceLCY : Decimal;
    ReceivablesPayablesCaptionLbl : TextConst ENU='Receivables-Payables';
    PageCaptionLbl : TextConst ENU='Page';
    DueDateCaptionLbl : TextConst ENU='Due Date';
    CustBalDueCaptionLbl : TextConst ENU='Cust. Balances Due (LCY)';
    VendBalDueCaptionLbl : TextConst ENU='Vendor Balances Due (LCY)';
    BalDateLCYCaptionLbl : TextConst ENU='Balance at Date (LCY)';
    NetChangeLCYCaptionLbl : TextConst ENU='Net Change (LCY)';
    BeforeCaptionLbl : TextConst ENU='...Before';
    AfterCaptionLbl : TextConst ENU='After...';
    TotalCaptionLbl : TextConst ENU='Total';

  local procedure MultiplyAmounts();
  begin
    with GLSetup do begin
      SetRange("Date Filter",StartDate,EndDate);
      CalcFields("Cust. Balances Due","Vendor Balances Due");
      NetBalancesDueLCY := NetBalancesDueLCY + "Cust. Balances Due" - "Vendor Balances Due";
    end;
  end;

  procedure InitializeRequest(NewStartDate : Date;NewNoOfPeriods : Integer;NewPeriodLength : DateFormula);
  begin
    StartDate := NewStartDate;
    NoOfPeriods := NewNoOfPeriods;
    PeriodLength := NewPeriodLength;
  end;
}


```

## See Also
[Developing Extensions Using the New Development Environment](newdev-dev-overview.md)  
[Developer Reference](newdev-reference-overview.md)  
[Page Extension Object](newdev-page-ext-object.md)  
[Pages](pages.md)  
[Tables](tables.md)  
[Page Properties](page-properties.md)
