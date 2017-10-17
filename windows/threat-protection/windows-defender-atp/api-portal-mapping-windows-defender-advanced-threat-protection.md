---
title: Windows Defender ATP alert API fields
description: Understand how the alert API fields map to the values in the Windows Defender ATP portal.
keywords: alerts, alert fields, fields, api, fields, pull alerts, rest api, request, response
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

# Windows Defender ATP alert API fields

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]


>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-apiportalmapping-abovefoldlink) 

Understand what data fields are exposed as part of the alerts API and how they map to the Windows Defender ATP portal.


##	Alert API fields and portal mapping
The following table lists the available fields exposed in the alerts API payload. It shows examples for the populated values and a reference on how data is reflected on the portal.


The ArcSight field column contains the default mapping between the Windows Defender ATP fields and the built-in fields in ArcSight. You can download the mapping file from the portal when you enable the SIEM integration feature and you can modify it to match the  needs of your organization. For more information, see [Enable SIEM integration in Windows Defender ATP](enable-siem-integration-windows-defender-advanced-threat-protection.md).

Field numbers match the numbers in the images below.

> [!div class="mx-tableFixed"]
| Portal   label   | SIEM field name           | ArcSight field      | Example value                                                                      | Description                                                                                                                                                                    |
|------------------|---------------------------|---------------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1                | AlertTitle                | name                | A dll was unexpectedly loaded into   a high integrity process without a UAC prompt | Value available for every alert.                                                                                                                                               |
| 2                | Severity                  | deviceSeverity      | Medium                                                                             | Value available for every alert.                                                                                                                                               |
| 3                | Category                  | deviceEventCategory | Privilege Escalation                                                               | Value available for every alert.                                                                                                                                               |
| 4                | Source                    | sourceServiceName   | WindowsDefenderATP                                                                 | Windows Defender Antivirus or   Windows Defender ATP. Value available for every alert.                                                                                         |
| 5                | MachineName               | sourceHostName      | liz-bean                                                                           | Value available for every alert.                                                                                                                                               |
| 6                | FileName                  | fileName            | Robocopy.exe                                                                       | Available for alerts associated   with a file or process.                                                                                                                      |
| 7                | FilePath                  | filePath            | C:\Windows\System32\Robocopy.exe                                                   | Available for alerts associated   with a file or process.                                                                                                                     |
| 8                | UserDomain                | sourceNtDomain      | contoso                                                                            | The domain of the user context   running the activity, available for Windows Defender ATP behavioral based   alerts.                                                           |
| 9                | UserName                  | sourceUserName      | liz-bean                                                                           | The user context running the   activity, available for Windows Defender ATP behavioral based alerts.                                                                           |
| 10               | Sha1                      | fileHash            | 5b4b3985339529be3151d331395f667e1d5b7f35                                           | Available for alerts associated   with a file or process.                                                                                                                      |
| 11               | Md5                       | deviceCustomString5 | 55394b85cb5edddff551f6f3faa9d8eb                                                   | Available for Windows Defender AV   alerts.                                                                                                                                    |
| 12               | Sha256                    | deviceCustomString6 | 9987474deb9f457ece2a9533a08ec173a0986fa3aa6ac355eeba5b622e4a43f5                   | Available for Windows Defender AV   alerts.                                                                                                                                    |
| 13               | ThreatName                | eviceCustomString1  | Trojan:Win32/Skeeyah.A!bit                                                         | Available for Windows Defender AV   alerts.                                                                                                                                    |
| 14               | IpAddress                 | sourceAddress       | 218.90.204.141                                                                     | Available for alerts associated   to network events. For example, 'Communication to a malicious network   destination'.                                                        |
| 15               | Url                       | requestUrl          | down.esales360.cn                                                                  | Available for alerts associated to   network events. For example, 'Communication to a malicious network   destination'.                                                         |
| 16               | RemediationIsSuccess      | deviceCustomNumber2 | TRUE                                                                               | Available for Windows Defender AV   alerts. ArcSight value is 1 when TRUE and 0 when FALSE.                                                                                    |
| 17               | WasExecutingWhileDetected | deviceCustomNumber1 | FALSE                                                                              | Available for Windows Defender AV   alerts. ArcSight value is 1 when TRUE and 0 when FALSE.                                                                                    |
| 18               | AlertId                   | externalId          | 636210704265059241_673569822                                                       | Value available for every alert.                                                                                                                                               |
| 19               | LinkToWDATP               | flexString1         | `https://securitycenter.windows.com/alert/636210704265059241_673569822`            | Value available for every alert.                                                                                                                                               |
| 20               | AlertTime                 | deviceReceiptTime   | 2017-05-07T01:56:59.3191352Z                                                       | The time the activity relevant to   the alert occurred. Value available for every alert.                                                                                       |
| 21               | MachineDomain             | sourceDnsDomain     | contoso.com                                                                        | Domain name not relevant for AAD   joined machines. Value available for every alert.                                                                                           |
| 22               | Actor                     | deviceCustomString4 |                                                                                    | Available for alerts related to a   known actor group.                                                                                                                         |
| 21+5             | ComputerDnsName           | No mapping          | liz-bean.contoso.com                                                               | The machine fully qualified   domain name. Value available for every alert.                                                                                                    |
|                  | LogOnUsers                | sourceUserId        | contoso\liz-bean;   contoso\jay-hardee                                             | The domain and user of the   interactive logon user/s at the time of the event. Note: For machines on   Windows 10 version 1607, the domain information will not be available. |
|                  | InternalIPv4List          | No mapping          | 192.168.1.7, 10.1.14.1                                                             | List of IPV4 internal IPs for active network interfaces.                                                                                                                                                                               |
|                  | InternalIPv6List          | No mapping          | fd30:0000:0000:0001:ff4e:003e:0009:000e,   FE80:CD00:0000:0CDE:1257:0000:211E:729C | List of IPV6 internal IPs for active network interfaces.                                                                                                                                                                               |
| Internal   field | LastProcessedTimeUtc      | No mapping          | 2017-05-07T01:56:58.9936648Z                                                       | Time when event arrived at the   backend. This field can be used when setting the request parameter for the   range of time that alerts are retrieved.                         |
|                  | Not part of the schema    | deviceVendor        |                                                                                    | Static value in the ArcSight   mapping - 'Microsoft'.                                                                                                                          |
|                  | Not part of the schema    | deviceProduct       |                                                                                    | Static value in the ArcSight   mapping - 'Windows Defender ATP'.                                                                                                               |
|                  | Not part of the schema    | deviceVersion       |                                                                                    | Static value in the ArcSight   mapping - '2.0', used to identify the mapping versions.                                                                                         


![Image of alert with numbers](images/atp-alert-page.png)

![Image of alert details pane with numbers](images/atp-siem-mapping13.png)

![Image of artifact timeline with numbers](images/atp-siem-mapping3.png)

![Image of artifact timeline with numbers](images/atp-siem-mapping4.png)

![Image machine view](images/atp-mapping6.png)

![Image browser URL](images/atp-mapping5.png)

![Image actor alert](images/atp-mapping7.png)


## Related topics
- [Enable SIEM integration in Windows Defender ATP](enable-siem-integration-windows-defender-advanced-threat-protection.md)
- [Configure Splunk to pull Windows Defender ATP alerts](configure-splunk-windows-defender-advanced-threat-protection.md)
- [Configure ArcSight to pull Windows Defender ATP alerts](configure-arcsight-windows-defender-advanced-threat-protection.md)
- [Pull Windows Defender ATP alerts using REST API](pull-alerts-using-rest-api-windows-defender-advanced-threat-protection.md)
- [Troubleshoot SIEM tool integration issues](troubleshoot-siem-windows-defender-advanced-threat-protection.md)
