---
description: >-
  This document outlines the requirements and setup for the CyberCNS
  integration.
---

# CyberCNS Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

## Setting up the API account

1. **Log in** to the CyberCNS Portal.
2. **Switch** to Global View on the top right.
3. **Navigate** to Users on the left sidebar.
4. **Create** a new user for API access with the Admin role.
5. **Click** the "Actions" button and choose the API key.
6. **Copy** **Client ID** and **Client Secret.**

## Configuring the Integration

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Click** on the _"Integrations"_ menu on the left sidebar.
3. **Click** on or search for _"CyberCNS"_.
4. **Enter** the URL for the hostname that is used to access the CyberCNS Portal. (Example: portaluseast2.mycybercns.com).
5. **Enter** your **Client ID.**
6. **Enter** your **Tenant Name** ('Domain' value used when logging in).
7. **Enter** your **Client Secret.**

Beneath that integration authentication section you will see the following options:

1. **Suggest Values**: This option will attempt to generate mappings between Rewst organizations and child organizations in this integration.
2. **Refresh Options:** This will re-read the potential mapping options - for both organizations and companies in CyberCNS.
3. **Save Mappings:** This will apply mapping configuration changes.
