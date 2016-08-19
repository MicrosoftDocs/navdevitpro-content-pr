---
title: "How to: Use OData to Return-Obtain a JSON Document"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 055f76ec-ef51-4320-b5e5-983f469f3dd8
caps.latest.revision: 3
---
# How to: Use OData to Return-Obtain a JSON Document
You can publish a page as a web service and consume it using JavaScript Object Notation \(JSON\).  
  
### To obtain a document based on JSON  
  
1.  You can build applications that consume and display [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)] data using JSON. This example assumes that you have registered and published a page web service in [!INCLUDE[navnow](../dynamics-nav/includes/navnow_md.md)]. For more information, see [Walkthrough: Creating and Interacting with a Page Web Service \(OData\)](../Topic/Walkthrough:%20Creating%20and%20Interacting%20with%20a%20Page%20Web%20Service%20\(OData\).md).  
  
2.  Start Windows Internet Explorer. In the **Address** field, enter a URI in this format:  
  
    ```  
    http://<Server>:<WebServicePort>/<ServerInstance>/OData/<web service>?$format=json  
    ```  
  
     If [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] is running on the local computer and is using the default [!INCLUDE[nav_server](../dynamics-nav/includes/nav_server_md.md)] instance and OData port, and you have published a web service that is based on page 21 that is called **Customer**, then the address is:  
  
    ```  
    http://localhost:7048/DynamicsNAV/OData/Customer?$format=json  
    ```  
  
     This generates a text file that contains metadata and data from the web service. You can open the file from the browser, or you can save it to disk.  
  
    > [!NOTE]  
    >  The value of the format attribute must be lowercase: `?$format=json`.  
  
     If you want to consume the web service as JSON\-P, you can add the `?$callback=<callback function name>` parameter.  
  
     You can use a similar URI to return the web service as an AtomPub document, in which case the attribute is `?$format=atom`. For more information, see [How to: Use OData to Return\-Obtain an AtomPub Document](../Topic/How%20to:%20Use%20OData%20to%20Return-Obtain%20an%20AtomPub%20Document.md).  
  
## See Also  
 [Using OData Web Services to Modify Data](../dynamics-nav/Using-OData-Web-Services-to-Modify-Data.md)