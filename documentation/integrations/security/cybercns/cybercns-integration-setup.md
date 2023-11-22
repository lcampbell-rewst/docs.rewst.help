---
description: >-
  This document outlines the requirements and setup for the ConnectSecure
  (previously CyberCNS) integration.
---

# ConnectSecure Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

## **Getting Started with ConnectSecure**

* **Tenant Name**: `msp_domain`
* **Base URL**: `portaluseast2.mycybercns.com`
* **API Login Endpoint**: `/api/{{ tenant name }}/login`
* **API Documentation**: Accessible in the [CyberCNS Fast API Docs](https://portaluseast2.mycybercns.com/docs).

## Setting up the API account

1. **Log in** to the [CyberCNS Portal](https://portal.mycybercns.com/login).
2. **Switch** to `Global View` on the top right.
3. **Navigate** to `Users` on the left sidebar.
4. **Create** a new user for API access with the `Admin` role.
5. **Click** the `Actions` button and choose the API key.
6. **Copy** `Client ID` and `Client Secret`**.**

## Configuring the Integration

1. **Log in** to your [Rewst account](https://app.rewst.io/).
2. **Click** on the `Integrations` menu on the left sidebar.
3. **Click** on or search for `ConnectSecure`.
4. **Enter** the `Base URL` or hostname that is used to access the portal.
5. **Enter** your collected `Client ID`**,** `Tenant Name`**,** and `Client Secret`**.**

## **Additional Configuration Options**

* **Suggest Values**: Generates mappings between Rewst organizations and corresponding entities in ConnectSecure.
* **Suggest Values**: This option will attempt to generate mappings between Rewst organizations and child organizations in this integration.
* **Refresh Options:** This will re-read the potential mapping options - for both organizations and companies in ConnectSecure.
