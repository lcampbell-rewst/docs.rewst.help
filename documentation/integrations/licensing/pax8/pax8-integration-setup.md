---
description: This document outlines the requirements and setup for the Pax8 integration.
---

# Pax8 Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

### Getting the Client ID and Client Secret from Pax8

1. **Log in** to your Pax8 account.

<figure><img src="../../../../.gitbook/assets/pax8-login.png" alt=""><figcaption></figcaption></figure>

2. **Click** on your account at the top right.

<figure><img src="../../../../.gitbook/assets/pax-8-user-account.png" alt=""><figcaption></figcaption></figure>

3. **Click** on Users in the left-hand menu.

<figure><img src="../../../../.gitbook/assets/pax-users.png" alt=""><figcaption></figcaption></figure>

4. **Go to** the _Integrations_ section.

<figure><img src="../../../../.gitbook/assets/pax-integrations.png" alt=""><figcaption></figcaption></figure>

5. **Click** _Create_ at the top right of the _Integrations_ section.
   * It may ask you to accept the Pax8 API terms of service. Accept these to move forward.
6. **Type** _Rewst_ for the Developer App Name.

<figure><img src="../../../../.gitbook/assets/pax8-developer-app-name.png" alt=""><figcaption></figcaption></figure>

7. **Click** Create to get this view.

<figure><img src="../../../../.gitbook/assets/pax8-client-id-secret.png" alt=""><figcaption></figcaption></figure>

8. **Copy** the Client ID and Client Secret.

***

## Configuring the Integration in Rewst

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Click** on the _Integrations_ menu on the left sidebar.
3. **Click** on or search for _Pax8_.
4. **Add** the Client ID and Client Secret to the form.

<figure><img src="../../../../.gitbook/assets/pax8-in-rewst.png" alt=""><figcaption></figcaption></figure>

5. **Click** _Save Configuration_ at the bottom right.

Beneath that integration authentication section you will see the following options:

1. **Suggest Values**: This option will attempt to generate mappings between Rewst organizations and child organizations in this integration.
2. **Refresh Options**: This will re-read the potential mapping options - for both organizations and companies in Pax8.
3. **Save Mappings**: This will apply mapping configuration changes.

Once saved, Rewst will do a quick validation of your input. Now you can make use of Pax8 actions in your workflows!
