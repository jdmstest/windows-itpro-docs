---
title: Assign user access to the Windows Defender ATP portal
description: Assign read and write or read only access to the Windows Defender Advanced Threat Protection portal.
keywords: assign user roles, assign read and write access, assign read only access, user, user roles, roles
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

# Assign user access to the Windows Defender ATP portal
**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Azure Active Directory
- Office 365
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Windows Defender ATP users and access permissions are managed in Azure Active Directory (AAD). Use the following methods to assign security roles.

## Assign user access using Azure PowerShell
You can assign users with one of the following levels of permissions:
- Full access (Read and Write)
- Read only access

### Before you begin
- Install Azure PowerShell. For more information see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).<br>

    > [!NOTE]
    > You need to run the PowerShell cmdlets in an elevated command-line.

- Connect to your Azure Active Directory. For more information see, [Connect-MsolService](https://msdn.microsoft.com/library/dn194123.aspx).



**Full access** <br>
Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.
Assigning full access rights requires adding the users to the “Security Administrator” or “Global Administrator” AAD built-in roles.

**Read only access** <br>
Users with read only access can log in, view all alerts, and related information.
They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.
Assigning read only access rights requires adding the users to the “Security Reader” AAD built-in role.

Use the following steps to assign security roles:

- For **read and write** access, assign users to the security administrator role by using the following command:
```text
Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
```
- For **read only** access, assign users to the security reader role by using the following command:
```text
Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress “reader@Contoso.onmicrosoft.com”
```

For more information see, [Manage Azure AD group and role membership](https://technet.microsoft.com/library/321d532e-407d-4e29-a00a-8afbe23008dd#BKMK_ManageGroups).

## Assign user access using the Azure portal

1.	Go to the [Azure portal](https://portal.azure.com).

2.	Select **Azure Active Directory**.

3.  Select **Manage** > **Users and groups**.

4.  Select **Manage** > **All users**.

5.	Search or select the user you want to assign the role to.

6.	Select **Manage** > **Directory role**.

7.	Under **Directory role**, select **Limited administrator**, then **Security Reader** or **Security Administrator**.

![Image of Microsoft Azure portal](images/atp-azure-ui-user-access.png)


>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-portalaccess-belowfoldlink)
