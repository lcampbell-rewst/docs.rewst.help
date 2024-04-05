---
description: >-
  This document outlines the requirements and the setup for the Microsoft CSP
  integration, one of the most complex integrations due to the diversity of
  Microsoft's products and services.
---

# Microsoft CSP Integration Setup

{% hint style="warning" %}
**New: Microsoft Cloud Integration Bundle!** 🌟 We've combined our Microsoft integrations into a single, streamlined package for easier management and enhanced security. While individual integration guides are still here, we recommend checking out the new bundle for a simplified setup. Learn more on the [Microsoft Cloud Integration Bundle](../microsoft-cloud-integration-bundle-documentation/) page.
{% endhint %}

## **Best Practices for Microsoft Integrations**

For best practice information please refer to: [Best Practices for Microsoft Integrations](https://docs.rewst.help/documentation/integrations/cloud/authorization-best-practices).

{% hint style="success" %}
For more information on setting the GDAP user in Rewst check out the [rewst-user-setup-and-gdap-relationship-guidance.md](rewst-user-setup-and-gdap-relationship-guidance.md "mention")article.&#x20;
{% endhint %}

## **Configuring the Integration**

Follow these steps to configure the integration within the Rewst platform:

* **Log in** to the [Rewst platform](https://app.rewst.io).
* Click on the **"Integrations"** menu on the left sidebar.
* Click on or search for **"CSP"**.
* Click on the integration to **install** it.
* Click on **Authorize**, and follow the prompts to log in.

## **Mapping Clients**

After completing the installation and authentication processes:

1. **Locate the Desired Client**: Search for the client you intend to map. Once located, choose their name from the provided drop-down menu.
2. **Consent to Delegated Access**: Next to the mapping, there is a green button. Clicking on this will consent to delegated access for the selected client.

{% hint style="warning" %}
When you're in the process of setting up Rewst's CSP integration, it's possible to come across two distinct enterprise applications within your Azure AD tenant: **`Rewst Prod`** and **`Rewst CSP Connector.`** Removing this integration and readding it results in the deletion of the old service principal, and a creation of a new one upon reconsent.

* **Rewst Prod**: This application is present in your MSP's tenant. Moreover, in scenarios where there is direct integration, it might also appear in other tenants. If the integration is configured directly at the customer level, expect to see this application.
* **Rewst CSP Connector**: At times, this is known as the CPV API application. It is the application tasked with carrying out delegated calls using the CPV/CSP API. _When you press the shield icon, you are effectively giving consent_, which leads to the creation of the enterprise application in the client's tenant. Once established, the required permissions are assigned to this application.

**Note**: It's expected to see different permissions levels between these applications. Their presence, whether singularly or together, depends on the specific integration setup. Altering API permissions or deciding to re-consent can potentially change these permissions. For an in-depth understanding, refer to Microsoft's detailed guide on [using the secure application model framework.](https://learn.microsoft.com/en-us/partner-center/developer/secure-app-model-framework)
{% endhint %}
