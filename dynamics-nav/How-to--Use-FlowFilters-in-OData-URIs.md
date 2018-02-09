---
title: "How to: Use FlowFilters in OData URIs"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 53086760-566b-4bc9-97d4-e3ac74f0b818
caps.latest.revision: 13
manager: edupont
---
# How to: Use FlowFilters in OData URIs
You can set FlowFilters on the data that your OData web service extracts from the [!INCLUDE[navnow](includes/navnow_md.md)] database.  
  
 FlowFilters are a special kind of filter that you use to set ranges on calculations that are shown in FlowFields. For more information, see [FlowFilter Overview](FlowFilter-Overview.md). FlowFilters for a page are included in the metadata for that page when it is published as a web service. You can then use FlowFilters as filters in a URI that specifies a query against page data. However, only those FlowFilters that are required to calculate the FlowFields that are exposed on the page as controls are included.  
  
## Using FlowFilters to Query Data on the Item Card Page  
 In this procedure, you create and publish a web service from the **Item Card** page in [!INCLUDE[navnow](includes/navnow_md.md)] and then query the data in that web service by using a FlowFilter.  
  
#### To query data on the Item Card page using a FlowFilter  
  
1.  Register and publish a page web service by using the [!INCLUDE[rtc](includes/rtc_md.md)] as described in [Walkthrough: Creating and Interacting with a Page Web Service \(OData\)](Walkthrough--Creating-and-Interacting-with-a-Page-Web-Service--OData-.md). Register and publish page 30, Item Card, and name the service **ItemCard**.  
  
2.  Start Windows Internet Explorer, and then in the **Address** field, enter a URI in this format:  
  
    ```  
    http://<Server>:<WebServicePort>/<ServerInstance>/OData/$metadata  
    ```  
  
     If [!INCLUDE[nav_server](includes/nav_server_md.md)] is running on the local computer and uses the default [!INCLUDE[nav_server](includes/nav_server_md.md)] instance and the default OData port, then the address is:  
  
    ```  
    http://localhost:7048/DynamicsNAV/OData/$metadata  
    ```  
  
3.  Examine the metadata that is returned by this URI. At the end of the list is a set of parameters that end in the word `Filter`. This is the list of FlowFilters for the page:  
  
    ```  
    <Property Type="Edm.String" Name="Location_Filter" Nullable="true"/>  
    <Property Type="Edm.String" Name="Drop_Shipment_Filter" Nullable="true"/>  
    <Property Type="Edm.String" Name="Variant_Filter" Nullable="true"/>  
    <Property Type="Edm.String" Name="Lot_No_Filter" Nullable="true"/>  
    <Property Type="Edm.String" Name="Serial_No_Filter" Nullable="true"/>  
    <Property Type="Edm.String" Name="Date_Filter" Nullable="true"/>  
    ```  
  
    > [!NOTE]  
    >  The set of FlowFilters that is listed in the page metadata may not match the set of FlowFilters on the equivalent page in the [!INCLUDE[rtc](includes/rtc_md.md)]. This is because the [!INCLUDE[rtc](includes/rtc_md.md)] shows all FlowFilter fields that are defined on the table on which the page is based. The metadata only shows the FlowFilters that are used to calculate the FlowField controls that are exposed on the page.  
  
4.  Create a URI that returns information for a single item card. For example:  
  
    ```  
    http://localhost:7048/DynamicsNAV/OData/Company('CRONUS-International-Ltd.')/ItemCard('1906-S')  
    ```  
  
     This is the "ATHENS Mobile Pedestal" item. The value for the *Qty\_on\_Sales\_Order* parameter is 33:  
  
    ```  
    <d:Qty_on_Sales_Order m:type="Edm.Decimal">33</d:Qty_on_Sales_Order>  
    ```  
  
5.  Apply a FlowFilter to that item and specify **GREEN** as the value for the **Location\_Filter**:  
  
    ```  
    http://localhost:7048/DynamicsNAV/OData/Company('CRONUS-International-Ltd.')/ItemCard('1906-S')?$filter=Location_Filter eq 'GREEN'  
    ```  
  
     The item is returned as before, the value of the FlowField that has changed. The value for the *Qty\_on\_Sales\_Order* parameter is now 27:  
  
    ```  
    <d:Qty_on_Sales_Order m:type="Edm.Decimal">27</d:Qty_on_Sales_Order>  
    ```  
  
     This indicates that there are 27 ATHENS Mobile Pedestals on sales orders designated for the GREEN location.  
  
## See Also  
 [OData Web Services](OData-Web-Services.md)