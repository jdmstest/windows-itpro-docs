---
title: What's new in Windows 10 deployment
description: Changes and new features related to Windows 10 deployment
keywords: deployment, automate, tools, configure, news
ms.mktglfcycl: deploy
ms.localizationpriority: high
ms.prod: w10
ms.sitesec: library
ms.pagetype: deploy
ms.date: 08/23/2017
author: greg-lindsay
---

# What's new in Windows 10 deployment

**Applies to**
-   Windows 10


## In this topic

This topic provides an overview of new solutions and online content related to deploying Windows 10 in your organization.

- For an all-up overview of new features in Windows 10, see [What's new in Windows 10](https://technet.microsoft.com/itpro/windows/whats-new/index).
- For a detailed list of changes to Windows 10 ITPro TechNet library content, see [Online content change history](#online-content-change-history).


## Windows 10 Enterprise upgrade

Windows 10 version 1703 includes a Windows 10 Enterprise E3 and E5 benefit to Microsoft customers with Enterprise Agreements (EA) or Microsoft Products & Services Agreements (MPSA). These customers can now subscribe users to Windows 10 Enterprise E3 or E5 and activate their subscriptions on up to five devices. Virtual machines can also be activated. For more information, see [Windows 10 Enterprise Subscription Activation](windows-10-enterprise-subscription-activation.md).

Windows 10 Enterprise E3 launched in the Cloud Solution Provider (CSP) channel on September 1, 2016. Previously, only organizations with a Microsoft Volume Licensing Agreement could deploy Windows 10 Enterprise to their users. With Windows 10 Enterprise E3 in CSP, small and medium-sized organizations can more easily take advantage of Windows 10 Enterprise features.

For more information, see [Windows 10 Enterprise E3 in CSP](windows-10-enterprise-e3-overview.md)


## Deployment solutions and tools

### Windows AutoPilot

Windows AutoPilot streamlines and automates the process of setting up and configuring new devices, with minimal interaction required from the end user. You can also use Windows AutoPilot to reset, repurpose and recover devices.

Windows AutoPilot joins devices to Azure Active Directory (Azure AD), optionally enrolls into MDM services, configures security policies, and sets a custom out-of-box-experience (OOBE) for the end user. For more information, see [Overview of Windows AutoPilot](windows-10-auto-pilot.md).

### Upgrade Readiness

The Upgrade Readiness tool moved from public preview to general availability on March 2, 2017. 

Upgrade Readiness helps you ensure that applications and drivers are ready for a Windows 10 upgrade. The solution provides up-to-date application and driver inventory, information about known issues, troubleshooting guidance, and per-device readiness and tracking details. 

The development of Upgrade Readiness has been heavily influenced by input from the community the development of new features is ongoing. To begin using Upgrade Readiness, add it to an existing Operation Management Suite (OMS) workspace or sign up for a new OMS workspace with the Upgrade Readiness solution enabled.  

For more information about Upgrade Readiness, see the following topics:

- [Windows Analytics blog](https://blogs.technet.microsoft.com/upgradeanalytics/)
- [Manage Windows upgrades with Upgrade Readiness](upgrade/manage-windows-upgrades-with-upgrade-readiness.md)


### Update Compliance

Update Compliance helps you to keep Windows 10 devices in your organization secure and up-to-date.

Update Compliance is a solution built using OMS Logs and Analytics that provides information about installation status of monthly quality and feature updates. Details are provided about the deployment progress of existing updates and the status of future updates. Information is also provided about devices that might need attention to resolve issues.

For more information about Update Compliance, see [Monitor Windows Updates with Update Compliance](update/update-compliance-monitor.md).

### Device Health

Device Health is the newest Windows Analytics solution that complements the existing Upgrade Readiness and Update Compliance solutions by helping to identify devices crashes and the cause. Device drivers that are causing crashes are identified along with alternative drivers that might reduce the number of crashes.  Windows Information Protection misconfigurations are also identified. For more information, see [Monitor the health of devices with Device Health](update/device-health-monitor.md)

### MBR2GPT

MBR2GPT.EXE converts a disk from Master Boot Record (MBR) to GUID Partition Table (GPT) partition style without modifying or deleting data on the disk. Previously, it was necessary to image, then wipe and reload a disk to change from MBR format to GPT. 

There are many benefits to converting the partition style of a disk to GPT, including the use of larger disk partitions, added data reliability, and faster boot and shutdown speeds. The GPT format also enables you to use the Unified Extensible Firmware Interface (UEFI) which replaces the Basic Input/Output System (BIOS) firmware interface.  Security features of Windows 10 that require UEFI mode include: Secure Boot, Early Launch Anti-malware (ELAM) driver, Windows Trusted Boot, Measured Boot, Device Guard, Credential Guard, and BitLocker Network Unlock.

For more information, see [MBR2GPT.EXE](mbr-to-gpt.md).


### Microsoft Deployment Toolkit (MDT)

MDT build 8443 is available, including support for:
- Deployment and upgrade of Windows 10, version 1607 (including Enterprise LTSB and Education editions) and Windows Server 2016.
- The Windows ADK for Windows 10, version 1607.
- Integration with Configuration Manager version 1606.

For more information about MDT, see the [MDT resource page](https://technet.microsoft.com/en-US/windows/dn475741).


### Windows Assessment and Deployment Kit (ADK)

The Windows Assessment and Deployment Kit (Windows ADK) contains tools that can be used by IT Pros to deploy Windows. See the following topics:

- [What's new in ADK kits and tools](https://msdn.microsoft.com/windows/hardware/commercialize/what-s-new-in-kits-and-tools)
- [Windows ADK for Windows 10 scenarios for IT Pros](windows-adk-scenarios-for-it-pros.md)


## Testing and validation guidance

### Windows 10 deployment proof of concept (PoC)

The Windows 10 PoC guide enables you to test Windows 10 deployment in a virtual environment and become familiar with deployment tools such as MDT and Configuration Manager. The PoC guide provides step-by-step instructions for installing and using Hyper-V to create a virtual lab environment. The guide makes extensive use of Windows PowerShell to streamline each phase of the installation and setup. 

For more information, see the following guides:

- [Step by step guide: Configure a test lab to deploy Windows 10](windows-10-poc.md)
- [Deploy Windows 10 in a test lab using Microsoft Deployment Toolkit](windows-10-poc-mdt.md)
- [Deploy Windows 10 in a test lab using System Center Configuration Manager](windows-10-poc-sc-config-mgr.md)


## Troubleshooting guidance

[Resolve Windows 10 upgrade errors](upgrade/resolve-windows-10-upgrade-errors.md) was published in October of 2016 and will continue to be updated with new fixes. The topic provides a detailed explanation of the Windows 10 upgrade process and instructions on how to locate, interpret, and resolve specific errors that can be encountered during the upgrade process.


## Online content change history

The following topics provide a change history for Windows 10 ITPro TechNet library content related to deploying and using Windows 10.

[Change history for Deploy Windows 10](change-history-for-deploy-windows-10.md)
<BR>[Change history for Access Protection](/windows/access-protection/change-history-for-access-protection)
<BR>[Change history for Device Security](/windows/device-security/change-history-for-device-security)
<BR>[Change history for Threat Protection](/windows/threat-protection/change-history-for-threat-protection)


## Related topics

[Overview of Windows as a service](update/waas-overview.md)
<BR>[Windows 10 deployment considerations](planning/windows-10-deployment-considerations.md)
<BR>[Windows 10 release information](https://technet.microsoft.com/en-us/windows/release-info.aspx)
<BR>[Windows 10 Specifications & Systems Requirements](https://www.microsoft.com/en-us/windows/windows-10-specifications)
<BR>[Windows 10 upgrade paths](upgrade/windows-10-upgrade-paths.md)
<BR>[Windows 10 deployment tools](windows-deployment-scenarios-and-tools.md)

 