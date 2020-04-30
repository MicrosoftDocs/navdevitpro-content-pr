---
title: "How to: Enable Web Services for ADCS"
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 5f81cec5-34bc-4530-b1b3-6ae99b9d31ae
caps.latest.revision: 14
manager: edupont
---
# How to: Enable Web Services for ADCS
To use Automated Data Capture System, you must enable the ADCS web service.  

### To enable and publish the ADCS web service  

1.  Start the [!INCLUDE[rtc](includes/rtc_md.md)].  

2.  In the **Search** box, enter **Web Services**, and then choose the related link.  

3.  On the **Home** tab, choose **New**.  

4.  In the **Web Services** window, enter the following information on a new line:  

    |[!INCLUDE[bp_tablefield](includes/bp_tablefield_md.md)]|Value|  
    |---------------------------------|-----------|  
    |**Object Type**|Codeunit|  
    |**Object ID**|7714|  
    |**Service Name**|ADCS **Important:**  It is required that you name the service **ADCS**.|  

5.  Select the **Published** check box.  

6.  Choose the **OK** button.  

### To verify that the web service has been published  

1.  In a web browser window, enter a URL in the following format:  **https://\<web services path>/Services**. The following example demonstrates the results.  

    ```  
    https://localhost:7047/nav_server_instance/WS/Services  
    ```  

     You see the following XML information if the ADCS web service is published.  

    ```  
    <contractRef xmlns="https://schemas.xmlsoap.org/disco/scl/" ref="https://localhost:7047/nav_server_instance/WS/Codeunit/ADCS"/>  
    ```  

2.  To verify that the codeunit is performing as expected, enter a URL in the following format: **https://\<web services path>/Codeunit/\<Service Name>**.  

    ```  
    https://localhost:7047/nav_server_instance/WS/Codeunit/ADCS  
    ```  

     Information about the ADCS web service is displayed.  

## See Also  
 [Configuring Automated Data Capture System](Configuring-Automated-Data-Capture-System.md)   
 [How to: Configure ADCS Options](How-to--Configure-ADCS-Options.md)   
 [SOAP Web Services](SOAP-Web-Services.md)
