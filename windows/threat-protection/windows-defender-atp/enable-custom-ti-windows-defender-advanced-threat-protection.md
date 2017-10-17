---
title: Enable the custom threat intelligence API in Windows Defender ATP
description: Learn how to setup the custom threat intelligence application in Windows Defender ATP to create custom threat intelligence (TI).
keywords: enable custom threat intelligence application, custom ti application, application name, client id, authorization url, resource, client secret, access tokens
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

# Enable the custom threat intelligence API in Windows Defender ATP

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-enablecustomti-abovefoldlink) 

Before you can create custom threat intelligence (TI) using REST API, you'll need to set up the custom threat intelligence application through the Windows Defender ATP portal.

1. In the navigation pane, select **Preference Setup** > **Threat intel API**.

  ![Image of threat intel API menu](images/atp-threat-intel-api.png)

2. Select **Enable threat intel API**. This activates the **Azure Active Directory application** setup sections with pre-populated values.

3. Copy the individual values or select **Save details to file** to download a file that contains all the values.

  >[!WARNING]
  >The client secret is only displayed once. Make sure you keep a copy of it in a safe place. <br>
  For more information about getting a new secret see, [Learn how to get a new secret](troubleshoot-custom-ti-windows-defender-advanced-threat-protection.md#learn-how-to-get-a-new-client-secret).

4. Select **Generate tokens** to get an access and refresh token.

You’ll need to use the access token in the Authorization header when doing REST API calls.

## Related topics
- [Understand threat intelligence concepts](threat-indicator-concepts-windows-defender-advanced-threat-protection.md)
- [Enable the custom threat intelligence API in Windows Defender ATP](enable-custom-ti-windows-defender-advanced-threat-protection.md)
- [PowerShell code examples for the custom threat intelligence API](powershell-example-code-windows-defender-advanced-threat-protection.md)
- [Python code examples for the custom threat intelligence API](python-example-code-windows-defender-advanced-threat-protection.md)
- [Experiment with custom threat intelligence alerts](experiment-custom-ti-windows-defender-advanced-threat-protection.md)
- [Troubleshoot custom threat intelligence issues](troubleshoot-custom-ti-windows-defender-advanced-threat-protection.md)
