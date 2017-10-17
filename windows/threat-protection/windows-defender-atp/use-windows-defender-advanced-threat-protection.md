---
title: Use the Windows Defender Advanced Threat Protection portal
description: Learn about the features on Windows Defender ATP portal, including how alerts work, and suggestions on how to investigate possible breaches and attacks.
keywords: dashboard, alerts queue, manage alerts, investigation, investigate alerts, investigate machines, submit files, deep analysis, high, medium, low, severity, ioc, ioa
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

# Use the Windows Defender Advanced Threat Protection portal

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-usewdatp-abovefoldlink) 

A typical security breach investigation requires a member of a security operations team to:

1. View an alert on the **Security operations dashboard** or **Alerts queue**
2. Review the indicators of compromise (IOC) or indications of attack (IOAs)
3. Review a timeline of alerts, behaviors, and events from the machine
4. Manage alerts, understand the threat or potential breach, collect information to support taking action, and resolve the alert

![Flowchart describing the four stages of investigation](images/overview.png)

Security operation teams can use Windows Defender ATP portal to carry out this end-to-end process without having to leave the portal.

Teams can monitor the overall status of enterprise endpoints from the **Security operations dashboard**, gain insight on the various alerts, their category, when they were observed, and how long they’ve been in the network at a glance.

### In this section

Topic | Description
:---|:---
[View the Windows Defender Advanced Threat Protection Security operations dashboard](dashboard-windows-defender-advanced-threat-protection.md) | The Windows Defender ATP  **Security operations dashboard** provides a snapshot of your network. You can view aggregates of alerts, the overall status of the service of the endpoints on your network, investigate machines, files, and URLs, and see snapshots of threats seen on machines.
[View the Windows Defender Advanced Threat Protection Security analytics dashboard](security-analytics-dashboard-windows-defender-advanced-threat-protection.md) | The **Security Analytics dashboard** expands your visibility into the overall security posture of your organization. From this dashboard, you'll be able to quickly assess the security posture of your organization, see machines that require attention, as well as recommendations for actions to further reduce the attack surface in your organization - all in one place.
[View and organize the Alerts queue](alerts-queue-windows-defender-advanced-threat-protection.md) | You can sort and filter alerts across your network, and drill down on individual alert queues such as new, in progress, or resolved queues.
[Investigate alerts](investigate-alerts-windows-defender-advanced-threat-protection.md)| Investigate alerts in Windows Defender ATP which might indicate possible security breaches on endpoints in your organization.
[Investigate files](investigate-files-windows-defender-advanced-threat-protection.md) | Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.
[Investigate an IP address](investigate-ip-windows-defender-advanced-threat-protection.md) | Examine possible communication between your machines and external Internet protocol (IP) addresses.
[Investigate a domain](investigate-domain-windows-defender-advanced-threat-protection.md) | Investigate a domain to see if machines and servers in your enterprise network have been communicating with a known malicious domain.
[View and organize the Machines list](machines-view-overview-windows-defender-advanced-threat-protection.md)| You can sort, filter, and exporting the machine list.
[Investigate machines](investigate-machines-windows-defender-advanced-threat-protection.md) | The **Machines list** shows a list of the machines in your network, the corresponding number of active alerts for each machine categorized by alert severity levels, as well as the number of threats.
[Investigate a user account](investigate-user-windows-defender-advanced-threat-protection.md)| Investigate user accounts with the most active alerts.
[Manage alerts](manage-alerts-windows-defender-advanced-threat-protection.md) | The **Manage Alert** menu on every alert lets you change an alert's status, resolve it, suppress it, or contribute comments about the alert.
[Take response actions](response-actions-windows-defender-advanced-threat-protection.md)| Take action on a machine or file to quickly respond to detected attacks.
