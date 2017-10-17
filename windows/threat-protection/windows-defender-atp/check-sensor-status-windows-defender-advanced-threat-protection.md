---
title: Check the health state of the sensor in Windows Defender ATP
description: Check the sensor health on machines to identify which ones are misconfigured, inactive, or are not reporting sensor data.
keywords: sensor, sensor health, misconfigured, inactive, no sensor data, sensor data, impaired communications, communication
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

# Check sensor health state in Windows Defender ATP

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

The sensor health tile provides information on the individual endpoint’s ability to provide sensor data and communicate with the Windows Defender ATP service. It reports how many machines require attention and helps you identify problematic machines and take action to correct known issues.

![Windows Defender ATP sensor health tile](images/atp-portal-sensor.png)

There are two status indicators on the tile that provide information on the number of machines that are not reporting properly to the service:
-	**Inactive** - Machines that have stopped reporting to the Windows Defender ATP service for more than seven days in the past month.
- **Misconfigured** - These machines might partially be reporting sensor data to the Windows Defender ATP service and might have configuration errors that need to be corrected.

Clicking any of the groups directs you to Machines list, filtered according to your choice.

![Windows Defender ATP sensor filter](images/atp-sensor-filter.png)

<!--
![Windows Defender ATP sensor filter](images/atp-machines-list-misconfigured.png)

Filter the **Machines list** by time period, **OS Platform**, **Health**, or **Malware category alerts** to focus on certain sets of machines, according to the desired criteria.  

-->

You can also download the entire list in CSV format using the **Export to CSV** feature. For more information on filters, see [View and organize the Machines list](machines-view-overview-windows-defender-advanced-threat-protection.md).

You can filter the health state list by the following status:
- **Active** - Machines that are actively reporting to the Windows Defender ATP service.
- **Inactive** - Machines that have stopped reporting to the Windows Defender ATP service.
- **Misconfigured** - These machines might partially be reporting sensor data to the Windows Defender ATP service but have configuration errors that need to be corrected. Misconfigured machines can have either one or a combination of the following issues:
  - **No sensor data** - Machines has stopped sending sensor data. Limited alerts can be triggered from the machine.
  - **Impaired communications** - Ability to communicate with machine is impaired. Sending files for deep analysis, blocking files, isolating machine from network and other actions that require communication with the machine may not work.

You can view the machine details when you click on a misconfigured or inactive machine. You’ll see more specific machine information when you click the information icon.

![Windows Defender ATP sensor filter](images/atp-machine-health-details.png)

In the **Machines list**, you can download a full list of all the machines in your organization in a CSV format. To download, click the **Manage Alert** menu icon on the top corner of the page.

>[!NOTE]
>Export the list in CSV format to display the unfiltered data. The CSV file will include all machines in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.

## Related topic
- [Fix unhealthy sensors in Windows Defender ATP](fix-unhealhty-sensors-windows-defender-advanced-threat-protection.md)
