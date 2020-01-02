---
title: "Walkthrough: Creating and Interacting with a Page Web Service (OData)"
ms.custom: na
ms.date: 10/08/2019
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 72563698-e7ea-44d1-b351-6f2984b70409
caps.latest.revision: 19
author: jswymer
---
# Walkthrough: Creating and Interacting with a Page Web Service (OData)

This walkthrough illustrates how you can publish a [!INCLUDE[navnow](includes/navnow_md.md)] page as an OData V3 web service, use it in a Visual Studio console application, and change data in [!INCLUDE[navnow](includes/navnow_md.md)] through the web service.  
  
## About This Walkthrough
  
This walkthrough provides an overview of how to expose a page as a web service and how to use the web service in a C\# console application. The walkthrough illustrates the following tasks:  
  
- Publishing a [!INCLUDE[navnow](includes/navnow_md.md)] page as a web service.  
  
- Verifying web service availability from a browser.  
  
- Adding the published web service as a service reference in a console application that you create in Visual Studio.
  
- Changing the data in the console application.  
  
### Prerequisites
  
 To complete this walkthrough, you will need:  
  
- [!INCLUDE[navnowlong](includes/navnowlong_md.md)] with a developer license.  
  
- [!INCLUDE[demolong](includes/demolong_md.md)].  

- ODate Services and V3 Endpoint enabled on the [!INCLUDE[nav_server](includes/nav_server_md.md)]. 
  
- Visual Studio 2015 or later.

    You can use any edition of Visual Studio that supports adding web references. In this walkthrough, you will use Visual Studio 2017. You also have the option to use service references instead of web references, or use the web service proxy generating tools svcutil.exe and wsdl.exe, which are included in the Microsoft .NET Framework SDK.  

- OData Connected Service installed in Visual Studio.

    This tool generates code to facilitate the consumption of OData services. To install OData Connected Service you can either download it from [OData Connected Service](https://marketplace.visualstudio.com/items?itemName=laylaliu.ODataConnectedService) and follow the instructions, or do the following in Visual Studio:

    1. On the **Tools** menu, select **Extensions and Updates** > **Online**
    2. Search for **OData Connected Service**, select it in the results, and choose **Download**.
    3. Close Visual Studio to start the installation.

## Publishing a Page as a Web Service
  
You publish a web service by using the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or the [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
1. Open the client and connect to the [!INCLUDE[demoname](includes/demoname_md.md)] company.  
  
2. In the **Search** box, enter **Web services**, and then choose the related link.  
  
3. In the **Web Services** page, choose **New**.  
  
4. In the **Object Type** column, select **Page**. In the **Object ID** column, enter **21**, and in the **Service Name** column, enter **Customer**.  
  
5. Select the check box in the **Published** column.  
  
6. Choose the **OK** button.  
  
## Verifying Web Service Availability  
  
After publishing a web service, verify that the port that web service applications will use to connect to your web service is open. The default port for OData web services is 7048. You can configure this value by using the [Microsoft Dynamics NAV Server Administration Tool](Microsoft-Dynamics-NAV-Server-Administration-Tool.md).  

1. Start an Internet browser.  
  
2. In the **Address** field, enter the Dynamics NAV OData endpoint.

    The endpoint has the format: `https://<Server>:<WebServicePort>/<ServerInstance>/OData`. For example:
  
    `https://localhost:7048/DynamicsNAV/OData`  
  
   - `Server` is the name of the computer that is running [!INCLUDE[nav_server](includes/nav_server_md.md)].  
  
   - `WebServicePort` is the port that OData is running on. The default port is 7048.  
  
   - `ServiceInstance` is the name of the [!INCLUDE[nav_server](includes/nav_server_md.md)] instance for your solution. The default name is [!INCLUDE[nav_server_instance](includes/nav_server_instance_md.md)].  
  
      The browser should show the web services that you have published, including the `Customer`, in a format of an AtomPub document:

      ![Basic AtomPub document for a page](media/BasAtomPub.JPG "BasAtomPub") 
  <!--
    `{"@odata.context":"https://navdevvm-0399:7048/DynamicsNAV110/ODataV4/$metadata","value":[{"name":"Customer","kind":"EntitySet","url":"Customer"},...`

 -->
  
##  <a name="BKMK_CreateConsoleApp"></a> Creating the Console Application

Next, you create a C\# console application in Visual Studio. The console app will return a list of customers from [!INCLUDE[navnow](includes/navnow_md.md)] and create a new customer.

### Create the C\# project
  
1. In Visual Studio, on the **File** menu, point to **New**, and then choose **Project**.  
2. In the pane on the left, select **Installed** > **Visual C\#** > **Windows (Classic) Desktop** > **Console App (.NET Framework)**.
3. Set the **Name** and **Solution Name** for the application to **Customers** , and choose  **OK** to exit the **New Project** page.
<!--   
### Add a Service Reference for your OData Web service (Visual Studio 2015 and earlier)
1. In the Solution Explorer pane, right-click **References**, and then choose **Add Service Reference**.  
  
2. In the **Address** field, enter the URI for your OData web service, such as **https://localhost:7048/DynamicsNAV/OData/**.  
  
   > [!IMPORTANT]  
   >  In this example, we use the HTTP protocol to illustrate the use of OData web services. We recommend that you use the more secure HTTPS protocol when you consume web services.  
  
3. Choose **Go**, and then, in the **Services** field, choose **NAV**, and then choose the **OK** button.  
  
   The project is created, and your OData web service is added as a service reference. Next, you add the code that will show a list of existing customers, add a customer and then rename the new customer.  -->

### Add a connected service for the OData web service

1. In the Solution Explorer pane, right-click the **Customers** project, and then choose **Add** > **Connected Service**.
2. On the **Configure Endpoint** page, you can keep the **Service name** of **OData Service** or change it as you like.
3. In the **Address** field, enter the endpoint URI for your OData web service.

    This is the endpoint that you verified in an earlier step. The endpoint has the format `https://<servercomputer>:<odataport>/<serverinstance>/OData/`, for example:

    `https://localhost:7048/DynamicNAV/OData/`
  
   > [!IMPORTANT]  
   >  In this example, we use the HTTP protocol to illustrate the use of OData web services. We recommend that you use the more secure HTTPS protocol when you consume web services.
  
4. Choose **Next**.
5. On the **Settings** page, you can keep the file name **Reference** or change it as you like.
  
   The project is created, and your OData web service is added as a connected service reference. Next, you add the code that will show a list of existing customers, add a customer and then rename the new customer.  
  
<!--
### Install and reference the Simple.OData.Client library

The Simple.OData.Client is a multi-platform OData client library that provides an alternative to the WCF Data Services Client library. It is available as a NuGet package for Visual Studio. For more information, see [Simple.OData.Client](https://github.com/simple-odata-client/Simple.OData.Client/wiki).

1. Select **Tools** > **NuGet Package Manager** > **Package Manager Console**.
2. At the `PM>` prompt, enter the the following command:

    ```
    Install-Package Simple.OData.Client
    ```

3. When the installation has finished, the console application project (Customers) should include a references to: Simple.OData.Client.Core, Simple.OData.Client.Dynamics, Simple.OData.Client.V3.Adapter, and Simple.OData.Client.V4.Adapter. If not, add the manually.
-->
### Add code to the console application 

1. In the program.cs file of your solution, add the `using` statement after the namespaces that are automatically added to your project:  
  
    ```  
    using NAV;  
    ```

2. After the `Main` method, add the following method to return a list of customers whose name start with `Cust`:  
  
    ```  
    private static void PrintCustomersCalledCust(NAV.NAV nav)  
      {  
        var customers = from c in nav.Customer  
                        where c.Name.StartsWith("Cust")  
                        select c;  
  
        Boolean customerFound = false;  
        foreach (Customer customer in customers)  
        {  
          customerFound = true;  
          Console.WriteLine("No.: {0} Name: {1}", customer.No, customer.Name);  
        }  
  
        if (!customerFound)  
        {  
          Console.WriteLine("There are no customers that start with 'Cust'.");  
        }  
      }  
  
    ```  
  
    The `PrintCustomersCalledCust` method reads the OData web service that you created, Customer, and creates a list of customers where the customer name begins with the letters **Cust**. Next, you add code to the Main method that uses the web service to write to [!INCLUDE[navnow](includes/navnow_md.md)].  

3. In the `Main` method, add the following code to establish the connection to [!INCLUDE[navnow](includes/navnow_md.md)] through the OData web service:  

    ```  
    NAV.NAV nav = new NAV.NAV(new Uri("https://localhost:7048/DynamicsNAV/OData/Company('CRONUS%20International%20Ltd.')"));
    nav.Credentials = System.Net.CredentialCache.DefaultNetworkCredentials; 
    ```  

    This implementation will authenticate users on their Windows credentials.

    In the example, the name of the [!INCLUDE[navnow](includes/navnow_md.md)] company that you modify data for is [!INCLUDE[demoname](includes/demoname_md.md)]. You must replace this with the name of the company that you have access to. To find the correct URI, you can paste the following URI into your browser and then see the exact URI that you must use: `https://localhost:7048/DynamicsNAV/OData/Company`.  

  
<!-- OData V4 
    ```
    ODataClientSettings settings = new ODataClientSettings(new Uri("https://navdevvm-0399:7048/DynamicsNAV/OData/"), System.Net.CredentialCache.DefaultNetworkCredentials); 
    ```
-->
  

<!-- ODataV4 example using Simple.Odata.Client
```
    // Connects to Dynamics NAV through the OData web service, using the user's Windows credentials. Replace https://localhost:7048/DynamicsNAV/ODataV4 with your endpoint.  
    ODataClientSettings settings = new ODataClientSettings(new Uri("https://localhost:7048/DynamicsNAV/ODataV4"), System.Net.CredentialCache.DefaultNetworkCredentials);

    var client = new ODataClient(settings);

    // Lists customers
    {
        var x = ODataDynamic.Expression;
        IEnumerable<dynamic> customers = client
            .For(x.Company)
            .Key("CRONUS International Ltd.")
            .NavigateTo(x.Customer)
            .FindEntriesAsync().Result;

        foreach (var customer in customers)
        {
            Console.WriteLine("No.: {0} Name: {1}", customer.No, customer.Name);
        }
    }

    // Creates customer
    {
        var x = ODataDynamic.Expression;
        dynamic newCustomer = client
            .For(x.Company)
            .Key("CRONUS International Ltd.")
            .NavigateTo(x.Customer)
            .Set(new { No = "99989", Name = "Torben" })
            .InsertEntryAsync().Result;

        Console.WriteLine("Added Customer-> No.: {0} Name: {1}", newCustomer.No, newCustomer.Name);
    }

    ```
-->
4. Add the following code to the method:

    ```  
    Console.WriteLine("Printing list of current customers:");  
    PrintCustomersCalledCust(nav);  
  
    Console.WriteLine("Adding new customer.");  
    Customer newCustomer = new Customer();  
    newCustomer.Name = "Customer Name";  
    nav.AddToCustomer(newCustomer);  
    nav.SaveChanges();  
  
    Console.WriteLine("Printing list of current customers:");  
    PrintCustomersCalledCust(nav);  
  
    newCustomer.Name += "Changed";  
    nav.UpdateObject(newCustomer);  
    nav.SaveChanges();  
  
    Console.WriteLine("Printing list of current customers:");  
    PrintCustomersCalledCust(nav);  
    ```
 
    In this code, the customer is created and then renamed. The code prints a list of the customers that currently exist in the **Customer** table when each change has been made.

5. Build and run the project.  
  
### To verify the inserted and modified data in [!INCLUDE[navnow](includes/navnow_md.md)]  
  
1. Open the [!INCLUDE[nav_windows](includes/nav_windows_md.md)] or the [!INCLUDE[nav_web](includes/nav_web_md.md)].  
  
2. Open the list of customers, filter for a customer with the name **Customer NameChanged**.  
  
     This is the customer that the console application created.  
  
## Next Steps

You have built a console application that uses an OData web service to modify [!INCLUDE[navnow](includes/navnow_md.md)] data. You can use similar OData web services in other applications when you want to allow users to modify data outside [!INCLUDE[navnow](includes/navnow_md.md)].  
  
## See Also  
 [Microsoft Dynamics NAV Web Services Overview](Microsoft-Dynamics-NAV-Web-Services-Overview.md)   
 [Using OData Web Services to Modify Data](Using-OData-Web-Services-to-Modify-Data.md)   
 [Web Service Walkthroughs](Web-Service-Walkthroughs.md)   
 [Walkthrough: Registering and Using a Page Web Service \(SOAP\)](Walkthrough--Registering-and-Using-a-Page-Web-Service--SOAP-.md)   
 [Web Service Alternatives: SOAP and OData](Web-Service-Alternatives:-SOAP-and-OData.md)