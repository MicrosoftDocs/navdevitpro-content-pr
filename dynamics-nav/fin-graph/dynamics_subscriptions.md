---
title: Managing Subscriptions | Microsoft Docs
description: Overview of how to manage subscriptions to Dynamics 365 Business Central API.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/24/2018
ms.author: solsen
---

# Managing Subscriptions
By default, a subscription lives for 3 days. The value is specified in the CustomSettings.config file under the ApiSubscriptionExpiration entry in order for it to be modified on premise.

For the `POST` and `PATCH` requests service must complete the handshake. During the POST and PATCH request we will invoke the `notificationUrl` provided with the `POST` request like:
```
notificationUrl?validationToken=value
```

The body will contain the “Client State” that was provided in the `POST` or `PATCH`request, so that the service can verify if the request is coming from us. The service has 5 seconds to respond to this challenge. The response should contain the validation token as the sole value in the body.

This is done as a verification to prevent any unwanted traffic, service must reply that it wants to receive the webhooks. Without that check someone could register a target service to receive the notifications and use it as a targeted attack. 

To remove the subscription, it is sufficient to execute a `DELETE` request.
There is a maximum number of subscriptions specified in the ApiSubscriptionMaxNumberOfSubscriptions in the CustomSettings.config file. This value is per tenant and it is currently set to `200`, which means that a single tenant can have 200 subscriptions in total.

## Limitations
Subscriptions are not allowed for API pages that are based on: 
- Query objects of the type API.
- Pages that have composite keys (multi value keys).
- Pages that use temporary or system tables as a source.

## Notifications
The notification payload contains following fields:

||||
|----|----|----|
|subscriptionId|GUID|The ID of the subscription|
|clientState|TEXT 250|Provided when subscription was created, used to store state or validate it is the BC server that is calling you back.|
|expirationDateTime|datetime|When the subscription is expiring|
|resource||the link to the record / resource that changed. Client should use this one to read the entity that was updated|
|changeType||created, updated, deleted, collection|
|lastModifiedDateTime||When the change happened on the resource specified above|

> [!NOTE]  
> The client should expect that they can get the different changeType for the same resource. For example, for `api/beta/ companies(f64eba74-dacd-4854-a584-1834f68cfc3a)/customers` there can be 3 notifications, created, updated, deleted. That means that the entity was created, updated and deleted at the end. 

> [!NOTE]  
> If there are too many changes, they will be grouped under the collection. This usually means that the client should read the URL provided in the resource and fetch all the records. If there were few changes and no deletes, a lastModifiedDateTime filter will be provided, so that it is sufficient to update the cache on only impacted entities. If there were any deletes, then the client has to fetch the entire set. Currently the limit per resource is 100 and it is controlled by ApiSubscriptionMaxNumberOfNotifications in the CustomSettings.config file on the server folder.
In case of multiple sequential updates on the same entity (MODIFY is triggered many times in a row without other changes) they will be grouped into a single updated notification. 



## Working with notifications
After the subscription is created, we will push the notifications on every update that happens for the entity requested. Notifications may be lossy or out of order, client has to take this into the account. 
We will batch the notifications per URL, so clients should expect to get multiple resources in a single payload (e.g. customer and item). 
Example of the payload **MISSING CANNOT COPY FROM IMAGE**

The service must respond within 30 seconds. This value is specified under the ApiSubscriptionSendingNotificationTimeout in the CustomSettings.config under the server folder.

If we cannot deliver the notification, we will issue multiple retries with exponential back-off. The service must respond with following error codes: `408 - Request Timeout`, `429 - Too Many Requests or any error in 500-599 range (5xx)`. If service responds with any other code than listed above, no retries will be attempted and the subscription will be deleted; it is not considered valid. 

After at least 5 additional unsuccessful attempts (approx. a day and a half) the subscription will be deleted.

## See also
[Subscription Resource Type](resources/dynamics_subscription.md)  
[Get subscriptions](api/dynamics_subscription_get.md)  
[Create subscriptions](api/dynamics_subscription_create.md)  
[Update subscriptions](api/dynamics_subscription_update.md)  
[Delete subscriptions](api/dynamics_subscription_delete.md)  
