---
description: This document outlines the requirements and setup for the Sherweb integration.
---

# Sherweb Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

### Setting up the API account

Before configuring the Rewst integration you must generate an API user.

Please refer to [Sherweb's documentation](https://github.com/sherweb/Public-Apis) for generating a Client ID and Client Secret.

You can also follow these instructions:

1. **Open** the Sherweb Partner Portal.
2. **Click** on the APIs menu in the left menu under Security.
3. **Type** the name of your new application and click "Create".

### Configuring the Integration

Once you have created an API account, you will need to configure the integration within the Rewst platform.

Follow the below steps to configure a new integration:

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Click** **on** the _"Integrations"_ menu on the left sidebar.
3. **Click** **on** or search for _"Sherweb"_.
4. **Complete** the form with the details you created:
   1. **Client ID**
   2. **Client Secret**
   3. **Subscription Key**
5. **Save** the configuration.

Rewst will do a quick validation of your input.

To access some API endpoints, you may have to set your rebilling settings within the partner portal or contact your account manager at Sherweb to have them enabled manually.

Beneath that integration authentication section you will see the following options:

1. **Suggest Values**: This option will attempt to generate mappings between Rewst organizations and child organizations in this integration.
2. **Refresh Options**: This will re-read the potential mapping options - for both organizations and companies in Sherweb.
3. **Save Mappings**: This will apply mapping configuration changes.
