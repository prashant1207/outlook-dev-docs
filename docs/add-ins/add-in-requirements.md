---
title: Outlook Add-in requirements | Microsoft Docs
description: Learn about the client and server requirements to use Outlook Add-ins.
author: jasonjoh
ms.topic: article
ms.technology: office-add-ins
ms.date: 08/08/2017
ms.author: jasonjoh
---

# Outlook Add-in requirements

For Outlook Add-ins to load and function properly, there are a number of requirements for both the servers and the clients. 

## Client requirements

- The client must be one of the supported hosts for Outlook Add-ins. The following clients support add-ins:

   - Outlook 2013 and 2016 for Windows
   - Outlook 2016 for Mac
   - Outlook for iOS
   - Outlook on the web for Exchange 2016 and Office 365
   - Outlook Web Access for Exchange 2013
   - Outlook.com

- The client must be connected to an Exchange server or Office 365 using a direct connection. When configuring the client, the user must choose an **Exchange**, **Office 365**, or **Outlook.com** account type. If the client is configured to connect with POP3 or IMAP, add-ins will not load.

## Mail server requirements

If the user is connected to Office 365 or Outlook.com, mail server requirements are all taken care of already. However, for users connected to on-premises installations of Exchange Server, the following requirements apply.

- The server must be Exchange 2013 or later.
- Exchange Web Services (EWS) must be enabled and must be exposed to the Internet. Many add-ins require EWS to function properly.
- The server must have a valid authentication certificate in order for the server to issue valid identity tokens. New installations of Exchange Server include a default authentication certificate. For more information, see [Digital certificates and encryption in Exchange 2016](https://technet.microsoft.com/en-us/library/dd351044(v=exchg.160).aspx) and [Set-AuthConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/organization/Set-AuthConfig?view=exchange-ps).
- To access add-ins from the [Office Store](https://appsource.microsoft.com/en-us/marketplace/apps?product=office&page=1&src=office&corrid=a35323d5-0e3d-4cc0-ba44-57537d74aae8&omexanonuid=581941df-1c6f-4eda-89e7-651af8aeaeb2), the client access servers must be able to communicate with AppSource. 

## Add-in server requirements

Add-in files (HTML, JavaScript, etc.) can be hosted on any web server platform desired. The only requirement is that the server must be configured to use HTTPS, and the SSL certificate must be trusted by the client.