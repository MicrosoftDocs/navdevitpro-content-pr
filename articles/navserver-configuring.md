<properties
                pageTitle="Using the Development Environment from the Command Prompt" | Project “Madeira”"
                description="Describes the how to use finsql.exe,"
                services=""
                documentationCenter="Madeira"
                authors="jswymer"/>


<!-- The content in this article supports Madeira deliverables 169219, which adds a new parameter (showalldesignercolumns) to the finsql.exe. The content should be added to the Using the Development Environment from the Command Prompt article as described.-->

<!-- Change 1: In the section "Configuring Microsoft Dynamics NAV Server After Installation" section, in the last bullet, update the path CustomSetting.config file as follows:-->

 By default, this file is located in C:\Program Files\Microsoft Dynamics NAV\91\Service\Instances\<instancename>



<!-- Change 2: Add the following section In the "Parameters" section, add a row for the "showalldesignercolumns" parameter as follows:-->
## Task Scheduler Tab Settings
The following table describes fields on the **Task Scheduler** tab in the Microsoft Dynamics NAV Server Administration tool.

|  Setting  |  Description  |
|-----------|---------------|  
|  Enable Save as Excel on Request Pages of RDLC-layout Reports  |  Specifies whether the Microsoft Dynamics NAV Server instance starts with the task scheduler enabled. The task scheduler processes jobs and other processes on a scheduled basis.

If this option is enabled, the server instance will process scheduled tasks. |
|  Enable Save as Word on Request Pages of RDLC-layout Reports  |  Specifies whether users can open or save a report as a Microsoft Word document if the report uses an RDLC layout. If you clear this check box, the **Word** option is removed from the **Print** menu on the request page.|
|  Enable Save from Report Preview  |  Specifies whether users can save a report as a PDF, Microsoft Word, or Microsoft Excel document from the report preview window. If you clear this check box, the **Save As** icon is removed from the report preview window.  |
| Report PDF Font Embedding  |  Specifies whether fonts are embedded in PDF files that are generated for reports when the report uses an RDLC report layout at runtime. This setting applies when reports are run and saved as PDF files on the Dynamics NAV client (from the report request page or print preview window) or on the Dynamics NAV Server instance (by the [SAVEAS function](function-reportsaveas.md) or [SAVEASPDF function](function-reportsaveaspdf.md) in C/AL code).<br/><br/> **Note:** This setting does not apply when a report uses a Word report layout at runtime.<br/><br/>Embedding fonts in a PDF of a report makes sure that the PDF will use the same fonts as the original file, regardless of where the PDF is opened and which fonts are installed on the computer. However, embedding fonts can significantly increase the size of the PDF files. By disabling font embedding, you can decrease the size of the report PDF files.<br/><br/>**Note:** This is a global setting for font embedding in report PDF files. You can override this setting on a report basis by the specifying the [PDFFontEmbedding property](property-reportpdffontembedding.md).<br/><br/>Default: Not enabled|
## Reports Tab Settings
The following table describes fields on the **Reports** tab in the Microsoft Dynamics NAV Server Administration tool.

|  Setting  |  Description  |
|-----------|---------------|  
|  Enable Save as Excel on Request Pages of RDLC-layout Reports  |  Specifies whether users can open or save a report as an Microsoft Excel document if the report uses an RDLC layout. If you clear this check box, the **Excel** option is removed from the **Print** menu on the request page.  |
|  Enable Save as Word on Request Pages of RDLC-layout Reports  |  Specifies whether users can open or save a report as a Microsoft Word document if the report uses an RDLC layout. If you clear this check box, the **Word** option is removed from the **Print** menu on the request page.|
|  Enable Save from Report Preview  |  Specifies whether users can save a report as a PDF, Microsoft Word, or Microsoft Excel document from the report preview window. If you clear this check box, the **Save As** icon is removed from the report preview window.  |
| Report PDF Font Embedding  |  Specifies whether fonts are embedded in PDF files that are generated for reports when the report uses an RDLC report layout at runtime. This setting applies when reports are run and saved as PDF files on the Dynamics NAV client (from the report request page or print preview window) or on the Dynamics NAV Server instance (by the [SAVEAS function](function-reportsaveas.md) or [SAVEASPDF function](function-reportsaveaspdf.md) in C/AL code).<br/><br/> **Note:** This setting does not apply when a report uses a Word report layout at runtime.<br/><br/>Embedding fonts in a PDF of a report makes sure that the PDF will use the same fonts as the original file, regardless of where the PDF is opened and which fonts are installed on the computer. However, embedding fonts can significantly increase the size of the PDF files. By disabling font embedding, you can decrease the size of the report PDF files.<br/><br/>**Note:** This is a global setting for font embedding in report PDF files. You can override this setting on a report basis by the specifying the [PDFFontEmbedding property](property-reportpdffontembedding.md).<br/><br/>Default: Not enabled|

<!-- Change 3: Move the Max Data Rows Allowed to Send to Excel row
MinAdd the following section In the "Parameters" section, add a row for the "showalldesignercolumns" parameter as follows:-->
