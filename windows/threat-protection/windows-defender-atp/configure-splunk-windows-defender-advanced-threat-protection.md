---
title: Configure Splunk to pull Windows Defender ATP alerts
description: Configure Splunk to receive and pull alerts from the Windows Defender ATP portal.
keywords: configure splunk, security information and events management tools, splunk
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

# Configure Splunk to pull Windows Defender ATP alerts

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configuresplunk-abovefoldlink) 

You'll need to configure Splunk so that it can pull Windows Defender ATP alerts.

## Before you begin

- Install the [REST API Modular Input app](https://splunkbase.splunk.com/app/1546/) in Splunk.
- Make sure you have enabled the **SIEM integration** feature from the **Preferences setup** menu. For more information, see [Enable SIEM integration in Windows Defender ATP](enable-siem-integration-windows-defender-advanced-threat-protection.md)

- Have the details file you saved from enabling the **SIEM integration** feature ready. You'll need to get the following values:
  - OAuth 2 Token refresh URL
  - OAuth 2 Client ID
  - OAuth 2 Client secret

- Have the refresh token that you generated from the SIEM integration feature ready.

## Configure Splunk

1. Login in to Splunk.

2. Click **Search & Reporting**, then **Settings** > **Data inputs**.

3. Click **REST** under **Local inputs**.

  NOTE:
  This input will only appear after you install the [REST API Modular Input app](https://splunkbase.splunk.com/app/1546/).

4. Click **New**.

5. Type the following values in the required fields, then click **Save**:

  NOTE:
  All other values in the form are optional and can be left blank.

  <table>
  <tbody style="vertical-align:top;">
  <tr>
  <th>Field</th>
  <th>Value</th>
  </tr>
  <tr>
  <td>Endpoint URL</td>
  <td>Depending on the location of your datacenter, select either the EU or the US URL: </br></br> **For EU**:  `https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts`</br>**For US:**` https://wdatp-alertexporter-us.securitycenter.windows.com/api/alerts`
  </tr>
  <tr>
  <td>HTTP Method</td>
  <td>GET</td>
  </tr>
  <td>Authentication Type</td>
  <td>oauth2</td>
  <tr>
  <td>OAuth 2 Access token</td>
  <td>Use the value that you generated when you enabled the SIEM integration feature. </br></br> NOTE: The access token expires after an hour. </td>
  </tr>
  <tr>
  <td>OAuth 2 Refresh Token</td>
  <td>Use the value that you generated when you enabled the **SIEM integration** feature.</td>
  </tr>
  <tr>
  <td>OAuth 2 Token Refresh URL</td>
  <td>Use the value from the details file you saved when you enabled the **SIEM integration** feature.</td>
  </tr>
  <tr>
  <td>OAuth 2 Client ID</td>
  <td>Use the value from the details file you saved when you enabled the **SIEM integration** feature.</td>
  </tr>
  <tr>
  <td>OAuth 2 Client Secret</td>
  <td>Use the value from the details file you saved when you enabled the **SIEM integration** feature.</td>
  </tr>
  <tr>
  <td>Response type</td>
  <td>Json</td>
  </tr>
  <tr>
  <td>Response Handler</td>
  <td>JSONArrayHandler</td>
  </tr>
  <tr>
  <td>Polling Interval</td>
  <td>Number of seconds that Splunk will ping the Windows Defender ATP endpoint. Accepted values are in seconds.</td>
  </tr>
  <tr>
  <td>Set sourcetype</td>
  <td>From list</td>
  </tr>
  <tr>
  <td>Source type</td>
  <td>\_json</td>
  </tr>
  </tr>
  </table>

After completing these configuration steps, you can go to the Splunk dashboard and run queries.

## View alerts using Splunk solution explorer
Use the solution explorer to view alerts in Splunk.

1. In Splunk, go to **Settings** > **Searchers, reports, and alerts**.

2. Select **New**.

3. Enter the following details:
  - Destination app: Select Search & Reporting (search)
  - Search name: Enter a name for the query
  - Search: Enter a query, for example:</br>
    `source="rest://windows atp alerts"|spath|table*`

    Other values are optional and can be left with the default values.
4. Click **Save**. The query is saved in the list of searches.

5. Find the query you saved in the list and click **Run**. The results are displayed based on your query.


## Related topics
- [Enable SIEM integration in Windows Defender ATP](enable-siem-integration-windows-defender-advanced-threat-protection.md)
- [Configure ArcSight to pull Windows Defender ATP alerts](configure-arcsight-windows-defender-advanced-threat-protection.md)
- [Windows Defender ATP alert API fields](api-portal-mapping-windows-defender-advanced-threat-protection.md)
- [Pull Windows Defender ATP alerts using REST API](pull-alerts-using-rest-api-windows-defender-advanced-threat-protection.md)
- [Troubleshoot SIEM tool integration issues](troubleshoot-siem-windows-defender-advanced-threat-protection.md)
