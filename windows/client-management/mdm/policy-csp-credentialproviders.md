---
title: Policy CSP - CredentialProviders
description: Policy CSP - CredentialProviders
ms.author: maricia
ms.topic: article
ms.prod: w10
ms.technology: windows
author: nickbrower
ms.date: 09/29/2017
---

# Policy CSP - CredentialProviders

> [!WARNING]
> Some information relates to prereleased product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.

<hr/>

<!--StartPolicies-->
## CredentialProviders policies  

<dl>
  <dd>
    <a href="#credentialproviders-allowpinlogon">CredentialProviders/AllowPINLogon</a>
  </dd>
  <dd>
    <a href="#credentialproviders-blockpicturepassword">CredentialProviders/BlockPicturePassword</a>
  </dd>
  <dd>
    <a href="#credentialproviders-disableautomaticredeploymentcredentials">CredentialProviders/DisableAutomaticReDeploymentCredentials</a>
  </dd>
</dl>

<hr/>
<!--StartPolicy-->
<a href="" id="credentialproviders-allowpinlogon"></a>**CredentialProviders/AllowPINLogon**  

<!--StartSKU-->
<table>
<tr>
	<th>Home</th>
	<th>Pro</th>
	<th>Business</th>
	<th>Enterprise</th>
	<th>Education</th>
	<th>Mobile</th>
	<th>Mobile Enterprise</th>
</tr>
<tr>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
</tr>
</table>

<!--EndSKU-->
<!--StartScope-->
[Scope](./policy-configuration-service-provider.md#policy-scope):

> [!div class = "checklist"]
> * Device

<hr/>

<!--EndScope-->
<!--StartDescription-->
This policy setting allows you to control whether a domain user can sign in using a convenience PIN.

If you enable this policy setting, a domain user can set up and sign in with a convenience PIN.

If you disable or don't configure this policy setting, a domain user can't set up and use a convenience PIN.

Note: The user's domain password will be cached in the system vault when using this feature.

To configure Windows Hello for Business, use the Administrative Template policies under Windows Hello for Business.

<!--EndDescription-->
> [!TIP]
> This is an ADMX-backed policy and requires a special SyncML format to enable or disable.  For details, see [Understanding ADMX-backed policies](./understanding-admx-backed-policies.md).

> You must specify the data type in the SyncML as &lt;Format&gt;chr&lt;/Format&gt;. For an example SyncML, refer to [Enabling a policy](./understanding-admx-backed-policies.md#enabling-a-policy).

> The payload of the SyncML must be XML-encoded; for this XML encoding, there are a variety of online encoders that you can use. To avoid encoding the payload, you can use CDATA if your MDM supports it.  For more information, see [CDATA Sections](http://www.w3.org/TR/REC-xml/#sec-cdata-sect).

<!--StartADMX-->
ADMX Info:  
-   GP English name: *Turn on convenience PIN sign-in*
-   GP name: *AllowDomainPINLogon*
-   GP path: *System/Logon*
-   GP ADMX file name: *credentialproviders.admx*

<!--EndADMX-->
<!--EndPolicy-->
<hr/>
<!--StartPolicy-->
<a href="" id="credentialproviders-blockpicturepassword"></a>**CredentialProviders/BlockPicturePassword**  

<!--StartSKU-->
<table>
<tr>
	<th>Home</th>
	<th>Pro</th>
	<th>Business</th>
	<th>Enterprise</th>
	<th>Education</th>
	<th>Mobile</th>
	<th>Mobile Enterprise</th>
</tr>
<tr>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /></td>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
</tr>
</table>

<!--EndSKU-->
<!--StartScope-->
[Scope](./policy-configuration-service-provider.md#policy-scope):

> [!div class = "checklist"]
> * Device

<hr/>

<!--EndScope-->
<!--StartDescription-->
This policy setting allows you to control whether a domain user can sign in using a picture password.

If you enable this policy setting, a domain user can't set up or sign in with a picture password.

If you disable or don't configure this policy setting, a domain user can set up and use a picture password.

Note that the user's domain password will be cached in the system vault when using this feature.

<!--EndDescription-->
> [!TIP]
> This is an ADMX-backed policy and requires a special SyncML format to enable or disable.  For details, see [Understanding ADMX-backed policies](./understanding-admx-backed-policies.md).

> You must specify the data type in the SyncML as &lt;Format&gt;chr&lt;/Format&gt;. For an example SyncML, refer to [Enabling a policy](./understanding-admx-backed-policies.md#enabling-a-policy).

> The payload of the SyncML must be XML-encoded; for this XML encoding, there are a variety of online encoders that you can use. To avoid encoding the payload, you can use CDATA if your MDM supports it.  For more information, see [CDATA Sections](http://www.w3.org/TR/REC-xml/#sec-cdata-sect).

<!--StartADMX-->
ADMX Info:  
-   GP English name: *Turn off picture password sign-in*
-   GP name: *BlockDomainPicturePassword*
-   GP path: *System/Logon*
-   GP ADMX file name: *credentialproviders.admx*

<!--EndADMX-->
<!--EndPolicy-->
<hr/>
<!--StartPolicy-->
<a href="" id="credentialproviders-disableautomaticredeploymentcredentials"></a>**CredentialProviders/DisableAutomaticReDeploymentCredentials**  

<!--StartSKU-->
<table>
<tr>
	<th>Home</th>
	<th>Pro</th>
	<th>Business</th>
	<th>Enterprise</th>
	<th>Education</th>
	<th>Mobile</th>
	<th>Mobile Enterprise</th>
</tr>
<tr>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
	<td><img src="images/checkmark.png" alt="check mark" /><sup>3</sup></td>
	<td><img src="images/checkmark.png" alt="check mark" /><sup>3</sup></td>
	<td><img src="images/checkmark.png" alt="check mark" /><sup>3</sup></td>
	<td><img src="images/checkmark.png" alt="check mark" /><sup>3</sup></td>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
	<td><img src="images/crossmark.png" alt="cross mark" /></td>
</tr>
</table>

<!--EndSKU-->
<!--StartScope-->
[Scope](./policy-configuration-service-provider.md#policy-scope):

> [!div class = "checklist"]
> * Device

<hr/>

<!--EndScope-->
<!--StartDescription-->
Added in Windows 10, version 1709. Boolean policy to disable the visibility of the credential provider that triggers the PC refresh on a device. This policy does not actually trigger the refresh. The admin user is required to authenticate to trigger the refresh on the target device.

The Windows 10 Automatic ReDeployment feature allows admin to reset devices to a known good managed state while preserving the management enrollment. After the automatic redeployment is triggered the devices are for ready for use by information workers or students.

- 0 - Enable the visibility of the credentials for Windows 10 Automatic ReDeployment
- 1 - Disable visibility of the credentials for Windows 10 Automatic ReDeployment

<!--EndDescription-->
<!--EndPolicy-->
<hr/>

Footnote:

-   1 - Added in Windows 10, version 1607.
-   2 - Added in Windows 10, version 1703.
-   3 - Added in Windows 10, version 1709.

<!--EndPolicies-->

<!--StartIoTCore-->
## <a href="" id="iotcore"></a>CredentialProviders policies supported by IoT Core  

-   [CredentialProviders/AllowPINLogon](#credentialproviders-allowpinlogon)  
-   [CredentialProviders/BlockPicturePassword](#credentialproviders-blockpicturepassword)  
<!--EndIoTCore-->

