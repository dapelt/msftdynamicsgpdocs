---
title: "Prerequisites for Dynamics GP"
description: "See the specifications of minimum hardware and software requirements to install and run Dynamics GP."
keywords: "requirements"
author: edupont04
ms.author: edupont
manager: annbe
applies_to: 
ms.date: 08/23/2018
ms.prod: dynamics-gp
ms.topic: article
ms.assetid: d8d8b73c-60f6-46f4-bb8c-436e94c01501
ms.reviewer: edupont
---
# System requirements

This chapter contains a list of the prerequisites for Dynamics GP, as well as the disk space requirements for SQL Server.

## Prerequisites

The following components also must be installed before you can install Dynamics GP.

- Microsoft Windows Installer 4.5

- Microsoft .NET Framework 3.5

- Microsoft .NET Framework 4.6

- Visual C++ 2015 Runtime Libraries (x64)

- Visual C++ 2015 Runtime Libraries (x86)

- Visual Basic for Applications Core (this redist is no longer supportedl it's offered as-is)

- Microsoft SQL Server Native Client 10.0

- Dexterity Shared Components 18.0

- Microsoft Application Error Reporting 11.0

- Open XML SDK 2.0 for Microsoft Office

- Microsoft Lync 2010 SDK Runtime

If one of these components isn’t installed on your computer when you attempt to install Dynamics GP using the installation media, the Dynamics GP Bootstrapper Setup window opens. This window shows which components need to be installed. Click Install to install the missing component or components. After all the components are installed, the installation of Dynamics GP continues.

## Home page prerequisites

To display metrics and reports in the Business Analyzer area on your home page, install and set up Microsoft SQL Server 2012 Reporting Services or SQL Server 2014 Reporting Services to use with Dynamics GP. For more information about installing and setting up Reporting Services for use with Dynamics GP, go to the [Dynamics GP documentation resource website](https://go.microsoft.com/fwlink/?LinkId=249465) for the most current documentation.

## Word templates prerequisites

Predefined Word templates for document types such as sales quotes and purchase orders are provided for you with Dynamics GP. The templates are based on standard reports in Dynamics GP. You also can create your own template or create a template from an existing template.

The following components are required to modify templates.

- Microsoft Word 2013 or later to make layout changes such changing the font size

- Dynamics GP Add-in for Microsoft Word to add fields and data sources to the template

- Visual Studio Tools for Office Runtime 2.0 or later—Visual Studio Tools for Office Runtime 3.0 is installed with Dynamics GP Add-in for Microsoft Word

You can install Dynamics GP Add-in for Microsoft Word from the Dynamics GP installation media. Double-click the Setup.exe file and then click Dynamics GP Add-in for Microsoft Word.

Be sure that the Open XML SDK 2.0 for Microsoft Office (installed as a Dynamics GP prerequisite) is installed before you use Word Templates for Dynamics GP.

## Email requirements

By using the email functionality in Dynamics GP, you can embed documents into the body of the email or send documents as attachments. You can send a single document, batches of documents, or send multiple documents from sales and purchasing transaction lists. When setting up the email functionality, you can select which documents you can send and which customers and vendors should receive their documents in email. If you are using Word templates for Dynamics GP, you can send predefined or customized forms.

Review the following requirements.

- You can send documents by email if you’re using a MAPI-compliant e-mail service or Exchange 2007 Service Pack 1 or greater with Exchange Web Services.

- If you are using Exchange 2007 Service Pack 1 or greater with Exchange Web Services, the Autodiscover service must be enabled to connect to the Exchange server.

- The email functionality in Dynamics GP supports the following document types. Depending on the document type and the email service, Microsoft Word 2013 or later and Word templates for Dynamics GP are required.

| File format | Word         | Word templates | Web Client    |
|-------------|-------------------|----------------|---------------|
| XPS         | Required for MAPI | Enabled        | Not available |
| PDF         | Required for MAPI | Enabled        | Not available |
| DOCX        | Not required      | Enabled        | Available\*   |
| HTML        | Not required      | Not required   | Available\*   |

\*E-mail for Dynamics GP Web Client will only be available if Exchange is your server type in the System Preferences window.

- Before you can send documents as DOCX, PDF, or XPS attachments, the Word template for the document must be enabled in the Template Configuration Manager window.

- The email functionality is supported on the 32-bit edition of Microsoft Office.

- The email functionality is supported on the 64-bit edition of Microsoft Office if you are using Exchange 2007 Service Pack 1 or greater with Exchange Web Services and Exchange is your server type in the System Preferences window.

Depending on the file format you choose to send your documents in email, your customers and vendors must be using the following components to view their documents.

| File format   | Component                    |
|----------------|------------------------------|
| XPS       | Microsoft XPS Viewer         |
| PDF           | Adobe Reader                 |
| DOCX          | Microsoft Word Viewer        |
| HTML\*          | Internet Explorer 8 or later |
| If you are using Dynamics GP Web Client only, your customers and vendors must be using HTML to view their documents. |

## SQL Server Reporting Services requirements

Before you deploy Dynamics GP Reporting Services reports, you must install and configure SQL Server Reporting Services, and then set up security for SQL Server Reporting Services reports.

## Modify the Report Server web.config file

To deploy the SQL Server Reporting Services reports, you must modify the Report Server web.config file for the timeout execution and the maximum request length. If you don’t update the Report Server web.config file for the timeout execution, you might receive an error that states that the operation has timed out. If you don’t update the Report Server web.config file for the maximum request length, you will receive an error that the deployment has exceeded the maximum request length allowed by the target server.

> [!NOTE]
> You must be an administrator to modify the Report Server web.config file.  

To modify the Report Server Web.config file:

1. Create a backup copy of the web.config file located in the ReportServer folder. (The ReportServer folder is located in C:\\Program Files\\Microsoft SQL Server\\MS SQL SERVER\\Reporting Services\\Report Server where Reporting Services is installed.)

2. Open the Report Server web.config file using a text editor, such as Notepad.

3. Search for &lt;httpRuntime executionTimeout="9000" /&gt;.

4. In that line, change executionTimeout=”9000” to executionTimeout=”19000” and add the value maxRequestLength="20960".

    (&lt;httpRuntime executionTimeout="19000" maxRequestLength="20960"/&gt;

5. Save and close the Report Server web.config file.

## Dynamics GP CRM requirements

You must be using SQL Server 2012 R2 Reporting Services or SQL Server 2014 Reporting Services and Microsoft Dynamics CRM 2011 or later to deploy SQL Server Reporting Services reports and metrics that include CRM data. Microsoft Dynamics CRM supports only the native mode of deployment of SQL Server Reporting Services.

You must install the Microsoft Dynamics CRM Reporting Extensions on the Dynamics GP report server to render reports. Before you render a SQL Server Reporting Services report with CRM data, be sure to start the Microsoft Dynamics CRM application to initialize data.

## Supported system requirements

For detailed system requirements for Dynamics GP, see [System requirements for Dynamics GP 2016](https://go.microsoft.com/fwlink/?LinkId=521785). The system requirements include supported databases and operating systems, hardware recommendations, client requirements, and Terminal Server requirements.

Recommended system requirements depend on the number of users and transactions. If there will be many users performing concurrent tasks, such as depreciation, posting, or heavy reporting, enhancing your hardware and system software improves performance.

## About remote access

You can use Windows Server 2012 Terminal Services, Windows Server 2012 R2 Remote Desktop Services, and Windows Server 2012 Remote Desktop Services. Citrix Xenapps can also be used with most database configurations to provide remote access to Dynamics GP in a Wide Area Network (WAN) environment.

For more information about system requirements see <https://go.microsoft.com/fwlink/?LinkId=521785>. You also should refer to the documentation provided by Citrix for more information.
