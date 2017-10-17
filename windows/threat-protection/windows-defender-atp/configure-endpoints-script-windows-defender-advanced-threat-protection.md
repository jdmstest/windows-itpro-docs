---
title: Configure Windows Defender ATP endpoints using a local script
description: Use a local script to deploy the configuration package on endpoints so that they are onboarded to the service.
keywords: configure endpoints using a local script, endpoint management, configure Windows ATP endpoints, configure Windows Defender Advanced Threat Protection endpoints
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

# Configure endpoints using a local script

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

You can also manually onboard individual endpoints to Windows Defender ATP. You might want to do this first when testing the service before you commit to onboarding all endpoints in your network.

> [!NOTE]
> The script has been optimized to be used on a limited number of machines (1-10 machines). To deploy to scale, use other deployment options. For more information on using other deployment options, see [Configure Windows Defender ATP endpoints](configure-endpoints-windows-defender-advanced-threat-protection.md).

## Onboard endpoints
1.  Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard. You can also get the package from the [Windows Defender ATP portal](https://securitycenter.windows.com/):

    a.  Click **Endpoint management** on the **Navigation pane**.

    b.  Select **Local Script**, click **Download package** and save the .zip file.


2.  Extract the contents of the configuration package to a location on the endpoint you want to onboard (for example, the Desktop). You should have a file named *WindowsDefenderATPOnboardingScript.cmd*.

3.  Open an elevated command-line prompt on the endpoint and run the script:

    a.  Go to **Start** and type **cmd**.

    b.  Right-click **Command prompt** and select **Run as administrator**.

    ![Window Start menu pointing to Run as administrator](images/run-as-admin.png)

4.  Type the location of the script file. If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

5.  Press the **Enter** key or click **OK**.

For for information on how you can manually validate that the endpoint is compliant and correctly reports sensor data see, [Troubleshoot Windows Defender Advanced Threat Protection onboarding issues](troubleshoot-onboarding-windows-defender-advanced-threat-protection.md).

## Configure sample collection settings
For each endpoint, you can set a configuration value to state whether samples can be collected from the endpoint when a request is made through the Windows Defender ATP portal to submit a file for deep analysis.

You can manually configure the sample sharing setting on the endpoint by using *regedit* or creating and running a *.reg* file.  

The configuration is set through the following registry key entry:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Where:<br>
Name type is a D-WORD. <br>
Possible values are:
- 0 - doesn't allow sample sharing  from this endpoint
- 1 - allows sharing of all file types from this endpoint

The default value in case the registry key doesn’t exist is 1.


## Offboard endpoints
For security reasons, the package used to offboard endpoints will expire 30 days after the date it was downloaded. Expired offboarding packages sent to an endpoint will be rejected. When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.

> [!NOTE]
> Onboarding and offboarding policies must not be deployed on the same endpoint at the same time, otherwise this will cause unpredictable collisions.

1.	Get the offboarding package from the [Windows Defender ATP portal](https://securitycenter.windows.com/):

    a. Click **Endpoint management** on the **Navigation pane**.

    b. Click the **Endpoint offboarding** section.

    c. Select **Group Policy**, click **Download package** and save the .zip file.

2.	Extract the contents of the .zip file to a shared, read-only location that can be accessed by the endpoints. You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.

3.  Open an elevated command-line prompt on the endpoint and run the script:

    a.  Go to **Start** and type **cmd**.

    b.  Right-click **Command prompt** and select **Run as administrator**.

    ![Window Start menu pointing to Run as administrator](images/run-as-admin.png)

4.  Type the location of the script file. If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*

5.  Press the **Enter** key or click **OK**.

> [!IMPORTANT]
> Offboarding causes the machine to stop sending sensor data to the portal but data from the machine, including reference to any alerts it has had will be retained for up to 6 months.


## Monitor endpoint configuration
You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding-windows-defender-advanced-threat-protection.md) to verify that the script completed successfully and the agent is running.

Monitoring can also be done directly on the portal, or by using the different deployment tools.

### Monitor endpoints using the portal
1.	Go to the Windows Defender ATP portal.

2.	Click **Machines list**.

3.	Verify that endpoints are appearing.


## Related topics
- [Configure endpoints using Group Policy](configure-endpoints-gp-windows-defender-advanced-threat-protection.md)
- [Configure endpoints using System Center Configuration Manager](configure-endpoints-sccm-windows-defender-advanced-threat-protection.md)
- [Configure endpoints using Mobile Device Management tools](configure-endpoints-mdm-windows-defender-advanced-threat-protection.md)
- [Configure non-persistent virtual desktop infrastructure (VDI) machines](configure-endpoints-vdi-windows-defender-advanced-threat-protection.md)
- [Troubleshoot Windows Defender Advanced Threat Protection onboarding issues](troubleshoot-onboarding-windows-defender-advanced-threat-protection.md)
