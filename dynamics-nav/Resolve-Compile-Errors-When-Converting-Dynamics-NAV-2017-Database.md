---
title: "Compilation Errors When Converting a Microsoft Dynamics NAV 2016 Database"
ms.custom: na
ms.date: 20/03/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: 6ea75b39-cf7d-4c88-868b-86fa0be2426b
caps.latest.revision: 4
manager: edupont
author: jswymer
---
# Resolving Compilation Errors When Converting a Dynamics NAV 2017 Database
When you convert a [!INCLUDE[nav2017](includes/nav2017.md)] database, you will receive compilation errors in several standard [!INCLUDE[navnow](includes/navnow_md.md)] objects. This article describes how to resolve these errors.

## Compilation Errors
The following table lists the compilation errors that might occur when you build the server application objects during the database conversion, with a link to a solution for fixing the problem.

|  Object Type  |  Object ID  |  Object Name  |  Function/Trigger  |  Error Message  |  Solution  |
|---------------|-------------|---------------|--------------------|------------|------------|
|Codeunit|700|Page Management|CheckAnyRoleAssignedToUser|Type conversion is not possible because 1 of the operators contains an invalid type. Text = Integer.|See [Resolving Table 5330 CRM Connection Setup Error](Resolve-Table-5330-Error-Converting-Database.md). |
|Codeunit|5330|CRM Integration Management|CheckAnyRoleAssignedToUser|You have specified an unknown variable. Entities Define the variable under 'Global C/AL symbols'.|See [Resolving Table 5330 CRM Connection Setup Error](Resolve-Table-5330-Error-Converting-Database.md). |
|Codeunit|6303|Azure AD Auth Flow|Initialize|Type conversion is not possible because 1 of the operators contains an invalid type. DotNet := GUID|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|
|Page|9621|New Page Patterns List Part| SaveNewFieldDefinition|Type conversion is not possible because 1 of the operators contains an invalid type. Integer := OemMText|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|
|Page|9626|New Page Patterns List Part| - |TableData 2000000174 does not exist.|See [Resolving Dynamics Online Payment Service Errors](Resolve-Dynamics-Online-Errors-Database-Conversion.md).|

## Codeunit 700 Page Management

On the  `LOCAL VerifyPageID(TableID : Integer;PageID : Integer) : Boolean` function, change the `PageMetadata.APIVersion` variable to `PageMetadata.SourceTable`. 

**Before:**

```
EXIT(PageMetadata.GET(PageID) AND (PageMetadata.APIVersion = TableID));
```

**After:**

```
EXIT(PageMetadata.GET(PageID) AND (PageMetadata.SourceTable = TableID));
```

## Codeunit 5330 CRM Integration Management

On the `LOCAL CheckRoleAssignedToUser` function, change the version number of the .NET type that is used on the `OrganizationServiceProxy` parameter, `QueryExpression` and `EntityCollection` variables from **7.0.0.0** to **8.0.0.0**. For example:

**OrganizationServiceProxy parameter - before**
```
Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy.'Microsoft.Xrm.Sdk, Version=7.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

**OrganizationServiceProxy parameter - after**
```
Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

<!--
**QueryExpression variable - before**
```
Microsoft.Xrm.Sdk.Query.QueryExpression.'Microsoft.Xrm.Sdk, Version=7.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

**QueryExpression variable - after**
```
Microsoft.Xrm.Sdk.Query.QueryExpression.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```


**EntityCollection variable - Before:**

```
Microsoft.Xrm.Sdk.EntityCollection.'Microsoft.Xrm.Sdk, Version=7.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

**EntityCollection variable - After**
```
Microsoft.Xrm.Sdk.EntityCollection.'Microsoft.Xrm.Sdk, Version=8.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'
```

-->

## Codeunit 6303 Azure AD Auth Flow
On the `Initialize`and  `OnInitialize` functions, remove the `SecurityId` parameter and all references so that the function signatures and code are as follows.

**Initialize function - before**

```
Initialize(SecurityId : GUID;RedirectUri : Text)
  IF CanHandle THEN
    AuthFlow := AuthFlow.ALAzureAdCodeGrantFlow(SecurityId,Uri.Uri(RedirectUri))
  ELSE
    OnInitialize(SecurityId,RedirectUri,AuthFlow);
```

**Initialize function - after**
```
Initialize(RedirectUri : Text)
  IF CanHandle THEN
    AuthFlow := AuthFlow.ALAzureAdCodeGrantFlow(Uri.Uri(RedirectUri))
  ELSE
    OnInitialize(RedirectUri,AuthFlow);
```

**OnInitialize function - before**
```
LOCAL [External] [IntegrationEvent] OnInitialize(RedirectUri : Text;VAR AzureADAuthFlow : DotNet "Microsoft.Dynamics.Nav.Runtime.ALAzureAdCodeGrantFlow")
```

**OnInitialize function - after**
```
LOCAL [IntegrationEvent] OnInitialize(SecurityId : GUID;RedirectUri : Text;VAR AzureADAuthFlow : DotNet "Microsoft.Dynamics.Nav.Runtime.ALAzureAdCodeGrantFlow")
```

## Page 9621 New Page Patterns List Part

**Before**

LOCAL SaveNewFieldDefinition()
NewFieldId := NavDesigner.CreateTableField(PageId,NewFieldName,'Option',35,NewFieldDescr);
IF NewFieldId > 0 THEN BEGIN
  NavDesigner.SetFieldProperty(NewFieldId,'Caption',NewFieldCaption);
  NavDesigner.SetFieldProperty(NewFieldId,'OptionString',NewFieldOptionsValue);
END;

IF NewFieldId = 0 THEN
  ERROR('');

**After**


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
      FieldType := NewFieldType;
      IF NewFieldType = 'Related Data Field' THEN BEGIN
        IF (RelatedTableName = '') OR (RelatedTableFieldName = '') THEN
          ERROR(RelatedFieldValidationErrorErr);

        FieldDetails.SETFILTER(TableNo,FORMAT(RelatedTableNumber));
        FieldDetails.SETFILTER(FieldName,RelatedTableFieldName);
        IF FieldDetails.FINDFIRST THEN BEGIN
          FieldType := FORMAT(FieldDetails.Type);
          TextFieldTypeDataLength := 0;
          IF (FieldType = 'Text') OR (FieldType = 'Code') THEN
            TextFieldTypeDataLength := FieldDetails.Len;
        END;
      END;

      PropertyDictionary := PropertyDictionary.Dictionary;
      PropertyDictionary.Add(NavDesignerProperty.Description,NewFieldDescr);
      PropertyDictionary.Add(NavDesignerProperty.Caption,NewFieldCaption);

      CASE NewFieldType OF
        'Text','Code':
          PropertyDictionary.Add(NavDesignerProperty.Editable,ConvertToBooleanText(IsFieldEditable));
        'Decimal':
          BEGIN
            PropertyDictionary.Add(NavDesignerProperty.DecimalPlaces,FORMAT(Field_NoOfDecimalPlaces));
            PropertyDictionary.Add(NavDesignerProperty.BlankZero,ConvertToBooleanText(IsBlankZero));
          END;
        'Integer','BigInteger':
          PropertyDictionary.Add(NavDesignerProperty.BlankZero,ConvertToBooleanText(IsBlankZero));
        'Option':
          BEGIN
            PropertyDictionary.Add(NavDesignerProperty.OptionString,NewOptionsFieldValues);
            PropertyDictionary.Add(NavDesignerProperty.InitValue,NewFieldInitialValue);
          END;
      END;

      IF PageId > 0 THEN
        NewFieldId := NavDesigner.CreateTableField(PageId,NewFieldName,FieldTypeEnumValue,TextFieldTypeDataLength,PropertyDictionary)
      ELSE
        ERROR(PageIdNotFoundErr);

      IF NewFieldId = 0 THEN
        ERROR(FieldCreationErrorErr);
    END;


## See Also  
[Converting a Database](Converting-a-Database.md)  
