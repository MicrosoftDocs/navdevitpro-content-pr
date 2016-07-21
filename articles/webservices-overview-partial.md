<properties
                pageTitle="Microsoft Dynamics NAV Web Services Overview | Dynamics NAV"
                description="Provides a general introduction to web services in Dynamics NAV."
                services=""
                documentationCenter=""
                authors="edupont04"/>
<tags
    ms.prod="dynamics-nav-2017"
    ms.topic="article"
    ms.devlang="na"
    ms.tgt_pltfrm="na"
    ms.workload="na"
    ms.date="07/21/2016"
    ms.author="edupont04" />

# Microsoft Dynamics NAV Web Services Overview
<!-- This topic represents changes to a topic that is pending migration from CAPS -->
## Web Services and Regional Settings  
Data is formatted according to the value of the **Services Language** setting for the relevant [!INCLUDE[nav_server](../Token/nav_server_md.md)] instance. The default value is *en\-us*. This means that [!INCLUDE[nav_server](../Token/nav_server_md.md)] interprets all incoming data as the specified culture, such as dates and amounts.  

 <!--Add this section:-->
 Similarly, you can use the **ServicesOptionFormat** setting to specify how [!INCLUDE[nav_server](../Token/nav_server_md.md)] must understand option values. If you set the **ServicesOptionFormat** setting to *OptionString*, [!INCLUDE[nav_server](../Token/nav_server_md.md)] understand option values as the *name* of the option value, which is always en\-us. If you set the setting to *OptionCaption*, web service data will be interpreted in the language specified by the **Services Language** setting.  

<!-- existing section-->
If you know that the **Services Language** setting is always en\-us, for example, your code can be based on that assumption. In a multilanguage environment, you will see more predictable transformations of data if data that is transmitted through web services is in a consistent culture.  

<!-- Delete this section!
 However, you can choose to use the culture that is specified in the regional settings for the user who reads the data. To enforce this, add the following entry to the CustomSettings.config file for the relevant [!INCLUDE[nav_server](../Token/nav_server_md.md)] instances:  

```  
<add key="ServicesCultureDefaultUserPersonalization" value="true"/>  
```  

 If you set this key to true, web services override the **Services Language** setting and look up the [\($ T\_2000000073\_12 Language ID $\)](../Topic/\($%20T_2000000073_12%20Language%20ID%20$\).md) for the current user in the **\($ T\_2000000073 User Personalization $\)** table.-->
