---
description: >-
  This document outlines the requirements and the setup for the Microsoft CSP
  integration, one of the most complex integrations due to the diversity of
  Microsoft's products and services.
---

# Microsoft CSP Integration Setup

## **Best Practices for Microsoft Integrations**
For best practice information please refer to: [Best Practices for Microsoft Integrations](https://docs.rewst.help/documentation/integrations/cloud/authorization-best-practices)

## **Configuring the Integration**

Follow these steps to configure the integration within the Rewst platform:

* **Log in** to the [Rewst platform](https://app.rewst.io).
* Click on the **"Integrations"** menu on the left sidebar.
* Click on or search for **"CSP"**.
* Click on the integration to **install** it.
* Click on **Authorize**, and follow the prompts to log in.

## **Mapping Clients**

After installation and authentication:

* **Find** the client you want to map and select their domain from the drop-down menu.
* **Click** on the green button next to the mapping to **consent** to delegated access.

{% hint style="warning" %}
When setting up Rewst's CSP integration, you may encounter two enterprise applications within your Azure AD tenant: **Rewst Prod** and **Rewst CSP Connector**.

* **Rewst Prod**: This application is located in your MSP's tenant and in any tenant with direct integration enabled. It may be found in the customer environment if the integration is installed at the customer level.
* **Rewst CSP Connector:** Also known as the CPV API application, this is responsible for making CPV/CSP API for delegated calls. It gets approved CPV permissions by clicking on the shield icon.

**Note:** Different permissions between these applications are normal, and the presence of one or both depends on the integration setup. Refreshing API permissions or clicking re-consent may affect the permissions. For more information on this topic, see Microsoft's documentation on [using the secure application model framework.](https://learn.microsoft.com/en-us/partner-center/developer/secure-app-model-framework)
{% endhint %}
