---
title: Deploy Windows 10 Enterprise licenses
description: Steps to deploy Windows 10 Enterprise licenses for Windows 10 Enterprise E3 or E5 Subscription Activation, or for Windows 10 Enterprise E3 in CSP
keywords: upgrade, update, task sequence, deploy
ms.prod: w10
ms.mktglfcycl: deploy
localizationpriority: high
ms.sitesec: library
ms.pagetype: mdt
ms.date: 08/23/2017
author: greg-lindsay
---

# Deploy Windows 10 Enterprise licenses

This topic describes how to deploy Windows 10 Enterprise E3 or E5 licenses with [Windows 10 Enterprise Subscription Activation](windows-10-enterprise-subscription-activation.md) or [Windows 10 Enterprise E3 in CSP](windows-10-enterprise-e3-overview.md) and Azure Active Directory (Azure AD).

>Note: Windows 10 Enterprise Subscription Activation (EA or MPSA) requires Windows 10 Pro, version 1703 or later.<BR>
>Windows 10 Enterprise E3 in CSP requires Windows 10 Pro, version 1607 or later.<BR>

## Enabling Subscription Activation with an existing EA

If you are an EA customer with an existing Office 365 tenant, use the following steps to enable Windows 10 Subscription licenses on your existing tenant:

1.	Work with your reseller to place an order for $0 SKU. There are two SKUs available, depending on their current Windows Enterprise SA license:<BR>
    a.	**AAA-51069** - Win10UsrOLSActv Alng MonthlySub Addon E3<BR>
    b.	**AAA-51068** - Win10UsrOLSActv Alng MonthlySub Addon E5<BR>
2.	After placing an order, the OLS admin on the agreement will receive a service activation email, indicating their subscription licenses have been provisioned on the tenant.
3.	The admin can now assign subscription licenses to users.

Also in this article:
- [Explore the upgrade experience](#explore-the-upgrade-experience): How to upgrade devices using the deployed licenses.
- [Troubleshoot the user experience](#troubleshoot-the-user-experience): Examples of some license activation issues that can be encountered, and how to resolve them.

## Active Directory synchronization with Azure AD

You probably have on-premises Active Directory Domain Services (AD DS) domains. Users will use their domain-based credentials to sign in to the AD DS domain. Before you start deploying Windows 10 Enterprise E3 or E5 licenses to users, you need to synchronize the identities in the on-premises ADDS domain with Azure AD.

You might ask why you need to synchronize these identities. The answer is so that users will have a *single identity* that they can use to access their on-premises apps and cloud services that use Azure AD (such as Windows 10 Enterprise E3 or E5). This means that users can use their existing credentials to sign in to Azure AD and access the cloud services that you provide and manage for them.

**Figure 1** illustrates the integration between the on-premises AD DS domain with Azure AD. [Microsoft Azure Active Directory Connect](http://www.microsoft.com/en-us/download/details.aspx?id=47594) (Azure AD Connect) is responsible for synchronization of identities between the on-premises AD DS domain and Azure AD. Azure AD Connect is a service that you can install on-premises or in a virtual machine in Azure.

![Illustration of Azure Active Directory Connect](images/enterprise-e3-ad-connect.png)

**Figure 1. On-premises AD DS integrated with Azure AD**

For more information about integrating on-premises AD DS domains with Azure AD, see the following resources:

-   [Integrating your on-premises identities with Azure Active Directory](http://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)
-   [Azure AD + Domain Join + Windows 10](https://blogs.technet.microsoft.com/enterprisemobility/2016/02/17/azure-ad-domain-join-windows-10/)

## Preparing for deployment: reviewing requirements

Devices must be running Windows 10 Pro, version 1703, and be Azure Active Directory joined, or domain joined with Azure AD Connect. Customers who are federated with Azure Active Directory are also eligible. For more information, see [Review requirements on devices](#review-requirements-on-devices), later in this topic.

## Assigning licenses to users

Upon acquisition of Windows 10 subscription has been completed (Windows 10 Business, E3 or E5), customers will receive an email that will provide guidance on how to use Windows as an online service:

![profile](images/al01.png)

The following methods are available to assign licenses:

1. When you have the required Azure AD subscription, [group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal) is the preferred method to assign Enterprise E3 or E5 licenses to users.
2. You can sign in to portal.office.com and manually assign licenses:

    ![portal](images/al02.png)

3. You can assign licenses by uploading a spreadsheet.
4. A per-user [PowerShell scripted method](http://social.technet.microsoft.com/wiki/contents/articles/15905.how-to-use-powershell-to-automatically-assign-licenses-to-your-office-365-users.aspx) of assigning licenses is available.
5. Organizations can use synchronized [AD groups](https://ronnydejong.com/2015/03/04/assign-ems-licenses-based-on-local-active-directory-group-membership/) to automatically assign licenses. 

## Explore the upgrade experience

Now that your subscription has been established and Windows 10 Enterprise E3 or E5 licenses have been assigned to users, the users are ready to upgrade their devices running Windows 10 Pro, version 1703 edition to Windows 10 Enterprise edition. So what will the users experience? How will they upgrade their devices?

### Step 1: Join users’ devices to Azure AD

Users can join a device to Azure AD the first time they start the device (during setup), or they can join a device that they already use running Windows 10 Pro, version 1703.

**To join a device to Azure AD the first time the device is started**

1.  During the initial setup, on the **Who owns this PC?** page, select **My organization**, and then click **Next**, as illustrated in **Figure 2**.

    <img src="images/enterprise-e3-who-owns.png" alt="Who owns this PC? page in Windows 10 setup" width="624" height="351" />
    
    **Figure 2. The “Who owns this PC?” page in initial Windows 10 setup**

2.  On the **Choose how you’ll connect** page, select **Join Azure AD**, and then click **Next**, as illustrated in **Figure 3**.

    <img src="images/enterprise-e3-choose-how.png" alt="Choose how you'll connect - page in Windows 10 setup" width="624" height="351" />
    
    **Figure 3. The “Choose how you’ll connect” page in initial Windows 10 setup**

3.  On the **Let’s get you signed in** page, enter the Azure AD credentials, and then click **Sign in**, as illustrated in **Figure 4**.

    <img src="images/enterprise-e3-lets-get.png" alt="Let's get you signed in - page in Windows 10 setup" width="624" height="351" />
    
    **Figure 4. The “Let’s get you signed in” page in initial Windows 10 setup**

Now the device is Azure AD joined to the company’s subscription.

**To join a device to Azure AD when the device already has Windows 10 Pro, version 1703 installed and set up**

>[!IMPORTANT]
>Make sure that the user you're signing in with is **not** a BUILTIN/Administrator. That user cannot use the `+ Connect` button to join a work or school account.

1.  Go to **Settings &gt; Accounts &gt; Access work or school**, as illustrated in **Figure 5**.

    <img src="images/enterprise-e3-connect-to-work-or-school.png" alt="Connect to work or school configuration" width="624" height="482" />
    
    **Figure 5. Connect to work or school configuration in Settings**

2.  In **Set up a work or school account**, click **Join this device to Azure Active Directory**, as illustrated in **Figure 6**.

    <img src="images/enterprise-e3-set-up-work-or-school.png" alt="Set up a work or school account" width="624" height="603" />
    
    **Figure 6. Set up a work or school account**

3.  On the **Let’s get you signed in** page, enter the Azure AD credentials, and then click **Sign in**, as illustrated in **Figure 7**.

    <img src="images/enterprise-e3-lets-get-2.png" alt="Let's get you signed in - dialog box" width="624" height="603" />
    
    **Figure 7. The “Let’s get you signed in” dialog box**

Now the device is Azure AD joined to the company’s subscription.

### Step 2: Sign in using Azure AD account

Once the device is joined to your Azure AD subscription, the user will sign in by using his or her Azure AD account, as illustrated in **Figure 8**. The Windows 10 Enterprise E3 or E5 license associated with the user will enable Windows 10 Enterprise edition capabilities on the device.

<img src="images/enterprise-e3-sign-in.png" alt="Sign in, Windows 10" width="624" height="351" />

**Figure 8. Sign in by using Azure AD account**

### Step 3: Verify that Enterprise edition is enabled

You can verify the Windows 10 Enterprise E3 or E5 subscription in **Settings &gt; Update & Security &gt; Activation**, as illustrated in **Figure 9**.

<span id="win-10-activated-subscription-active"/>
<img src="images/enterprise-e3-win-10-activated-enterprise-subscription-active.png" alt="Windows 10 activated and subscription active" width="624" height="407" />

<BR>**Figure 9 - Windows 10 Enterprise subscription in Settings** <BR>


If there are any problems with the Windows 10 Enterprise E3 or E5 license or the activation of the license, the **Activation** panel will display the appropriate error message or status. You can use this information to help you diagnose the licensing and activation process.

## Virtual Desktop Access (VDA)

Subscriptions to Windows 10 Enterprise are also available for virtualized clients. Windows 10 Enterprise E3 and E5 are available for Virtual Desktop Access (VDA) in Windows Azure or in another [qualified multitenant hoster](https://www.microsoft.com/en-us/CloudandHosting/licensing_sca.aspx).

Virtual machines (VMs) must be configured to enable Windows 10 Enterprise subscriptions for VDA. Active Directory-joined and Azure Active Directory-joined clients are supported. See [Enable VDA for Enterprise Subscription Activation](vda-subscription-activation.md).

## Troubleshoot the user experience

In some instances, users may experience problems with the Windows 10 Enterprise E3 or E5 subscription. The most common problems that users may experience are as follows:

- The existing Windows 10 Pro, version 1703 operating system is not activated.

- The Windows 10 Enterprise E3 or E5 subscription has lapsed or has been removed.

Use the following figures to help you troubleshoot when users experience these common problems:

- [Figure 9](#win-10-activated-subscription-active) (above) illustrates a device in a healthy state, where Windows 10 Pro is activated and the Windows 10 Enterprise subscription is active.

- [Figure 10](#win-10-not-activated) (below) illustrates a device on which Windows 10 Pro is not activated, but the Windows 10 Enterprise subscription is active.

- [Figure 11](#subscription-not-active) (below) illustrates a device on which Windows 10 Pro is activated, but the Windows 10 Enterprise subscription is lapsed or removed.

- [Figure 12](#win-10-not-activated-subscription-not-active) (below) illustrates a device on which Windows 10 Pro license is not activated and the Windows 10 Enterprise subscription is lapsed or removed.

<BR>

<span id="win-10-not-activated"/>
<img src="images/enterprise-e3-win-10-not-activated-enterprise-subscription-active.png" alt="Windows 10 not activated and subscription active" width="624" height="407" />
<BR>**Figure 10 - Windows 10 Pro, version 1703 edition not activated in Settings**<BR>

<BR>

<span id="subscription-not-active"/>
<img src="images/enterprise-e3-win-10-activated-enterprise-subscription-not-active.png" alt="Windows 10 activated and subscription not active" width="624" height="407" />
<BR>**Figure 11 - Windows 10 Enterprise subscription lapsed or removed in Settings**<BR>

<BR>

<span id="win-10-not-activated-subscription-not-active"/>
<img src="images/enterprise-e3-win-10-not-activated-enterprise-subscription-not-active.png" alt="Windows 10 not activated and subscription not active" width="624" height="407" />
<BR>**Figure 12 - Windows 10 Pro, version 1703 edition not activated and Windows 10 Enterprise subscription lapsed or removed in Settings**<BR>


### Review requirements on devices

Devices must be running Windows 10 Pro, version 1703, and be Azure Active Directory joined, or domain joined with Azure AD Connect. Customers who are federated with Azure Active Directory are also eligible. You can use the following procedures to review whether a particular device meets requirements.

**To determine if a device is Azure Active Directory joined:**

1.  Open a command prompt and type **dsregcmd /status**.

2.  Review the output under Device State. If the **AzureAdJoined** status is YES, the device is Azure Active Directory joined.

**To determine the version of Windows 10:**

-   At a command prompt, type:
    **winver**

    A popup window will display the Windows 10 version number and detailed OS build information.

    If a device is running a previous version of Windows 10 Pro (for example, version 1511), it will not be upgraded to Windows 10 Enterprise when a user signs in, even if the user has been assigned a subscription in the CSP portal.