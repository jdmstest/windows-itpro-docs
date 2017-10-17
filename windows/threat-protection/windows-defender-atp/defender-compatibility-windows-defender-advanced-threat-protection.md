---
title: Windows Defender compatibility
description: Learn about how Windows Defender works with Windows Defender ATP and how it functions when a third-party antimalware client is used.  
keywords: windows defender compatibility, defender, windows defender atp
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

# Windows Defender compatibility

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

The Windows Defender Advanced Threat Protection agent depends on Windows Defender Antivirus for some capabilities such as file scanning.

If an onboarded endpoint is protected by a third-party antimalware client, Windows Defender Antivirus on that endpoint will enter into passive mode.

Windows Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.

The Windows Defender Antivirus interface will be disabled, and users on the endpoint will not be able to use Windows Defender Antivirus to perform on-demand scans or configure most options.

For more information, see the [Windows Defender Antivirus and Windows Defender ATP compatibility topic](../windows-defender-antivirus/windows-defender-antivirus-compatibility.md).
