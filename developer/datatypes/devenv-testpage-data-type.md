---
title: "TestPage Data Type"
ms.custom: na
ms.date: 06/08/2017
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2017"
ms.assetid: c702a57a-726f-43ec-978f-cabd2131a0ea
caps.latest.revision: 6
author: SusanneWindfeldPedersen
---
# TestPage Data Type
Stores test pages. A test page is a logical representation of a page that does not display a user interface (UI). The subtype of a test page is the page that it is used to test.  
  
A test page can be any page type. For more information [Page Object](../devenv-page-object.md). You can use test pages only within test codeunits.

There are three categories of TestPage data type methods: TestPage, TestPage field, and TestPage filter.
  
## TestPage methods
You use the TestPage Functions to:
-   Open and close test pages.
-   Navigate among records to display on the test page.
-   Navigate among fields on the test page.
-   Expand and collapse rows on a test page.
-   Create a new record from a test page.
-   Get the options and option count for an option field.
-   Get validation errors and error counts.

Here is a list of the TestPage methods:

[OPENEDIT Method](devenv-OPENEDIT-Method-TestPage.md)

[OPENNEW Method ](devenv-OPENNEW-Method-TestPage.md)

[OPENVIEW Method ](devenv-OPENVIEW-Method-TestPage.md)

[CLOSE Method ](devenv-CLOSE-Method-TestPage.md)

[TRAP Method ](devenv-TRAP-Method-TestPage.md)

[FIRST Method ](devenv-FIRST-Method-TestPage.md)

[LAST Method ](devenv-LAST-Method-TestPage.md)

[NEXT Method ](devenv-NEXT-Method-TestPage.md)

[PREVIOUS Method ](devenv-PREVIOUS-Method-TestPage.md)

[GOTOKEY Method ](devenv-GOTOKEY-Method-TestPage.md)

[GOTORECORD Method ](devenv-GOTORECORD-Method-TestPage.md)

[FINDFIRSTFIELD Method ](devenv-FINDFIRSTFIELD-Method-TestPage.md)

[FINDNEXTFIELD Method ](devenv-FINDNEXTFIELD-Method-TestPage.md)

[FINDPREVIOUSFIELD Method ](devenv-FINDPREVIOUSFIELD-Method-TestPage.md)

[GETFIELD Method ](devenv-GETFIELD-Method-TestPage.md) 

[EXPAND Method ](devenv-EXPAND-Method-TestPage.md)

[NEW Method ](devenv-NEW-Method-TestPage.md)

[GETOPTION Method \(TestPage Field\)](devenv-GETOPTION-Method-TestPage-Field.md)

[OPTIONCOUNT Method \(TestPage Field\)](devenv-OPTIONCOUNT-Method-TestPage-Field.md)

[GETVALIDATIONERROR Method \(TestPage, TestPage Field\)](devenv-GETVALIDATIONERROR-Method-TestPage-TestPage-Field.md)

[VALIDATIONERRORCOUNT Method \(TestPage, TestPage Field\)](devenv-VALIDATIONERRORCOUNT-Method-TestPage-TestPage-Field.md)

## TestPage field methods
The field methods enable you to view or change the value of a field on a test page.

Here is a list of the TestPage field methods:

[CAPTION Method](devenv-caption-method-fieldref-testpage-field.md)

[ASBOOLEAN Method](devenv-asboolean-method-testpage-field)

[ASDECIMAL Method](devenv-asdecimal-method-testpage-field)

[ASINTEGER Method](devenv-asinteger-method-testpage-field)

[ASSERTEQUALS Mehtod](devenv-assertequals-method-testpage-field)

[ASSISTEDIT Method](devenv-assistedit-method-testpage-field)

[DRILLDOWN Method](devenv-drilldown-method-testpage-field)

[GETVALIDATIONERROR Method](devenv-GETVALIDATIONERROR-Method-TestPage-TestPage-Field.md)

[LOOKUP Method](devenv-lookup-method-testpage-field)

[OPTIONCOUNT Method](devenv-optioncount-method-testpage-field)

[SETVALUE Method](devenv-setvalue-method-testpage-field)

[VALIDATIONERRORCOUNT Method \(TestPage, TestPage Field\)](devenv-VALIDATIONERRORCOUNT-Method-TestPage-TestPage-Field.md)

## TestPage filter methods
The filter methods enable you to filter data that can be accessed on a test page.

Here is a list of the TestPage filter methods:

[ASCENDING Method](devenv-ascending-method-testpage-filter)

[CURRENTKEY Method](devenv-currentkey-method-testpage-filter)

[GETFILTER Method](devenv-getfilter-method-testpage-filter)

[SETCURRENTKEY Method](devenv-setcurrentkey-method-testpage-filter)

[SETFILTER Method](devenv-setfilter-method-testpage-filter)

## See Also
[AL Methods](../devenv-al-methods.md)  
[TestRequestPage Data Type](devenv-testrequestpage-data-type.md)  