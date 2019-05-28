---
title: OpenAPI Specification | Microsoft Docs
description: Open API Specification for Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/25/2019
ms.author: solsen, henrikwh
---

# OpenAPI Specification for [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)]
[!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] has a OpenAPI Specification for [v1.0 of the Standard APIs](https://docs.microsoft.com/en-us/dynamics-nav/api-reference/v1.0/index).

[OpenAPI Specification](https://swagger.io/docs/specification/about/) (previously known as Swagger) is a way of describing REST APIs. OpenAPI describes the contract or interface for a given REST API: endpoints, security schemes, methods/verbs, parameters, models, headers etc.  

> [!NOTE]  
> Download OpenAPI Specification for Business Central in [JSON](v1.0.json) or [YML](v1.0.yaml) format.

## Exploring the APIs
For exploring [!INCLUDE[d365fin_long_md](../includes/d365fin_long_md.md)] APIs many tools are avaliable. A few examples of tools is listed here:

- [Swaggerhub](https://swagger.io/tools/swaggerhub/) from SmartBear
- Visual Studio Code extension, [Swagger Viewer](https://marketplace.visualstudio.com/items?itemName=Arjun.swagger-viewer).
- Node.js using [swagger-ui-express](https://github.com/scottie1984/swagger-ui-express)

The provided Business Central contract user OAuth. For test purposes and convenience, A Business Central *Test* Azure Active Directory application has been made avalible. When authorizing, provide ```client_id: 060af3ac-70c3-4c14-92bb-8a88230f3f38``` and check the scope ```Financials.ReadWrite.All```.

Using [Node.js](https://nodejs.org) and [swagger-ui-express](https://github.com/scottie1984/swagger-ui-express) this sample can be used: 
```javascript
const express = require('express');
const app = express();
const port = 3000;
const swaggerUi = require('swagger-ui-express');
const swaggerDocument = require('./v1.0.json');

var options = { };
 
app.use('/', swaggerUi.serve, swaggerUi.setup(swaggerDocument, options));

app.listen(port, () => console.log(`Swagger-UI for Business Central listening on port ${port}!`))
```


## See also
[OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification)

[Working with Dynamics 365 Business Central in Microsoft Graph](resources/dynamics_overview.md)
