---
title: Configure Windows Defender ATP client endpoints
description: Configure client endpoints so that they can send sensor data to the Windows Defender ATP sensor.
keywords: configure client endpoints, endpoint management, configure Windows ATP endpoints, configure Windows Defender Advanced Threat Protection endpoints
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

# Configure Windows Defender ATP client endpoints

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

Endpoints in your organization must be configured so that the Windows Defender ATP service can get sensor data from them. There are various methods and deployment tools that you can use to configure the endpoints in your organization.

Windows Defender ATP supports the following deployment tools and methods:

- Group Policy
- System Center Configuration Manager
- Mobile Device Management (including Microsoft Intune)
- Local script

## In this section
Topic | Description
:---|:---
[Configure endpoints using Group Policy](configure-endpoints-gp-windows-defender-advanced-threat-protection.md) | Use Group Policy to deploy the configuration package on endpoints.
[Configure endpoints using System Center Configuration Manager](configure-endpoints-sccm-windows-defender-advanced-threat-protection.md) | You can use either use System Center Configuration Manager (current branch) version 1606 or System Center Configuration Manager(current branch) version 1602 or earlier to deploy the configuration package on endpoints.
[Configure endpoints using Mobile Device Management tools](configure-endpoints-mdm-windows-defender-advanced-threat-protection.md) | Use Mobile Device Management tools or Microsoft Intune to deploy the configuration package on endpoints.
[Configure endpoints using a local script](configure-endpoints-script-windows-defender-advanced-threat-protection.md) | Learn how to use the local script to deploy the configuration package on endpoints.
[Configure non-persistent virtual desktop infrastructure (VDI) machines](configure-endpoints-vdi-windows-defender-advanced-threat-protection.md) | Learn how to use the configuration package to configure VDI machines.


>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)