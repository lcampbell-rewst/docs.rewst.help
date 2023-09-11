---
description: >-
  This document outlines the requirements and setup for the Kaseya BMS
  integration.
---

# Kaseya BMS Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

### Setting up the API account

Before configuring the Rewst integration you must generate an API user.

Please refer to [Kaseya's documentation](https://helpdesk.kaseya.com/hc/en-gb/articles/360016897877-BMS-API-Dedicated-API-integration-account-in-PSA) for generating API credentials for your organization if you have not already.

### Configuring the Integration

Once you have created an API account, you will need to configure the integration within the Rewst platform.

Follow the below steps to configure a new integration:

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Click** on the _"Integrations"_ menu on the left sidebar.
3. **Click** on or search for _"Kaseya BMS"_.
4. **Complete** the form with the details you created:
   1. **Tenant**: the name of the company tenant
   2. **Hostname**: Kaseya BMS Server hostname
   3. **Password**: the integrator password
   4. **TOTP Secret**: base32 string used to generate one-time codes
   5. **Username**: This is the unique dedicated service account used to access BMS
5. **Save** the configuration once these have been populated. Rewst will do a quick validation of your input.

Beneath that integration authentication section you will see the following options:

1. **Suggest Values**: This option will attempt to generate mappings between Rewst organizations and child organizations in this integration.
2. **Refresh Options:** This will re-read the potential mapping options - for both organizations and companies in Kaseya BMS.
3. **Save Mappings**: This will apply mapping configuration changes.
