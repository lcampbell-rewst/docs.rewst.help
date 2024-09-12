# IT Glue Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

{% hint style="warning" %}
IT Glue's API access is limited to users of the legacy **Classic** (pre 2018) and **Enterprise** level plans only. See **\[yourdomain].itglue.com/account/plan** for details on your organization's plan and usage.

For more information on IT Glue's plans and pricing review the [IT Glue pricing page](https://www.itglue.com/pricing/).
{% endhint %}

Integrating Rewst with IT Glue brings powerful documentation capabilities to your applications, enhancing IT knowledge management and streamlining workflows. With the integration, Rewst users can seamlessly access and collaborate on IT Glue's documentation repository, gaining centralized access to critical information, configurations, and processes. By leveraging IT Glue's robust documentation features, Rewst users can improve efficiency, ensure consistency, and enhance IT service delivery. This integration empowers IT teams to leverage the collective knowledge and expertise stored in IT Glue, enabling them to troubleshoot issues, onboard new team members, and deliver exceptional IT support through Rewst's integrated platform.

## Setup

1. **Generate** an API key in IT Glue by referring to the [IT Glue documentation](https://helpdesk.kaseya.com/hc/en-gb/articles/4407484149265-Getting-started-with-the-IT-Glue-API).
2. **Navigate** to the integrations page in Rewst.
3. **Click** on the IT Glue integration.
4. **Fill out** the configuration form.
5. **Click** on the Save Configuration button.

## Generating an API key

All API endpoints require authentication using a private API key. You can generate one or more API keys for your account. To generate a new API key:

1. **Navigate** to Account → Settings.
   * You will need to be a User with an Administrator role.
2. **Click** on API Keys → Custom API Keys.
3. **Enter** a name for the key.&#x20;
4. **Click** Generate API Key.&#x20;
   * You will not be able to view a key again after it has been generated.

{% hint style="danger" %}
For security, an optional Password Access setting is provided for each API key. Password values can be accessed from the Passwords API only if this setting is enabled. Note that Rewst will need Password Access to be enabled for full functionality.
{% endhint %}

<figure><img src="../../../../.gitbook/assets/2023-09-13_12-10-34.png" alt=""><figcaption></figcaption></figure>
