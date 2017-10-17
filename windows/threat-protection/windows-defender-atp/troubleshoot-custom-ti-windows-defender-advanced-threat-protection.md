---
title: Troubleshoot custom threat intelligence issues in Windows Defender ATP
description: Troubleshoot issues that might arise when using the custom threat intelligence feature in Windows Defender ATP.
keywords: troubleshoot, custom threat intelligence, custom ti, rest api, api, alert definitions, indicators of compromise
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

# Troubleshoot custom threat intelligence issues

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

You might need to troubleshoot issues while using the custom threat intelligence feature.

This page provides detailed steps to troubleshoot issues you might encounter while using the feature.


## Learn how to get a new client secret
If your client secret expires or if you've misplaced the copy provided when you were enabling the custom threat intelligence application,  you'll need to get a new secret.

1. Login to the [Azure management portal](https://ms.portal.azure.com).

2. Select **Active Directory**.

3. Select your tenant.

4. Click **Application**, then select your custom threat intelligence application. The application name is **WindowsDefenderATPThreatIntelAPI** (formerly known as **WindowsDefenderATPCustomerTiConnector**).

5. Select **Keys** section, then provide a key description and specify the key validity duration.

6. Click **Save**. The key value is displayed.

7. Copy the value and save it in a safe place.


>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-troubleshootcustomti-belowfoldlink) 


## Related topics
- [Understand threat intelligence concepts](threat-indicator-concepts-windows-defender-advanced-threat-protection.md)
- [Create custom alerts using the threat intelligence API](custom-ti-api-windows-defender-advanced-threat-protection.md)
- [Enable the custom threat intelligence API in Windows Defender ATP](enable-custom-ti-windows-defender-advanced-threat-protection.md)
- [PowerShell code examples for the custom threat intelligence API](powershell-example-code-windows-defender-advanced-threat-protection.md)
- [Python code examples for the custom threat intelligence API](python-example-code-windows-defender-advanced-threat-protection.md)
- [Experiment with custom threat intelligence alerts](experiment-custom-ti-windows-defender-advanced-threat-protection.md)
