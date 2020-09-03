---
title: subscriptions resource type | Microsoft Docs
description: A subscriptions object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen,henrikwh
---

# subscriptions resource type

Represents a webhook subscriptions object in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)]. Requests issued against the subscriptions entity, manages webhook subscriptionss for a tenant.

## Methods

| Method       | Return Type  |Description|
|:-------------|:-------------|:----------|
|[GET](../api/dynamics_subscriptions_get.md)|subscriptionss|Get subscriptionss object.|
|[POST](../api/dynamics_subscriptions_create.md)|subscriptionss|Create subscriptionss object.|
|[PATCH](../api/dynamics_subscriptions_update.md)|subscriptionss|Update subscriptionss object.|
|[DELETE](../api/dynamics_subscriptions_delete.md)|subscriptionss|Delete subscriptionss object.|

## Properties

| Property | Type	|Description| 
|:---------------|:--------|:----------|
|subscriptionsId|string|Unique key for the subscriptions. |
|notificationUrl|string|URL to which webhook notifications are sent.|  
|resource|string|URL for the resource being subscribed to. Supports relative and absolute URL.|
|userId|GUID|The ID of user that has created the subscriptions.|
|lastModifiedDateTime|datetime|Timestamp for when the subscriptions was modified.|
|clientState|string|Client state will be delivered with every notification. This can be used as a secret to verify message or for managing state if needed.|
|expirationDateTime|datetime|Date and time for when the webhook will expire.|

## JSON representation

Here is a JSON representation of the resource.

```json
{
   "subscriptionId": "string",
   "notificationUrl": "string",
   "resource": "string",
   "userId": "GUID",
   "lastModifiedDateTime": "datetime",
   "clientState": "string",
   "expirationDateTime": "datetime",
   "systemCreatedAt": "datetime",
   "systemCreatedBy": "GUID",
   "systemModifiedAt": "datetime",
   "systemModifiedBy": "GUID"
}

```

## See also



[Error Codes](../dynamics_error_codes.md)  
[Get subscriptionss](../api/dynamics_subscriptions_get.md)  
[Create subscriptionss](../api/dynamics_subscriptions_create.md)  
[Update subscriptionss](../api/dynamics_subscriptions_update.md)  
[Delete subscriptionss](../api/dynamics_subscriptions_delete.md)  


[Error Codes](../dynamics_error_codes.md)  
