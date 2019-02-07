---
title: "Walkthrough: Creating and Interacting With an OData V4 Bound Action"
ms.author: solsen
ms.custom: na
ms.date: 07/01/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na   
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: efcf5eaf-b129-469d-b4f7-b8681574483e
caps.latest.revision: 90
author: SusanneWindfeldPedersen
---

# Walkthrough: Creating and Interacting With an OData V4 Bound Action
This walkthrough illustrates how you can publish a [!INCLUDE[navnow](includes/navnow_md.md)] function as an OData V4 web service action. 

## About This Walkthrough  
This walkthrough provides an overview of how to expose a function as a web service action and how to verify that the service is working as expected. The walkthrough illustrates the following tasks:

-   Publishing a [!INCLUDE[navnow](includes/navnow_md.md)] function as a web service.    
-   Verifying web service availability from a browser.

### Prerequisites  
To complete this walkthrough, you will need:  

-   [!INCLUDE[navnowlong](includes/navnowlong_md.md)] CTP 10 or later with a developer license.  

-   OData services and V4 endpoint enabled on the [!INCLUDE[nav_server_md](includes/nav_server_md.md)]. For more information, see [Configuring Dynamics NAV Server](Configuring-Microsoft-Dynamics-NAV-Server.md#ODataServices).

-   [!INCLUDE[demolong](includes/demolong_md.md)].  

-   The **Postman** app for testing the web service URI.

## Publishing a Function as a Web Service   
You publish a function as a Web service action by using the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] to create the function and the [!INCLUDE[navnow](includes/navnow_md.md)] Windows client or the [!INCLUDE[navnow](includes/navnow_md.md)] Web client for publishing the objects the function is for. The tutorial provides an example that will return a location header. A location header would be used to later issue a get request for the resulting object. Refer to the **Return a Value** section for an example that will return a value specified in your function.

### To create the function

#### Create a Copy action on the Sales Invoice page.

1. Open the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] and then connect to the [!INCLUDE[demoname](includes/demoname_md.md)] company.  

    Object Designer opens automatically in the development environment.  

2. Open page 43, **Sales Invoice**.
3. Create a new function on the page named `Copy`.
4. Open the properties for the function and set the properties to the following values.  

   |      Property      |  Value   |
   |--------------------|----------|
   |       Local        |    No    |
   | FunctionVisibility | External |
   |   ServiceEnabled   |   Yes    |


5. Open **Locals** for the function and create the following parameter:  

   | Column |                                                                 Value                                                                 |
   |-----------|---------------------------------------------------------------------------------------------------------------------------------------|
   |    Var    |                                                                  Yes                                                                  |
   |   Name    |                                                             ActionContext                                                             |
   | DataType  |                                                                DotNet                                                                 |
   |  SubType  | Microsoft.Dynamics.Nav.Runtime.WebServiceActionContext.'Microsoft.Dynamics.Nav.Ncl, Culture=neutral, PublicKeyToken=31bf3856ad364e35' |


6. Select the **Variables** tab and add the following variables.  

   |Name|DataType|SubType|
   |----|--------|-------|
   |ToSalesHeader|Record|Sales Header (ID 36)|
   |FromSalesHeader|Record|Sales Header (ID 36)|
   |SalesSetup|Record|Sales & Receivables Setup (ID 311)|
   |ODataActionManagement|Codeunit|OData Action Management (ID 6711)|
   |CopyDocMgt|Codeunit|Copy Document Mgt. (ID 6620)|
   |DocType|Option|OptionString = Quote,Blanket Order,Order,Invoice,Return Order,Credit Memo,Posted Shipment,Posted Invoice,Posted Return Receipt,Posted Credit Memo|

7. On the `Copy` function, add the code that copies the sales document, for example.

   ```
   SalesSetup.GET;
   CopyDocMgt.SetProperties(
   TRUE,FALSE,FALSE,FALSE,FALSE,SalesSetup."Exact Cost Reversing Mandatory",FALSE);

   FromSalesHeader.GET(Rec."Document Type",Rec."No.");
   ToSalesHeader."Document Type" := FromSalesHeader."Document Type";
   ToSalesHeader.INSERT(TRUE);
   CopyDocMgt.CopySalesDoc(DocType::Invoice,FromSalesHeader."No.",ToSalesHeader);

   // Add the necessary keys of the newly created entity using that entity’s backing table to identify the field no. and it’s value.
   ODataActionManagement.AddKey(Rec.FIELDNO(Id),ToSalesHeader.Id);

   // Depending on what the result was of the action
   // - Created: SetCreatedPageResponse(ActionContext, PAGE::"Sales Invoice");
   // - Updated: SetUpdatedPageResponse(ActionContext,PAGE::"Sales Invoice");
   // - Deleted: SetDeleteResponse(ActionContext);
   ODataActionManagement.SetCreatedPageResponse(ActionContext,PAGE::"Sales Invoice");
   ```
7. Save and compile the **SalesInvoice** page.

### To register and publish a page as a Web service

1.  Open [!INCLUDE[navnow](includes/navnow_md.md)] and connect to the CRONUS International Ltd. company.
2.  In the **Search** box, enter **Web services**, and then choose the related link.
3.  In the **Web Services** page, on the **Home** tab, choose **New**.
4.  In the **Object Type** column, select **Page**. In the **Object ID** column, enter `43`, and in the **Service Name** column, enter `SalesInvoice`.
5.  Select the check box in the **Published** column.
6.  Choose the **OK** button.

## Verifying the Web Service Availability 
After publishing a web service, verify that the port that web service applications will use to connect to your web service is open. The default port for OData V4 web services is 7048. You can configure this value by using the [Microsoft Dynamics NAV Server Administration Tool](https://msdn.microsoft.com/en-us/library/hh165851(v=nav.90).aspx).

### To verify availability of a Microsoft Dynamics NAV Web service action

1.  Start **Postman** or another tool that can execute a POST command against the web service URI.
2.  In the **Address** field, enter a URI in this format:
    ```
    http://<Server>:<WebServicePort>/ODataV4/Company('CRONUS%20International%20Ltd.')/SalesInvoice(<Document Type>,<No.>)/NAV.Copy
    ```
     - `<Server>` is the name of the computer that is running Microsoft Dynamics NAV Server.
    - `<WebServicePort>` is the port that OData V4 is running on. The default port is 7048.
    - `<ServiceInstance>` is the name of the Microsoft Dynamics NAV Server instance for your solution. The default name is DynamicsNAV110.
    - `<Document Type>` is document type as specified in table **36 Sales Header**. For this example, use `Invoice`.
    - `<No.>` is the value of the **No.** field of the sales invoice that you want to copy.

     For example, if the default Microsoft Dynamics NAV Server is running on your local computer, and you want to copy the invoice that has the number 103004, use the following URI:
    ```
    http://localhost:7048/DynamicsNAV110/ODataV4/Company('CRONUS%20International%20Ltd.')/SalesInvoice('Invoice', '103004')/NAV.Copy
    ```
   <!--`http://<Server>:<WebServicePort>/<ServerInstance>/api/beta/companies(<companyid>)/salesInvoices(<invoiceid>)/Microsoft.NAV.Copy)`.

    Example if the default Microsoft Dynamics NAV Server is running on your local computer:<!--
    `http://localhost:7047/DynamicsNAV/api/beta/companies(b9248a6e-966d-478c-a25d-d91d28610397)/salesInvoices(8cc52602-3aa4-4256-b2c7-fdfef5248cbf)/Microsoft.NAV.Copy)`
    -->
3. Postman should now show the Web service function that you have published, and perform the action of copying an invoice. 

## Return a value

1. Open the [!INCLUDE[nav_dev_long](includes/nav_dev_long_md.md)] and connect to the application database.
2. Open page 43, **Sales Invoice**.
3. Create a new function called **Example**.
4. Open **Properties** for the function and set the properties to the following values.  

   |      Property      |  Value   |
   |--------------------|----------|
   |       Local        |    No    |
   | FunctionVisibility | External |
   |   ServiceEnabled   |   Yes    |


5. Open **Locals** for the function, ann add the following parameter:  

   | Name | Value |
   |-----------|-------|
   |  inParam  | Text  |


6. Select the **Return Value** tab, and set the following field values.   

   |   Name   | Return Type |
   |----------|------------|
   | outParam |    Text    |


7. Add the following code on the **Example** function:  
    ```
   outParam := inParam + ' Completed';
    ```

8. You can now issue a post request on the URI to the **Example** function, for example, by using the following URI:
   ```
   http://localhost:7048/DynamicsNAV110/ODataV4/Company('CRONUS%20International%20Ltd.')/SalesInvoice('Invoice', '103004')/NAV.Example
   ```
    
   And using the following code as the JSON body:
   ```  
   {
       "inParam": "Hello World"
   }
   ```
9. The returned value will be returned in the body of the message.  
   ```
   {
       "@odata.context": "http://localhost:7048/DynamicsNAV110/ODataV4/$metadata#Edm.String",
       "value": "Hello World Completed"
   }
   ```

You have now published a [!INCLUDE[navnow](includes/navnow_md.md)] function as an OData V4 web service action and verified that the service works as expected. To read more about web services, see the **See Also** section below.

## See Also  
 [Web Services](Web-Services.md)  
 [SOAP Web Services](SOAP-Web-Services.md)  
 [Microsoft Dynamics NAV Web Services Overview](Microsoft-Dynamics-NAV-Web-Services-Overview.md)  
 [How to: Publish a Web Service](How-to--Publish-a-Web-Service.md)  
 [Walkthrough: Configuring Web Services to Use SSL (SOAP and OData)](Walkthrough--Configuring-Web-Services-to-Use-SSL--SOAP-and-OData-.md)  
 [Web Service Alternatives: SOAP and OData](Web-Service-Alternatives:-SOAP-and-OData.md)