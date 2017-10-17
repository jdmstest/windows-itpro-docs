---
title: Windows Defender ATP data storage and privacy
description: Learn about how Windows Defender ATP handles privacy and data that it collects.
keywords: Windows Defender ATP data storage and privacy, storage, privacy
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: high
ms.date: 09/05/2017
---

# Windows Defender ATP data storage and privacy

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

This section covers some of the most frequently asked questions regarding privacy and data handling for Windows Defender ATP.
> [!NOTE]
> This document explains the data storage and privacy details related to Windows Defender ATP. For more information related to Windows Defender ATP and other products and services like Windows Defender and Windows 10, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576). See also [Windows 10 privacy FAQ](https://go.microsoft.com/fwlink/?linkid=827577) for more information.

## What data does Windows Defender ATP collect?

Microsoft will collect and store information from your configured endpoints in a database specific to the service for administration, tracking, and reporting purposes.

Information collected includes code file data (such as file names, sizes, and hashes), process data (running processes, hashes), registry data, network connection data (host IPs and ports), and machine details (such as GUIDs, names, and the operating system version).

Microsoft stores this data securely in Microsoft Azure and maintains it in accordance with Microsoft privacy practices and [Microsoft Trust Center policies](https://go.microsoft.com/fwlink/?linkid=827578).

Microsoft uses this data to:
- Proactively identify indicators of attack (IOAs) in your organization
- Generate alerts if a possible attack was detected
- Provide your security operations with a view into machines, files, and URLs related to threat signals from your network, enabling you to investigate and explore the presence of security threats on the network.

Microsoft does not mine your data for advertising or for any other purpose other than providing you the service.

## Do I have the flexibility to select where to store my data?

When onboarding the service for the first time, you can choose to store your data in Microsoft Azure datacenters in Europe or United States. Once configured, you cannot change the location where your data is stored. This provides a convenient way to minimize compliance risk by actively selecting the geographic locations where your data will reside. Microsoft will not transfer the data from the specified geolocation.

## Is my data isolated from other customer data?
Yes, your data is isolated through access authentication and logical segregation based on customer identifier. Each customer can only access data collected from its own organization and generic data that Microsoft provides.

## How does Microsoft prevent malicious insider activities and abuse of high privilege roles?

Microsoft developers and administrators have, by design, been given sufficient privileges to carry out their assigned duties to operate and evolve the service. Microsoft deploys combinations of preventive, detective, and reactive controls including the following mechanisms to help protect against unauthorized developer and/or administrative activity:

- Tight access control to sensitive data
- Combinations of controls that greatly enhance independent detection of malicious activity
- Multiple levels of monitoring, logging, and reporting

Additionally, Microsoft conducts background verification checks of certain operations personnel, and limits access to applications, systems, and network infrastructure in proportion to the level of background verification. Operations personnel follow a formal process when they are required to access a customer’s account or related information in the performance of their duties.

## Is data shared with other customers?
No. Customer data is isolated from other customers and is not shared. However, insights on the data resulting from Microsoft processing, and which don’t contain any customer specific data, might be shared with other customers. Each customer can only access data collected from its own organization and generic data that Microsoft provides.

## How long will Microsoft store my data? What is Microsoft’s data retention policy?
**At service onboarding**<br>
You can choose the data retention policy for your data. This determines how long Window Defender ATP will store your data. There’s a flexibility of choosing in the range of 1 month to six months to meet your company’s regulatory compliance needs.

**At contract termination or expiration**<br>
Your data will be kept for a period of at least 90 days, during which it will be available to you. At the end of this period, that data will be erased from Microsoft’s systems to make it unrecoverable, no later than 180 days from contract termination or expiration.


## Can Microsoft help us maintain regulatory compliance?
Microsoft provides customers with detailed information about Microsoft's security and compliance programs, including audit reports and compliance packages, to help customers assess Windows Defender ATP services against their own legal and regulatory requirements. Windows Defender ATP is ISO 27001 certified and has a roadmap for obtaining national, regional and industry-specific certifications.


By providing customers with compliant, independently-verified services, Microsoft makes it easier for customers to achieve compliance for the infrastructure and applications they run.

For more information on the Windows Defender ATP ISO certification reports, see [Microsoft Trust Center](https://www.microsoft.com/en-us/trustcenter/compliance/iso-iec-27001). 

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
