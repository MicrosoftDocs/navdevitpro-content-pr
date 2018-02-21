---
title: "Page 9621 Add Page Fields Error When Converting to Dynamics NAV 2018"
description: "Explains how to resolve the compilation error that you get for Page 9621 Add Page Fields when converting a database from Dynamics NAV 2017 to 2018."
ms.custom: na
ms.date: 27/11/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
author: jswymer
---
## Resolving Page 9621 Add Page Fields Compilation Error 
This article explains how to resolve the compilation error that you get for page **9621 Add Page Fields** when converting a [!INCLUDE[nav2017](includes/navcorfu_md.md)] database to [!INCLUDE[nav2018_md](includes/nav2018_md.md)].

To resolve this error, you can update page **9621 Add Page Fields** in the converted database to support the latest platform changes by replacing its code with the code that follows: 

1. Copy the code to a text editor, and save it as a .txt file type.
2. Use the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] to import and compile the file to the converted database.

> [!NOTE]  
>  If the page **9621 Add Page Fields**  object in your database includes custom code, then you might have to resolve conflicts with your custom code.

```
OBJECT Page 9621 Add Page Fields
{
  OBJECT-PROPERTIES
  {
    Date=;
    Time=;
    Version List=;
  }
  PROPERTIES
  {
    Editable=Yes;
    CaptionML=ENU=New Field;
    DeleteAllowed=No;
    LinksAllowed=No;
    SourceTable=Table2000000171;
    PageType=NavigatePage;
    SourceTableTemporary=Yes;
    OnOpenPage=VAR
                 DesignerPageId@1000 : Codeunit 9621;
               BEGIN
               END;

    ActionList=ACTIONS
    {
      { 20      ;    ;ActionContainer;
                      Name=ActionItems;
                      CaptionML=ENU=ActionItems;
                      ActionContainerType=ActionItems }
      { 21      ;1   ;Action    ;
                      Name=Next;
                      CaptionML=ENU=Next;
                      ApplicationArea=#Basic,#Suite;
                      Visible=IsNextVisible;
                      InFooterBar=Yes;
                      Image=NextRecord }
      { 22      ;1   ;Action    ;
                      Name=Previous;
                      CaptionML=ENU=Previous;
                      ApplicationArea=#Basic,#Suite;
                      Visible=IsBackVisible;
                      InFooterBar=Yes;
                      Image=PreviousRecord }
      { 23      ;1   ;Action    ;
                      Name=Create;
                      CaptionML=ENU=Create;
                      ApplicationArea=#Basic,#Suite;
                      Visible=IsCreateBtnVisible;
                      InFooterBar=Yes;
                      Image=NextRecord;
                      OnAction=VAR
                                 FieldTypeOptions@1000 : 'Number,Text,Boolean,DateTime,RelatedData,Option';
                               BEGIN
                               END;
                                }
      { 24      ;1   ;Action    ;
                      Name=Finish;
                      CaptionML=ENU=Finish;
                      ApplicationArea=#Basic,#Suite;
                      Visible=IsFinishBtnVisible;
                      InFooterBar=Yes;
                      Image=Approve }
    }
  }
  CONTROLS
  {
    { 1   ;    ;Container ;
                Name=PageControl;
                CaptionML=ENU=Page Control;
                ContainerType=ContentArea }

    { 2   ;1   ;Group     ;
                CaptionML=ENU=Select Type;
                GroupType=Group }

    { 3   ;2   ;Field     ;
                Name=NewFieldDescription;
                CaptionML=ENU=By adding a new field to the table you can store and display additional information about a data entry.;
                ApplicationArea=#Basic,#Suite }

    { 4   ;2   ;Part      ;
                Name=FieldTypes;
                CaptionML=ENU=Choose type of field;
                ApplicationArea=#Basic,#Suite;
                Description=Choose type of field';
                PagePartID=Page9622;
                Editable=FALSE;
                PartType=Page }

    { 7   ;1   ;Group     ;
                CaptionML=ENU=Step details;
                GroupType=Group }

    { 8   ;2   ;Group     ;
                CaptionML=ENU=Step 1 of 2;
                GroupType=Group }

    { 9   ;3   ;Group     ;
                Name=Step1Header;
                CaptionML=ENU=FIELD DEFINITION;
                GroupType=Group;
                InstructionalTextML=ENU=Fill in information about the new field. You can change the field information later if you need to. }

    { 10  ;4   ;Field     ;
                Name=NewFieldName;
                CaptionML=ENU=Name;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldName;
                ShowMandatory=True }

    { 11  ;4   ;Field     ;
                Name=NewFieldCaption;
                CaptionML=ENU=Caption;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldCaption }

    { 12  ;4   ;Field     ;
                Name=NewDescription;
                CaptionML=ENU=Description;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldDescr;
                MultiLine=Yes }

    { 47  ;4   ;Group     ;
                GroupType=Group }

    { 44  ;5   ;Field     ;
                Name=RelatedFieldType;
                CaptionML=ENU=Linked value Type;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=RelatedFieldType }

    { 13  ;1   ;Group     ;
                CaptionML=ENU=Step 2;
                GroupType=Group }

    { 30  ;2   ;Group     ;
                CaptionML=ENU=Step 2 of 2;
                GroupType=Group;
                InstructionalTextML=ENU=Choose how the system initializes and validates the text that is typed or pasted into the field. }

    { 14  ;3   ;Group     ;
                GroupType=Group }

    { 19  ;4   ;Group     ;
                GroupType=Group }

    { 5   ;5   ;Field     ;
                Name=NumberFieldType;
                CaptionML=ENU=Field data type;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NumberFieldTypes }

    { 36  ;5   ;Group     ;
                GroupType=Group }

    { 37  ;6   ;Field     ;
                Name=Field_NoOfDecimalPlaces;
                CaptionML=ENU=Number of decimal places;
                ApplicationArea=#Basic,#Suite;
                NotBlank=Yes;
                BlankZero=Yes;
                SourceExpr=Field_NoOfDecimalPlaces }

    { 28  ;5   ;Field     ;
                Name=Editable;
                CaptionML=ENU=Editable;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=IsFieldEditable }

    { 29  ;5   ;Field     ;
                Name=IsBlankZero;
                CaptionML=ENU=If zero show blank;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=IsBlankZero }

    { 25  ;4   ;Group     ;
                GroupType=Group }

    { 6   ;5   ;Field     ;
                Name=TextFieldType;
                CaptionML=ENU=Field data type;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=TextFieldType }

    { 33  ;5   ;Field     ;
                Name=DataLength;
                CaptionML=ENU=Text Length;
                ApplicationArea=#Basic,#Suite;
                BlankNumbers=BlankZero;
                SourceExpr=TextFieldTypeDataLength }

    { 53  ;5   ;Group     ;
                GroupType=Group }

    { 34  ;5   ;Field     ;
                Name=Editable_text;
                CaptionML=ENU=Editable;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=IsFieldEditable }

    { 26  ;4   ;Group     ;
                GroupType=Group }

    { 27  ;5   ;Field     ;
                Name=DateTimeFieldType;
                CaptionML=ENU=Field data type;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=DateTimeFieldType }

    { 32  ;5   ;Field     ;
                Name=typeDesc;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=FieldTypeMessage;
                Editable=False;
                MultiLine=Yes;
                ShowCaption=No }

    { 15  ;4   ;Group     ;
                Editable=True;
                GroupType=Group }

    { 16  ;5   ;Field     ;
                Name=OptionsValue;
                CaptionML=ENU=Options Value;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewOptionsFieldValues }

    { 17  ;5   ;Field     ;
                Name=InitialValue;
                CaptionML=ENU=Initial Value;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldInitialValue }

    { 39  ;3   ;Group     ;
                GroupType=Group }

    { 42  ;4   ;Group     ;
                CaptionML=ENU=Please select the related table and then the corresponding field.;
                GroupType=Group }

    { 41  ;5   ;Field     ;
                Name=TableSearch;
                CaptionML=ENU=Table;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=RelatedTableName;
                OnValidate=VAR
                             AvailableTables@1000 : Record 2000000136;
                             IsNumber@1001 : Integer;
                           BEGIN
                           END;

                OnLookup=VAR
                           AvailableTables@1001 : Record 2000000136;
                         BEGIN
                         END;
                          }

    { 43  ;5   ;Field     ;
                Name=FieldName;
                CaptionML=ENU=Field;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=RelatedTableFieldName;
                Editable=RelatedTableName <> '';
                OnValidate=VAR
                             FieldTable@1000 : Record 2000000041;
                           BEGIN
                           END;

                OnLookup=VAR
                           FieldTable@1000 : Record 2000000041;
                         BEGIN
                         END;
                          }

    { 40  ;4   ;Group     ;
                GroupType=Group }

    { 45  ;5   ;Field     ;
                Name=Method;
                CaptionML=ENU=Method;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=RelatedFieldMethod }

    { 38  ;5   ;Field     ;
                Name=ReverseSign;
                CaptionML=ENU=Reverse Sign;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=RelatedFieldFormulaCalc_ReverseSign }

    { 58  ;4   ;Group     ;
                Name=FilterSection;
                CaptionML=ENU=RELATED TABLE FILTER CRITERIA;
                Enabled=(RelatedTableName <> '') AND (RelatedTableFieldName <> '');
                GroupType=Group }

    { 56  ;5   ;Field     ;
                Name=RelatedTableFilterField;
                CaptionML=ENU=Filtered field;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=RelatedTableFilterFieldName;
                OnValidate=VAR
                             FieldTable@1000 : Record 2000000041;
                           BEGIN
                           END;

                OnLookup=VAR
                           FieldTable@1000 : Record 2000000041;
                         BEGIN
                         END;
                          }

    { 48  ;5   ;Group     ;
                GroupType=Group }

    { 54  ;6   ;Field     ;
                Name=Filter Type;
                CaptionML=ENU=Filter Type;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=FilterType }

    { 59  ;5   ;Group     ;
                GroupType=Group }

    { 57  ;6   ;Field     ;
                Name=CurrentTableFilterField;
                CaptionML=ENU=Filter Value From field;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=CurrentTableFilterFieldName;
                OnValidate=VAR
                             PageTableField@1000 : Record 2000000171;
                           BEGIN
                           END;

                OnLookup=VAR
                           PageTableField@1000 : Record 2000000171;
                         BEGIN
                         END;
                          }

    { 60  ;5   ;Group     ;
                GroupType=Group }

    { 61  ;6   ;Field     ;
                Name=Value;
                CaptionML=ENU=Value;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=FilterValue }

    { 52  ;1   ;Group     ;
                CaptionML=ENU=Step details;
                GroupType=Group }

    { 51  ;2   ;Group     ;
                Name=Step1Header_Boolean;
                CaptionML=ENU=FIELD DEFINITION;
                GroupType=Group;
                InstructionalTextML=ENU=Fill in information about the new field. You can change the field information later if you need to. }

    { 50  ;3   ;Field     ;
                Name=NewFieldName_Boolean;
                CaptionML=ENU=Name;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldName;
                ShowMandatory=True }

    { 49  ;3   ;Field     ;
                Name=NewFieldCaption_Boolean;
                CaptionML=ENU=Caption;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldCaption }

    { 46  ;3   ;Field     ;
                Name=NewDescription_Boolean;
                CaptionML=ENU=Description;
                ApplicationArea=#Basic,#Suite;
                SourceExpr=NewFieldDescr;
                MultiLine=Yes }

  }
  CODE
  {
    VAR
      NavDesignerProperty@1017 : DotNet "'Microsoft.Dynamics.Nav.Ncl, Version=11.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Dynamics.Nav.Runtime.Designer.DesignerFieldProperty";
      NavDesignerFieldType@1050 : DotNet "'Microsoft.Dynamics.Nav.Ncl, Version=11.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Dynamics.Nav.Runtime.Designer.DesignerFieldType";
      NavDesigner@1000 : DotNet "'Microsoft.Dynamics.Nav.Ncl, Version=11.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'.Microsoft.Dynamics.Nav.Runtime.Designer.NavDesignerALFunctions";
      PropertyDictionary@1037 : DotNet "'mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089'.System.Collections.Generic.Dictionary`2";
      IsNextVisible@1001 : Boolean;
      IsBackVisible@1004 : Boolean;
      IsCreateBtnVisible@1005 : Boolean;
      IsFinishBtnVisible@1007 : Boolean;
      NewFieldName@1008 : Text;
      NewFieldDescr@1009 : Text;
      NewFieldCaption@1010 : Text;
      NewOptionsFieldValues@1011 : Text;
      NewFieldInitialValue@1012 : Text;
      PageId@1014 : Integer;
      NewFieldId@1015 : Integer;
      NewFieldType@1016 : Text;
      NumberFieldTypes@1019 : 'Integer,Decimal,BigInteger';
      TextFieldType@1021 : 'Text,Code';
      IsTextFieldTypeVisible@1022 : Boolean;
      IsNumberFieldTypeVisible@1023 : Boolean;
      DateTimeFieldType@1024 : 'Date,DateTime,Time';
      IsDateTimeFieldTypeVisible@1025 : Boolean;
      TextFieldTypeDataLength@1032 : Integer;
      Field_NoOfDecimalPlaces@1035 : Text;
      IsOptionDetailsVisible@1026 : Boolean;
      IsFieldEditable@1027 : Boolean;
      IsBlankZero@1028 : Boolean;
      RelatedTableFieldName@1038 : Text;
      RelatedTableName@1039 : Text;
      RelatedFieldMethod@1041 : 'Sum,Average,Count';
      FilterType@1052 : 'CONST,FILTER,FIELD';
      RelatedTableNumber@1053 : Integer;
      RelatedTableFilterFieldName@1056 : Text;
      CurrentTableFilterFieldName@1058 : Text;
      FilterValue@1059 : Text;
      RelatedFieldFormulaCalc_ReverseSign@1029 : Boolean;
      RelatedFieldType@1033 : 'Linked value,Computed value';
      FieldType@1002 : Text;
      MandateFieldNameErr@1003 : TextConst 'ENU=Field name is required.';
      RelatedFieldValidationErrorErr@1006 : TextConst 'ENU=Table and Field values are required.';
      FieldCreationErrorErr@1018 : TextConst 'ENU=Error occurred while creating the field. Please validate the input values are correct and field name is unique.';
      InvalidRelatedFieldNameErr@1020 : TextConst '@@@="%1 = Field name";ENU=%1 field not found.';
      InvalidTableNumberOrNameErr@1034 : TextConst '@@@="%1 = Table name";ENU=%1 table not found.';
      CurrentNavigationPage@1036 : 'FieldSelectionPage,FieldBasicDefinitionPage,FieldAdvancedDefinitionPage';
      DateFieldDescMsg@1046 : TextConst 'ENU=Stores date of an event';
      FieldTypeMessage@1047 : Text;
      TimeFieldDescMsg@1048 : TextConst 'ENU=Stores time of an event';
      DateTimeFieldDescMsg@1049 : TextConst 'ENU=Stores Date and Time of an event';
      FieldTypeEnumValue@1042 : Integer;
      PageIdNotFoundErr@1013 : TextConst 'ENU=Please navigate to a card details page and begin process for field creation.';

    LOCAL PROCEDURE SaveNewFieldDefinition@2();
    VAR
      FieldDetails@1001 : Record 2000000041;
    BEGIN
    END;

    LOCAL PROCEDURE InitializeVariables@4();
    BEGIN
    END;

    LOCAL PROCEDURE ClearAllDynamicFieldsVisibility@6();
    BEGIN
    END;

    LOCAL PROCEDURE LoadRequestedPage@7(Page@1000 : Option);
    BEGIN
    END;

    LOCAL PROCEDURE ConvertToBooleanText@5(Value@1000 : Boolean) : Text;
    VAR
      Result@1001 : Text;
    BEGIN
    END;

    BEGIN
    END.
  }
}
```

## See Also  
 [Converting a Database](Converting-a-Database.md)  
 [Resolving Compilation Errors When Converting a Dynamics NAV 2017 Database](Resolve-Compile-Errors-When-Converting-Dynamics-NAV-2017-Database.md)  
 [How to: Import-Objects](How-to--Import-Objects.md)
