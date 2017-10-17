---
title: Manage Windows Defender Advanced Threat Protection alerts
description: Change the status of alerts, create suppression rules to hide alerts, submit comments, and review change history for individual alerts with the Manage Alert menu.
keywords: manage alerts, manage, alerts, status, new, in progress, resolved, resolve alerts, suppress, supression, rules, context, history, comments, changes
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

# Manage Windows Defender Advanced Threat Protection alerts

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Windows Defender ATP notifies you of possible malicious events, attributes, and contextual information through alerts. A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue** menu.

You can manage alerts by selecting an alert in the **Alerts queue** or the **Alerts related to this machine** section of the machine details view.

Selecting an alert in either of those places brings up the **Alert management pane**.

![Image of alert status](images/atp-alert-status.png)

## Change the status of an alert

You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses. This helps you organize and manage how your team can respond to alerts.

For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.

Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a machine that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.

## Alert classification
You can specify if an alert is a true alert or a false alert.

## Assign alerts
If an alert is no yet assigned, you can select **Assign to me** to assign the alert to yourself.

## Add comments and view the history of an alert
You can add comments and view historical events about an alert to see previous changes made to the alert.

Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.

Added comments instantly appear on the pane.

## Suppress alerts
There might be scenarios where you need to suppress alerts from appearing in the Windows Defender ATP portal. Windows Defender ATP lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization. 

Suppression rules can be created from an existing alert. They can be disabled and reenabled if needed.

When a suppression rule is created, it will take effect from the point when the rule is created. The rule will not affect existing alerts already in the queue prior to the rule creation. The rule will only be applied on alerts that satisfy the conditions set after the rule is created.

There are two contexts for a suppression rule that you can choose from:

- **Suppress alert on this machine**
- **Suppress alert in my organization**

The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.

You can use the examples in the following table to help you choose the context for a suppression rule:

| **Context**                           | **Definition**                                                                                                                                              | **Example scenarios**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Suppress alert on this machine**    | Alerts with the same alert title and on that specific machine only will be suppressed. <br /><br />All other alerts on that machine will not be suppressed. | <ul><li>A security researcher is investigating a malicious script that has been used to attack other machines in your organization.</li><li>A developer regularly creates PowerShell scripts for their team.</li></ul> |
| **Suppress alert in my organization** | Alerts with the same alert title on any machine will be suppressed.                                                                                         | <ul><li>A benign administrative tool is used by everyone in your organization.</li></ul>                                                                                                                               |


### Suppress an alert and create a new suppression rule:
Create custom rules to control when alerts are suppressed, or resolved. You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions. After specifying the context, you’ll be able to configure the action and scope on the alert. 

1. Select the alert you'd like to suppress. This brings up the **Alert management** pane.

2. Scroll down to the **Create a supression rule** section.

    ![Image of alert status](images/atp-create-suppression-rule.png)

3. Choose the context for suppressing the alert.
  
    ![Image of alert status](images/atp-new-suppression-rule.png)

  > [!NOTE]
  > You cannot create a custom or blank suppression rule. You must start from an existing alert.

4. Specify the conditions for when the rule is applied:
    - Alert title
    - Indicator of compromise (IOC)
    - Suppression conditions

    > [!NOTE]
    > The SHA1 of the alert cannot be modified, however you can clear the SHA1 to remove it from the suppression conditions.
    
5. Specify the action and scope on the alert. <br>
   You can automatically resolve an alert or hide it from the portal. Alerts that are automatically resolved will appear in the resolved section of the alerts queue. Alerts that are marked as hidden will be suppressed from the entire system, both on the machine's associated alerts and from the dashboard. You can also specify to suppress the alert on the machine only or the whole organization.

6. Click **Save and close**.


### View the list of suppression rules

1. Click **Alerts queue** > **Suppression rules**.

2. The list of suppression rules shows all the rules that users in your organization have created.

You can select rules to open up the **Alert management** pane. From there, you can activate previously disabled rules.

## Related topics
- [View the Windows Defender Advanced Threat Protection Security operations dashboard](dashboard-windows-defender-advanced-threat-protection.md)
- [View and organize the Windows Defender Advanced Threat Protection Alerts queue ](alerts-queue-windows-defender-advanced-threat-protection.md)
- [Investigate Windows Defender Advanced Threat Protection alerts](investigate-alerts-windows-defender-advanced-threat-protection.md)
- [Investigate a file associated with a Windows Defender ATP alert](investigate-files-windows-defender-advanced-threat-protection.md)
- [Investigate an IP address associated with a Windows Defender ATP alert](investigate-ip-windows-defender-advanced-threat-protection.md)
- [Investigate a domain associated with a Windows Defender ATP alert](investigate-domain-windows-defender-advanced-threat-protection.md)
- [View and organize the Windows Defender ATP Machines list](machines-view-overview-windows-defender-advanced-threat-protection.md)
- [Investigate machines in the Windows Defender ATP Machines list](investigate-machines-windows-defender-advanced-threat-protection.md)
- [Investigate a user account in Windows Defender ATP](investigate-user-windows-defender-advanced-threat-protection.md)
- [Take response actions in Windows Defender ATP](response-actions-windows-defender-advanced-threat-protection.md)
