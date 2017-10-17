---
title: Configure endpoint proxy and Internet connection settings
description: Configure the Windows Defender ATP proxy and internet settings to enable communication with the cloud service.
keywords: configure, proxy, internet, internet connectivity, settings, proxy settings, netsh, winhttp, proxy server
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


# Configure endpoint proxy and Internet connectivity settings

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

The Windows Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Windows Defender ATP service.

The embedded Windows Defender ATP sensor runs in system context using the LocalSystem account. The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Windows Defender ATP cloud service.

The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:

 - Auto-discovery methods:
    - Transparent proxy
    - Web Proxy Auto-discovery Protocol (WPAD)

> [!NOTE]
> If you're using Transparent proxy or WPAD in your network topology, you don't need special endpoint configuration settings. For more information on Windows Defender ATP URL exclusions in the proxy, see [Enable access to Windows Defender ATP service URLs in the proxy server](#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server).


 - Manual static proxy configuration:
    - Registry based configuration
    - WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)

## Configure the proxy server manually using a registry-based static proxy
Configure a registry-based static proxy to allow only Windows Defender ATP sensor to report telemetry and communicate with Windows Defender ATP services if a computer is not be permitted to connect to the Internet.

The static proxy is configurable through Group Policy (GP). The group policy can be found under: **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**.

The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.

The registry value `TelemetryProxyServer` takes the following string format:

```text
<server name or ip>:<port>
```
For example: 10.0.0.6:8080

The registry value `DisableEnterpriseAuthProxy` should be set to 1.

## Configure the proxy server manually using netsh command

Use netsh to configure a system-wide static proxy.

> [!NOTE]
> - This will affect all applications including Windows services which use WinHTTP with default proxy.</br>
> - Laptops that are changing topology (for example: from office to home) will malfunction with netsh. Use the registry-based static proxy configuration.

1. Open an elevated command-line:

    a. Go to **Start** and type **cmd**.

    b. Right-click **Command prompt** and select **Run as administrator**.

4. Enter the following command and press **Enter**:
```
netsh winhttp set proxy <proxy>:<port>
```
For example: netsh winhttp set proxy 10.0.0.6:8080

## Enable access to Windows Defender ATP service URLs in the proxy server
If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that the following URLs are white-listed to permit communication with Windows Defender ATP service in port 80 and 443:

Service location | .Microsoft.com DNS record
:---|:---
 US |```*.blob.core.windows.net``` <br>```crl.microsoft.com```<br> ```ctldl.windowsupdate.com```<br> ```us.vortex-win.data.microsoft.com```<br> ```winatp-gw-cus.microsoft.com``` <br> ```winatp-gw-eus.microsoft.com```
Europe |```*.blob.core.windows.net```<br>```crl.microsoft.com```<br>```ctldl.windowsupdate.com```<br>  ```eu.vortex-win.data.microsoft.com```<br>```winatp-gw-neu.microsoft.com```<br> ```winatp-gw-weu.microsoft.com```<br>

 If a proxy or firewall is blocking anonymous traffic, as Windows Defender ATP  sensor is connecting from system context, make sure anonymous traffic is permitted in the above listed URLs.


## Verify client connectivity to Windows Defender ATP service URLs

Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Windows Defender ATP service URLs.

1. Download the [connectivity verification tool](https://go.microsoft.com/fwlink/p/?linkid=823683) to the PC where Windows Defender ATP sensor is running on.

2.  Extract the contents of WDATPConnectivityAnalyzer on the endpoint.

3. Open an elevated command-line:

    a. Go to **Start** and type **cmd**.

    b.  Right-click **Command prompt** and select **Run as administrator**.

4. Enter the following command and press **Enter**:

    ```
    HardDrivePath\WDATPConnectivityAnalyzer.cmd
    ```
    Replace *HardDrivePath* with the path where the WDATPConnectivityAnalyzer tool was downloaded to, for example
    ```
    C:\Work\tools\WDATPConnectivityAnalyzer\WDATPConnectivityAnalyzer.cmd
    ```

5. Extract the *WDATPConnectivityAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.

6. Open *WDATPConnectivityAnalyzer.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs. <br><br>
The tool checks the connectivity of Windows Defender ATP service URLs that Windows Defender ATP client is configured to interact with. It then prints the results into the *WDATPConnectivityAnalyzer.txt* file for each URL that can potentially be used to communicate with the Windows Defender ATP  services. For example:
  ```text
  Testing URL : https://xxx.microsoft.com/xxx
  1 - Default proxy: Succeeded (200)
  2 - Proxy auto discovery (WPAD): Succeeded (200)
  3 - Proxy disabled: Succeeded (200)
  4 - Named proxy: Doesn't exist
  5 - Command line proxy: Doesn't exist              
  ```

If at least one of the connectivity options returns a (200) status, then the Windows Defender ATP client can communicate with the tested URL properly using this connectivity method. <br><br>

However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes). You can then use the URLs in the table shown in [Enable access to Windows Defender ATP service URLs in the proxy server](#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server). The URLs you'll use will depend on the region selected during the onboarding procedure.

## Related topics
- [Configure Windows Defender ATP endpoints](configure-endpoints-windows-defender-advanced-threat-protection.md)
- [Troubleshoot Windows Defender Advanced Threat Protection onboarding issues](troubleshoot-onboarding-windows-defender-advanced-threat-protection.md)
