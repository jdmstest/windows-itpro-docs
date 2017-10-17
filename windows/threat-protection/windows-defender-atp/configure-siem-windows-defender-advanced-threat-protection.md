---
title: Pull alerts to your SIEM tools from Windows Defender Advanced Threat Protection
description: Learn how to use REST API and configure supported security information and events management tools to receive and pull alerts.
keywords: configure siem, security information and events management tools, splunk, arcsight, custom indicators, rest api, alert definitions, indicators of compromise
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

# Pull alerts to your SIEM tools

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## Pull alerts using supported security information and events management (SIEM) tools
Windows Defender ATP supports (SIEM) tools to pull alerts. Windows Defender ATP exposes alerts through an HTTPS endpoint hosted in Azure. The endpoint can be configured to pull alerts from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.


Windows Defender ATP currently supports the following SIEM tools:

- Splunk
- HP ArcSight

To use either of these supported SIEM tools you'll need to:

- [Enable SIEM integration in Windows Defender ATP](enable-siem-integration-windows-defender-advanced-threat-protection.md)
- Configure the supported SIEM tool:
    - [Configure Splunk to pull Windows Defender ATP alerts](configure-splunk-windows-defender-advanced-threat-protection.md)
    - [Configure HP ArcSight to pull Windows Defender ATP alerts](configure-arcsight-windows-defender-advanced-threat-protection.md)

For more information on the list of fields exposed in the alerts API see, [Windows Defender ATP alert API fields](api-portal-mapping-windows-defender-advanced-threat-protection.md).


## Pull Windows Defender ATP alerts using REST API
Windows Defender ATP supports the OAuth 2.0 protocol to pull alerts using REST API.

For more information, see [Pull Windows Defender ATP alerts using REST API](pull-alerts-using-rest-api-windows-defender-advanced-threat-protection.md).


## In this section

Topic | Description
:---|:---
[Enable SIEM integration in Windows Defender ATP](enable-siem-integration-windows-defender-advanced-threat-protection.md)| Learn about enabling the SIEM integration feature in the **Preferences setup** page in the portal so that you can use and generate the required information to configure supported SIEM tools.
[Configure Splunk to pull Windows Defender ATP alerts](configure-splunk-windows-defender-advanced-threat-protection.md)| Learn about installing the REST API Modular Input app and other configuration settings to enable Splunk to pull Windows Defender ATP alerts.
[Configure ArcSight to pull Windows Defender ATP alerts](configure-arcsight-windows-defender-advanced-threat-protection.md)| Learn about installing the HP ArcSight REST FlexConnector package and the files you need to configure ArcSight to pull Windows Defender ATP alerts.
[Windows Defender ATP alert API fields](api-portal-mapping-windows-defender-advanced-threat-protection.md) | Understand what data fields are exposed as part of the alerts API and how they map to the Windows Defender ATP portal.
[Pull Windows Defender ATP alerts using REST API](pull-alerts-using-rest-api-windows-defender-advanced-threat-protection.md) | Use the Client credentials OAuth 2.0 flow to pull alerts from Windows Defender ATP using REST API.
[Troubleshoot SIEM tool integration issues](troubleshoot-siem-windows-defender-advanced-threat-protection.md) | Address issues you might encounter when using the SIEM integration feature.
