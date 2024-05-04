---
description: >-
  How to bring your own application permissions. Ideal for organizations with
  specific compliance or operational requirements needing more control than what
  the native Rewst Cloud Connector provides
---

# Owned App Registration

***

## Overview

Using an Owned App Registration created within your Microsoft tenant allows for tailored configuration and security settings. **This is an advanced configuration option for users proficient within their Entra environment and need customized control over their Microsoft integrations.**

Some example reasons for this could be:

* You require API access or special permissions not available via Rewst's Cloud Connector.
* You require control over the used application for security purposes.
* You wish to use an existing application to minimize the deployed applications.

***

{% hint style="info" %}
We've surfaced some high-level guidance below. For additional details or questions related to registering and managing your own applications, please refer to [Microsoft's QuickStart Guide: Registering an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).
{% endhint %}

***

## **Configuration Instructions**

1. **Access the Azure Portal:** Log into your [Microsoft Entra Admin Center](https://entra.microsoft.com). Under `Identity` click `Applications` -> `App Registrations`
2. **Create or Select an App Registration:** If you haven’t already, click `New registration` to create a new application or select an existing one from the `Owned applications` list.
3. **Configure Redirect URL**: A _redirect URI_ is the location where the Microsoft identity platform redirects a user's client and sends security tokens after authentication. To ensure Rewst can communicate with your App Registration after authentication, set this to: `https://engine.rewst.io/integrations/bundles/microsoft_cloud/callback`
4. **Gather Information:** note the `Client ID`, and generate a `Client Secret` under `Certificates & secrets` for inputting into Rewst fields.
5. **Clarify Single vs. Multi-tenant:** For the the `Auth Subject` field, choose between:
   * `common` if your app registration is set to be accessible from multiple tenants.
   * `Tenant ID` if your app registration is restricted to your own tenant.

{% hint style="info" %}
When using an owned App Registration with the `tenant_id` Auth Subject, **make sure you include the ID in the Tenant ID field**. This will be what Rewst uses to generate the authentication URL.
{% endhint %}

***
