---
description: >-
  This document outlines the requirements and the setup for the Microsoft CSP
  integration, one of the most complex integrations due to the diversity of
  Microsoft's products and services.
---

# Microsoft CSP Integration Setup

{% hint style="warning" %}
**New: Microsoft Cloud Integration Bundle!** 🌟 We've combined our Microsoft integrations into a single, streamlined package for easier management and enhanced security. While individual integration guides are still here, we recommend checking out the new bundle for a simplified setup. Learn more on the [Microsoft Cloud Integration Bundle](../) page.
{% endhint %}

## **Introduction**

The Microsoft CSP integration within the Rewst Microsoft Cloud Integration Bundle enhances the management of Cloud Solution Provider relationships and services. It simplifies the delegation and management of permissions across customer tenants, offering streamlined access to manage and administer Microsoft services.

## **Key Features**

* **Delegated Admin Permissions**: Manage CSP services with delegated permissions, simplifying customer management.
* **Efficient Client Mapping**: Easily map CSP clients to Rewst organizations to maintain clear and organized client management.
* **Seamless Service Integration**: Integrates closely with other Microsoft services for a cohesive management experience.

## **Setup Instructions**

### **Step 1: Access the Integration Bundle**

* Log into the Rewst dashboard.
* Navigate to `Integrations` and select the `Microsoft Cloud Integration Bundle`.

### **Step 2: Select CSP Integration**

* Choose `Microsoft CSP` from the `Select Integrations` list, along with any other Microsoft services you wish to configure.
* Click `Next` to proceed.

### **Step 3: Configure Authentication and Permissions**

* On the configuration parameters page, select your authentication app registration method from:
  * **Rewst Microsoft Cloud Connector**: Recommended for streamlined integration.
  * **Owned App Registration**: For users with their own setups who wish to use their app registrations.
  * **Legacy Rewst App (Deprecated)**: Not recommended and being phased out.

### **Step 4: Setup CSP-Specific Permissions**

* You will be presented with a list of necessary permissions for Microsoft CSP, which typically includes user impersonation permissions to manage CSP functions.
* Click `Next` to proceed to the authorization step.

{% hint style="info" %}
For more information on CSP Permissions See the [#microsoft-csp-permissions](../microsoft-cloud-permissions.md#microsoft-csp-permissions "mention")section of the [microsoft-cloud-permissions.md](../microsoft-cloud-permissions.md "mention") page
{% endhint %}

### **Step 5: Authorize Integration**

* In the `Authorize Integrations` step, click the `Authorize` button to open a Microsoft login window for authentication.
* Follow the on-screen prompts to complete the authorization process, using the same account as used for other Microsoft service integrations if necessary.

## **Managing Client Mappings and Delegated Access**

* **Locate Desired Client**: Search for the client you intend to map within the Rewst platform. Once located, select their name from a drop-down menu.
* **Consent to Delegated Access**: Click next to the client mapping to consent to delegated access for the selected client, facilitating the management of their CSP services under your administration.

## **Troubleshooting Tips**

* **Authorization Issues**: Ensure that you are using the correct account and that all permissions are properly configured before authorization.
* **Client Mapping Errors**: If issues arise during client mapping, ensure that client details are correct and that they are properly registered in the CSP portal.

{% hint style="info" %}
* For more information on setting the GDAP user in Rewst check out the [rewst-user-setup-and-gdap-relationship-guidance.md](rewst-user-setup-and-gdap-relationship-guidance.md "mention")article.&#x20;
* For troubleshooting tips, check out the [troubleshooting-installation-issues.md](../troubleshooting-installation-issues.md "mention") and [common-issues-with-microsoft-bundle](../common-issues-with-microsoft-bundle/ "mention") pages.
{% endhint %}

## **Best Practices for Microsoft Integrations**

For best practice information please refer to: [Best Practices for Microsoft Integrations](https://docs.rewst.help/documentation/integrations/cloud/authorization-best-practices).
