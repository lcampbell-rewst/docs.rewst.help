---
description: >-
  This document outlines the requirements and setup for the ConnectWise Manage
  integration.
---

# ConnectWise Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

## Requirements (pre-Rewst)

There are a few requirements for the ConnectWise Manage integration to work that need configuring by you as the MSP.

Rewst has a number of tasks that can be performed using the ConnectWise Manage API, all of which require different permissions. You can review the [ConnectWise Manage Security Roles Matrix](https://developer.connectwise.com/@api/deki/files/422/Security\_Roles\_Matrix\_11132017.xlsx?revision=1) for more information.

{% hint style="info" %}
You will need an active CW Developer account to access the above URL.
{% endhint %}

### Creating a Security Role

1. **Go to** System -> Security Roles -> Click the + in the top Left.
2. **Name** the Security Role "Rewst API" -> Click the save icon.
3. **Set** your permission as per [this document](least-privilege-access-requirements-for-connectwise-manage-integration.md).

### API Account

In order to create a new ConnectWise Manage integration, you will need to create an API account. This can be done by [following the instructions](https://developer.connectwise.com/Products/Manage/Developer\_Guide/Authentication).

#### Creating an API Member

1. **Navigate to** System -> Members -> Api Members in ConnectWise Manage.
2. **Create** a new API member by clicking +.
3. **Create** a Member ID and Member Name.
   1. We recommend naming these "Rewst"
4. **Select** Rewst API as your Role ID.
5. **Select** Your Highest Level such as _Corporate (Level 1)._
6. **Select** a Location, Department, Name, and Default Territory as per your company guidelines.
7. **Click** the Save Icon at the Top.

<figure><img src="../../../../.gitbook/assets/cwm-api-member.jpg" alt=""><figcaption><p>Creating an API Member in ConnectWise Manage</p></figcaption></figure>

8. **Click** on the Rewst API member.
9. **Click** API Keys -> "+".
10. **Add** a new API Key.
11. **Add** Rewst API as the Description.
12. **Click** the Save Icon.
13. **Save** the public and private key in a secure location.

<figure><img src="../../../../.gitbook/assets/public-api-key.jpg" alt=""><figcaption><p>Public and Private Key</p></figcaption></figure>



### Integration

Once you have created an API account, you will need to configure the integration within the Rewst platform.

Follow the below steps to configure a new integration:

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Navigate to** Configuration -> Integrations.
3. **Click** or **search** for "ConnectWise Manage".
4. **Enter** the API Member ID.
5. **Add** the company ID used when logging into ConnectWise Manage.
6. **Add** the Hostname for ConnectWise Manage.
7. **Add** the Private & Public API Key.
   1. (Optional) Change the Company Query Conditions to filter what companies are returned by the API
8. **Click** Save Configuration.

<figure><img src="../../../../.gitbook/assets/cwm-rewst-integration-setup.jpg" alt=""><figcaption><p>Configuring ConnectWise Manage Integration in Rewst</p></figcaption></figure>

{% hint style="warning" %}
**Other Configurations**

Once the integration has been configured within Rewst, we can use the Rewst Crate: Configure Organization Variables to configure your own custom settings and how Rewst should interact with ConnectWise Manage. Our Guide for that crate can be found here: [_Configure Organization Variable_](https://docs.rewst.help/prebuilt-automations/existing-crate-documentation/configure-organization-variables)[_s_](../../../../prebuilt-automations/existing-crate-documentation/configure-organization-variables.md)

Note that this form asks for information about your RMM / M365 settings as well. Whilst this form can be completed again separately, it is recommended that you also set up the integration for Microsoft Graph and your RMM.
{% endhint %}



1.
