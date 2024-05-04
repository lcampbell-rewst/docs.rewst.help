---
description: >-
  How to leverage your own application permissions for customized integration
  control.
---

# Owned App Registration

***

## **Overview**

Owned App Registration within your Microsoft tenant allows for a tailored configuration and heightened security settings. This advanced option is **suited for users with proficiency in their Microsoft Entra environment** who require custom control over their Microsoft integrations.

## **Reasons to Choose Owned App Registration**

* **Specialized Access:** Your requirements are not natively met via Rewst's Cloud Connector.
* **Enhanced Security Control:** You need control over the used application for security purposes.
* **Utilization of Existing Applications:** You wish to integrate with already existing applications.

***

{% hint style="info" %}
This is a high-level walkthrough of what you need to configure your owned app in Rewst. For detailed instructions and additional support on registering/managing your own apps, refer to Microsoft's[ Guide to registering an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).
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

***

{% hint style="info" %}
When using an owned App Registration with the `tenant_id` Auth Subject, **make sure you include the ID in the Tenant ID field**. This will be what Rewst uses to generate the authentication URL.
{% endhint %}

***
