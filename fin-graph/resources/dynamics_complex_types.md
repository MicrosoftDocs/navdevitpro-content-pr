---
title: Complex Types JSON | Microsoft Docs
description: Complex data types JSON.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/17/2017
ms.author: solsen
---

# Complex types JSON
These are the various complex types in Dynamics 365 for Financials. You can see usage of these complex types in the various individual methods that make use of them.

# Item category

Represents an Item Category complex type in Dynamics 365 for Financials.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|categoryId|string|The unique ID of the item category.|
|description|string|Specifies the description of the item category.|

```json
"ItemCategory" 
{ 
  "categoryId": "string", 
  "description": "string" 
} 
```

# Unit of measure

Represents a Unit of Measure complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|unitCode|string|The unique ID of the unit of measure.|
|unitName|string|Specifies the description of the unit of measure.|
|symbol|string|Specifies a graphical representation of the unit of measure.|
|unitConversion|Specifies the conversion rate to a different (target) unit of measure.|

```json
"UnitOfMeasure" 
{  
  "unitCode":  "string", 
  "unitName": "string", 
  "symbol": "string", 
  "unitConversion": "NAV.ItemUnitOfMeasureConversion" 
} 
```

# Unit of measure conversion

Represents a Unit of Measure Conversion complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|toUnitOfMeasure|string|Specifies the unit of measure to convert to.|
|fromToConversionRate|decimal|Specifies what the (source) base unit of measure is multiplied with in order to convert to the target unit of measure.|

```json
"ItemUnitOfMeasureConversion" 
{ 
"toUnitOfMeasure": "string", 
"fromToConversionRate": "decimal" 
} 
 ```

 # Payment method

Represents a Payment Method complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|code|string|The unique code of the payment method.|
|description|string|Specifies a text that describes the payment method.|

```json
"PaymentMethod" 
{ 
"code": "string", 
"description": "string" 
} 
 ```

 # Payment terms

Represents a Payment Terms complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|code|string|The unique code of the payment terms.|
|description|string|Specifies a text that describes the payment terms.|

```json
"PaymentTermsType" 
{ 
"code": "string", 
"description": "string" 
} 
 ```

 # Postal address

Represents a Postal Address complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|street|string|Postal address street.|
|city|string|Postal address city.|
|state|string|Postal address state.|
|countryLetterCode|string|Postal address country letter code (two character word)|
|postalCode|string|Postal address post code|

```json
"PostalAddress" 
{ 
"street": "string",
"city": "string", 
"state": "string", 
"countryLetterCode": "string", 
"postalCode": "string" 
} 
 ```

 # Shipment method

Represents a Shipment Method complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|code|string|The unique code of the shipment method.|
|description|string|Specifies the description of the shipment method.|

```json
"ShipmentMethod" 
{ 
"code": "string", 
"description": "string" 
} 
```

# Line details

Represents a Line Details complex type in Dynamics 365 for Financials.       

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|number|string|The sequence number of the document line details.|
|displayName|string|The display name of the line.|

```json
"documentLineObjectDetails" 
{ 
"number": "string", 
"displayName": "string" 
} 
```

## See also
[Working with Dynamics 365 for Finance and Operations, Business Edition in Microsoft Graph](../resources/dynamics_overview.md) 
