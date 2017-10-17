---
title: Troubleshoot Windows Defender Advanced Threat Protection
description: Find solutions and work arounds to known issues such as server errors when trying to access the service.
keywords: troubleshoot Windows Defender Advanced Threat Protection, troubleshoot Windows ATP, server error, access denied, invalid credentials, no data, dashboard portal, whitelist, event viewer
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

# Troubleshoot Windows Defender Advanced Threat Protection

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

This section addresses issues that might arise as you use the Windows Defender Advanced Threat service.

### Server error - Access is denied due to invalid credentials
If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.
Configure your browser to allow cookies.

### Elements or data missing on the portal
If some UI elements or data is missing on the Windows Defender ATP portal it’s possible that proxy settings are blocking it.

Make sure that `*.securitycenter.windows.com` is included the proxy whitelist.


> [!NOTE]
> You must use the HTTPS protocol when adding the following endpoints.

### Windows Defender ATP service shows event or error logs in the Event Viewer

See the topic [Review events and errors on endpoints with Event Viewer](event-error-codes-windows-defender-advanced-threat-protection.md) for a list of event IDs that are reported by the Windows Defender ATP service. The topic also contains troubleshooting steps for event errors.

### Windows Defender ATP service fails to start after a reboot and shows error 577

If onboarding endpoints successfully completes but Windows Defender ATP does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.

For more information, see [Ensure that Windows Defender is not disabled by policy](troubleshoot-onboarding-windows-defender-advanced-threat-protection.md#ensure-that-windows-defender-is-not-disabled-by-a-policy).

#### Known issues with regional formats

**Date and time formats**<br>
There are some known issues with the time and date formats. 

The following date formats are supported:
- MM/dd/yyyy
- dd/MM/yyyy

The following date and time formats are currently not supported:
- Date format yyyy/MM/dd
- Date format dd/MM/yy
- Date format with yy. Will only show yyyy.
- Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported). Only the 24-hour format is supported.

**Use of comma to indicate thousand**<br>
Support of use of comma as a separator in numbers are not supported. Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator. For example, 15,5K is displayed as 15.5K.

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)


### Related topic
- [Troubleshoot Windows Defender Advanced Threat Protection onboarding issues](troubleshoot-onboarding-windows-defender-advanced-threat-protection.md)
- [Review events and errors on endpoints with Event Viewer](event-error-codes-windows-defender-advanced-threat-protection.md)
