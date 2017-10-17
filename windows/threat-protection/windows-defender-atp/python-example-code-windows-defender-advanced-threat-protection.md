---
title: Python code examples for the custom threat intelligence API
description: Use Python code to create custom threat intelligence using REST API.
keywords: python, code examples, threat intelligence, custom threat intelligence, rest api, api
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

# Python code examples for the custom threat intelligence API

**Applies to:**

- Windows 10 Enterprise
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Defender Advanced Threat Protection (Windows Defender ATP)

[!include[Prerelease information](prerelease.md)]

## Before you begin
You must [install](http://docs.python-requests.org/en/master/user/install/#install) the "[requests](http://docs.python-requests.org/en/master/)" python library.

These code examples demonstrate the following tasks:
- [Obtain an Azure AD access token](#token)
- [Create request session object](#session-object)
- [Create calls to the custom threat intelligence API](#calls)
- [Create a new alert definition](#alert-definition)
- [Create a new indicator of compromise](#ioc)

<span id="token" />
## Step 1: Obtain an Azure AD access token
The following example demonstrates how to obtain an Azure AD access token that you can use to call methods in the custom threat intelligence API. After you obtain a token, you have 60 minutes to use this token in calls to the custom threat intelligence API before the token expires. After the token expires, you can generate a new token.

Replace the *auth_url*, *client_id*, and *client_secret* values with the ones you got from **Preferences settings** page in the portal:

```
import json
import requests
from pprint import pprint

auth_url="Your Authorization URL"
client_id="Your Client ID"
client_secret="Your Client Secret"

payload = {"resource": "https://graph.windows.net",
           "client_id": client_id,
           "client_secret": client_secret,
           "grant_type": "client_credentials"}

response = requests.post(auth_url, payload)
token = json.loads(response.text)["access_token"]
```


<span id="session-object" />
## Step 2: Create request session object
Add HTTP headers to the session object, including the Authorization header with the token that was obtained.

```
with requests.Session() as session:
    session.headers = {
        'Authorization': 'Bearer {}'.format(token),
        'Content-Type': 'application/json',
        'Accept': 'application/json'}
```

<span id="calls" />
## Step 3: Create calls to the custom threat intelligence API
After adding HTTP headers to the session object, you can now create calls to the API. The following example demonstrates how you can view all the alert definition entities:

```
    response = session.get("https://ti.securitycenter.windows.com/V1.0/AlertDefinitions")
    pprint(json.loads(response.text))
```

The response is empty on initial use of the API.

<span id="alert-definition" />
## Step 4: Create a new alert definition
The following example demonstrates how you to create a new alert definition.

```
    alert_definition = {"Name": "The alert's name",
                          "Severity": "Low",
                          "InternalDescription": "An internal description of the alert",
                          "Title": "The Title",
                          "UxDescription": "Description of the alerts",
                          "RecommendedAction": "The alert's recommended action",
                          "Category": "Trojan",
                          "Enabled": True}

      response = session.post(
          "https://ti.securitycenter.windows.com/V1.0/AlertDefinitions",
          json=alert_definition)
```

<span id="ioc" />
## Step 5: Create a new indicator of compromise
You can now use the alert ID obtained from creating a new alert definition to create a new indicator of compromise.

```
    alert_definition_id = json.loads(response.text)["Id"]

      ioc = {'Type': "Sha1",
             'Value': "dead1111eeaabbccddeeaabbccddee11ffffffff",
             'DetectionFunction': "Equals",
             'Enabled': True,
             "AlertDefinition@odata.bind": "AlertDefinitions({0})".format(alert_definition_id)}

      response = session.post(
          "https://ti.securitycenter.windows.com/V1.0/IndicatorsOfCompromise",
          json=ioc)
```

## Complete code
You can use the complete code to create calls to the API.

```syntax
import json
import requests
from pprint import pprint

auth_url="Your Authorization URL"
client_id="Your Client ID"
client_secret="Your Client Secret"

payload = {"resource": "https://graph.windows.net",
           "client_id": client_id,
           "client_secret": client_secret,
           "grant_type": "client_credentials"}

response = requests.post(auth_url, payload)
token = json.loads(response.text)["access_token"]

with requests.Session() as session:
    session.headers = {
        'Authorization': 'Bearer {}'.format(token),
        'Content-Type': 'application/json',
        'Accept': 'application/json'}

    response = session.get("https://ti.securitycenter.windows.com/V1.0/AlertDefinitions")
    pprint(json.loads(response.text))

    alert_definition = {"Name": "The alert's name",
                        "Severity": "Low",
                        "InternalDescription": "An internal description of the alert",
                        "Title": "The Title",
                        "UxDescription": "Description of the alerts",
                        "RecommendedAction": "The alert's recommended action",
                        "Category": "Trojan",
                        "Enabled": True}

    response = session.post(
        "https://ti.securitycenter.windows.com/V1.0/AlertDefinitions",
        json=alert_definition)

    alert_definition_id = json.loads(response.text)["Id"]

    ioc = {'Type': "Sha1",
           'Value': "dead1111eeaabbccddeeaabbccddee11ffffffff",
           'DetectionFunction': "Equals",
           'Enabled': True,
           "AlertDefinition@odata.bind": "AlertDefinitions({0})".format(alert_definition_id)}

    response = session.post(
        "https://ti.securitycenter.windows.com/V1.0/IndicatorsOfCompromise",
        json=ioc)

    pprint(json.loads(response.text))
```


>Want to experience Windows Defender ATP? [Sign up for a free trial.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-pyexample-belowfoldlink) 


## Related topics
- [Understand threat intelligence concepts](threat-indicator-concepts-windows-defender-advanced-threat-protection.md)
- [Create custom alerts using the threat intelligence API](custom-ti-api-windows-defender-advanced-threat-protection.md)
- [Enable the custom threat intelligence API in Windows Defender ATP](enable-custom-ti-windows-defender-advanced-threat-protection.md)
- [PowerShell code examples for the custom threat intelligence API](powershell-example-code-windows-defender-advanced-threat-protection.md)
- [Experiment with custom threat intelligence alerts](experiment-custom-ti-windows-defender-advanced-threat-protection.md)
- [Troubleshoot custom threat intelligence issues](troubleshoot-custom-ti-windows-defender-advanced-threat-protection.md)
