---
title: employees resource type | Microsoft Docs
description: An employee object in Dynamics 365 for Financials.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/11/2017
ms.author: solsen
---

# employees resource type
Represents an employee in Dynamics 365 for Financials.

## Methods

| Method                                              | Return Type|Description              |
|:----------------------------------------------------|:-----------|:------------------------|
|[GET Employees](../api/dynamics_get_employee.md)      |Employees  |Get an Employee object   |
|[POST Employees](../api/dynamics_create_employee.md)  |Employees  |Create an Employee object|
|[PATCH Employees](../api/dynamics_update_employee.md) |Employees  |Update an Employee object|
|[DELETE Employees](../api/dynamics_delete_employee.md)|none       |Delete an Employee object|

## Properties
| Property	         | Type	  |Description                                            |
|:-------------------|:-------|:------------------------------------------------------|
|id                  |GUID    |The employee ID. Non-editable.                         |
|number              |string  |The employee number. Read-Only.                        |
|displayName         |string  |The employee givenName + surname. Read-Only.           |
|givenName           |string  |The given name of the employee.                        |
|middleName          |string  |The middle name of the employee.                       |
|surname             |string  |The surname of the employee                            |
|jobTitle            |string  |The full name of the employee                          |
|address             |[NAV.PostalAddress](../resources/dynamics_complex_types.md)|Specifies the employee's address. This address will appear on all resource documents for the employee.|
|phoneNumber         |string  |Specifies the employee's telephone number.             |
|mobilePhone         |string  |Specifies the employee's mobile telephone number.      |
|email               |string  |Specifies the employee's email address.                |
|personalEmail       |string  |Specifies the employee's personal email address.       |
|employmentDate      |date    |Specifies the date when the employee began to work for the company.|
|terminationDate     |date    |Specifies the date when the employee was terminated, due to retirement or dismissal, for example.|
|status              |string  |Specifies the employee's status. Possible values are Active, Inactive or Terminated|
|birthDate           |date    |Specifies the employee's date of birth.                |
|picture             |stream  |The employee picture. Read-Only.                       |
|lastModifiedDateTime|datetime|The last datetime the employee was modified. Read-Only.|  


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "id": "GUID",
    "number": "string",
    "displayName": "string",
    "givenName": "string",
    "middleName": "string",
    "surname": "string",
    "jobTitle": "string",
    "address": "NAV.PostalAddress",
    "phoneNumber": "string",
    "mobilePhone": "string",
    "email": "string",
    "personalEmail": "string",
    "employmentDate": "date",
    "terminationDate": "date",
    "status": "string",
    "birthDate": "date",
    "picture": "stream",
    "lastModifiedDateTime": "datetime"
}

```
## See also
[Working with Dynamics 365 for Financials in Microsoft Graph](../resources/dynamics_overview.md) 
