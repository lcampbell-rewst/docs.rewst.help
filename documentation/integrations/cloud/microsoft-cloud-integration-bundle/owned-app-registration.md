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
* **Enhanced Security Control:** You need control over the application for security purposes.
* **Utilization of Existing Applications:** You wish to integrate with already existing applications.

***

## **Configuration Instructions**

{% hint style="info" %}
Below is a high-level walkthrough of what you need to configure your owned app in Rewst. For detailed instructions and additional support on registering/managing your own apps, refer to Microsoft's[ Guide to registering an application with the Microsoft identity platform](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app).
{% endhint %}

1. **Access the Azure Portal:**
   * Log into your [Microsoft Entra Admin Center](https://entra.microsoft.com/).
   * Navigate to **Identity** -> **Applications** -> **App Registrations**.
2. **Create or Select an App Registration:**
   * To create a new app, click **New registration**.
   * To use an existing app, select one from the **Owned applications** list.
3. **Configure Redirect URL:**
   * To ensure Rewst can communicate with your app registration after authentication, and receive security tokens post-authentication, set the redirect URI to `https://engine.rewst.io/integrations/bundles/microsoft_cloud/callback`
4. **Gather Essential Information:**
   * Note the **Client ID** & Generate a **Client Secret** under **Certificates & secrets**.
   * Enter these credentials when configuring the application in Rewst.
5. **Decide the Auth Subject:**
   * Select **common** if your app registration is accessible across multiple tenants.
   * Choose **Tenant ID** if your registration is restricted to your own tenant, and ensure this ID is included in the **Tenant ID** field to generate the correct authentication URL.

***
