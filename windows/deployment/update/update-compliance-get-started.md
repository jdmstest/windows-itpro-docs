---
title: Get started with Update Compliance (Windows 10)
description: Configure Update Compliance in OMS to see the status of updates and antimalware protection on devices in your network.
keywords: update compliance, oms, operations management suite, prerequisites, requirements, updates, upgrades, antivirus, antimalware, signature, log analytics, wdav
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: deploy
author: jaimeo
---

# Get started with Update Compliance

This topic explains the steps necessary to configure your environment for Windows Analytics: Update Compliance. 

Steps are provided in sections that follow the recommended setup process:
1.	Ensure that [prerequisites](#update-compliance-prerequisites) are met.
2.	[Add Update Compliance](#add-update-compliance-to-microsoft-operations-management-suite) to Microsoft Operations Management Suite.
3.	[Deploy your Commercial ID](#deploy-your-commercial-id-to-your-windows-10-devices) to your organization’s devices.

## Update Compliance prerequisites

Update Compliance has the following requirements: 
1. Update Compliance is currently only compatible with Windows 10 devices. The solution is intended to be used with desktop devices (Windows 10 workstations and laptops). 
2. The solution requires that Windows 10 telemetry is enabled on all devices that are intended to be displayed in the solution. These devices must have at least the [basic level of telemetry](https://technet.microsoft.com/itpro/windows/manage/configure-windows-telemetry-in-your-organization#basic-level) enabled. To learn more about Windows telemetry, see [Configure Windows telemetry in your organization](/windows/configuration/configure-windows-telemetry-in-your-organization). 
3. The telemetry of your organization’s Windows devices must be successfully transmitted to Microsoft. Microsoft has specified [endpoints for each of the telemetry services](https://technet.microsoft.com/itpro/windows/manage/configure-windows-telemetry-in-your-organization#endpoints), which must be whitelisted by your organization so the data can be transmitted. The following table is taken from the article on telemetry endpoints and summarizes the use of each endpoint:

    Service | Endpoint
    --- | ---
    Connected User Experience and Telemetry component | v10.vortex-win.data.microsoft.com<BR>settings-win.data.microsoft.com
    Windows Error Reporting | watson.telemetry.microsoft.com
    Online Crash Analysis | oca.telemetry.microsoft.com


 4. To use Windows Defender Antivirus Assessment, devices must be protected by Windows Defender AV (and not a 3rd party AV program), and must have enabled [cloud-delivered protection](/windows/threat-protection/windows-defender-antivirus/utilize-microsoft-cloud-protection-windows-defender-antivirus). See the [Troublehsoot Windows Defender Antivirus reporting](/windows/threat-protection/windows-defender-antivirus/troubleshoot-reporting.md) topic for help on ensuring the configuration is correct.
 
     For endpoints running Windows 10, version 1607 or earlier, [Windows telemetry must also be set to **Enhanced**](https://docs.microsoft.com/en-us/windows/configuration/configure-windows-telemetry-in-your-organization#enhanced-level). 
    
    See the [Windows Defender Antivirus in Windows 10](/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) content library for more information on enabling, configuring, and validating Windows Defender AV.


## Add Update Compliance to Microsoft Operations Management Suite

Update Compliance is offered as a solution in the Microsoft Operations Management Suite (OMS), a collection of cloud-based servicing for monitoring and automating your on-premise and cloud environments. For more information about OMS, see [Operations Management Suite overview](https://azure.microsoft.com/en-us/documentation/articles/operations-management-suite-overview/). 

If you are already using OMS, you’ll find Update Compliance in the Solutions Gallery. Select the **Update Compliance** tile in the gallery and then click **Add** on the solution's details page. Update Compliance is now visible in your workspace. While you're in the Solutions Gallery, you should consider installing the [Upgrade Readiness](../upgrade/use-upgrade-readiness-to-manage-windows-upgrades.md)  and [Device Health](device-health-monitor.md) solutions as well, if you haven't already.

If you are not yet using OMS, use the following steps to subscribe to OMS Update Compliance:

1.	Go to [Operations Management Suite](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite) on Microsoft.com and click **Sign in**.


   [![Operations Management Suite bar with sign-in button](images/uc-02a.png)](images/uc-02.png)


2.	Sign in to Operations Management Suite (OMS). You can use either a Microsoft Account or a Work or School account to create a workspace. If your company is already using Azure Active Directory (Azure AD), use a Work or School account when you sign in to OMS. Using a Work or School account allows you to use identities from your Azure AD to manage permissions in OMS.


   [![OMS Sign-in dialog box for account name and password](images/uc-03a.png)](images/uc-03.png)


3.	Create a new OMS workspace. 


   [![OMS dialog with buttons to create a new OMS workspace or cancel](images/uc-04a.png)](images/uc-04.png)
 
4.	Enter a name for the workspace, select the workspace region, and provide the email address that you want associated with this workspace. Click **Create**.


   [![OMS Create New Workspace dialog](images/uc-05a.png)](images/uc-05.png)


5.	If your organization already has an Azure subscription, you can link it to your workspace. Note that you may need to request access from your organization’s Azure administrator. If your organization does not have an Azure subscription, create a new one or select the default OMS Azure subscription from the list. If you do not yet have an Azure subscription, follow [this guide](https://blogs.technet.microsoft.com/upgradeanalytics/2016/11/08/linking-operations-management-suite-workspaces-to-microsoft-azure/) to create and link an Azure subscription to an OMS workspace.


   [![OMS dialog to link existing Azure subscription or create a new one](images/uc-06a.png)](images/uc-06.png)


6.	To add the Update Compliance solution to your workspace, go to the Solutions Gallery.  While you have this dialog open, you should also consider adding the [Upgrade Readiness](../upgrade/use-upgrade-readiness-to-manage-windows-upgrades.md) and [Device Health](device-health-monitor.md) solutions as well, if you haven't already. To do so, just select the check boxes for those solutions.


   [![OMS workspace with Solutions Gallery tile highlighted](images/uc-07a.png)](images/uc-07.png)


7.	Select the **Update Compliance** tile in the gallery and then select **Add** on the solution’s details page. You might need to scroll to find **Update Compliance**. The solution is now visible in your workspace. 

 
   [![Workspace showing Solutions Gallery](images/uc-08a.png)](images/uc-08.png)


8.	Click the **Update Compliance** tile to configure the solution. The **Settings Dashboard** opens.


   [![OMS workspace with new Update Compliance tile on the right side highlighted](images/uc-09a.png)](images/uc-09.png)


9.	Click **Subscribe** to subscribe to OMS Update Compliance. You will then need to distribute your Commercial ID across all your organization’s devices. More information on the Commercial ID is provided below.


   [![Series of blades showing Connected Sources, Windows Telemetry, and Upgrade Analytics solution with Subscribe button](images/uc-10a.png)](images/uc-10.png)


After you are subscribed to OMS Update Compliance and your devices have a Commercial ID, you will begin receiving data. It will typically take 24 hours for the first data to begin appearing. The following section explains how to deploy your Commercial ID to your Windows 10 devices.

>[!NOTE]
>You can unsubscribe from the Update Compliance solution if you no longer want to monitor your organization’s devices. User device data will continue to be shared with Microsoft while the opt-in keys are set on user devices and the proxy allows traffic.

## Deploy your Commercial ID to your Windows 10 devices

In order for your devices to show up in Windows Analytics: Update Compliance, they must be configured with your organization’s Commercial ID. This is so that Microsoft knows that a given device is a member of your organization and to feed that device’s data back to you. There are two primary methods for widespread deployment of your Commercial ID: Group Policy and Mobile Device Management (MDM). 

- Using Group Policy<BR><BR>
    Deploying your Commercial ID using Group Policy can be accomplished by configuring domain Group Policy Objects with the Group Policy Management Editor, or by configuring local Group Policy using the Local Group Policy Editor.
    1. In the console tree, navigate to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Data Collection and Preview Builds**
    2. Double-click **Configure the Commercial ID**
    3. In the **Options** box, under **Commercial Id**, type the Commercial ID GUID, and then click **OK**.<P>

- Using Microsoft Mobile Device Management (MDM)<BR><BR>
    Microsoft’s Mobile Device Management can be used to deploy your Commercial ID to your organization’s devices. The Commercial ID is listed under **Provider/ProviderID/CommercialID**. More information on deployment using MDM can be found [here](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/dmclient-csp).  


## Related topics

[Use Update Compliance to monitor Windows Updates](update-compliance-using.md)