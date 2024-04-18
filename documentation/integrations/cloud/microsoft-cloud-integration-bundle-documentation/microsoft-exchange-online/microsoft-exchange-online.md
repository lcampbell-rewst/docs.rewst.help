---
description: >-
  Microsoft Exchange Online provides access to Microsoft Exchange Online
  resources (i.e. Mailboxes, Distribution Groups, etc.).
---

# Microsoft Exchange Online

{% hint style="warning" %}
**New: Microsoft Cloud Integration Bundle!** 🌟 We've combined our Microsoft integrations into a single, streamlined package for easier management and enhanced security. While individual integration guides are still here, we recommend checking out the new bundle for a simplified setup. Learn more on the [Microsoft Cloud Integration Bundle](../) page.
{% endhint %}

## **Introduction**

The Microsoft Exchange Online integration in the Rewst Microsoft Cloud Integration Bundle provides advanced email and calendar management capabilities. This integration simplifies the administration of Exchange services, enhancing productivity and security within your organization.

## **Key Features**

* **Advanced Email Management**: Manage user mailboxes, settings, and security policies efficiently.
* **Enhanced Calendar Capabilities**: Facilitate better scheduling and calendar sharing across your organization.
* **Seamless Integration**: Works closely with other Microsoft services for a cohesive management experience, particularly with Microsoft Graph for enhanced functionality.

## **Setup Instructions**

### **Step 1: Access the Integration Bundle**

* Log into the Rewst dashboard.
* Navigate to 'Integrations' and select the 'Microsoft Cloud Integration Bundle'.

### **Step 2: Select Exchange Online Integration**

* Choose 'Microsoft Exchange Online' from the 'Select Integrations' list, along with any other services you wish to configure such as Microsoft CSP or Microsoft Graph.
* Click 'Next' to proceed.

### **Step 3: Configure Authentication and Permissions**

* On the configuration parameters page, select your authentication app registration method from:
  * **Rewst Microsoft Cloud Connector**: Recommended for most users for streamlined integration.
  * **Owned App Registration**: For those with an existing setup who prefer to use their own app registrations.
  * **Legacy Rewst App (Deprecated)**: Not recommended; being phased out.
* Continue to configure the necessary permissions for Microsoft Exchange Online.

### **Step 4: Setup Exchange-Specific Permissions**

* You will see a list of necessary permissions for Microsoft Exchange Online, which typically includes:
  * **Exchange.Manage**: Manage general features and settings.
  * **Exchange.ManageAsApp**: Manage Exchange features at the app level.
  * **Full\_Access\_As\_App**: Grant full access to the app to manage Exchange.
* Click `Next` to move to the authorization step.

{% hint style="info" %}
For more information on Exchange Permissions[#microsoft-exchange-online-permissions](../microsoft-cloud-permissions.md#microsoft-exchange-online-permissions "mention") section of the [microsoft-cloud-permissions.md](../microsoft-cloud-permissions.md "mention") page
{% endhint %}

### **Step 5: Authorize Integration**

* In the `Authorize Integrations` section, click the `Authorize` button. This will open a Microsoft login window for authentication.
* Follow the on-screen prompts to complete the authorization process, ensuring to use the same account as used for other Microsoft service integrations if necessary.

## **Troubleshooting Tips**

* **Authorization Issues**: If you encounter problems during the authorization step, ensure that you are using the correct account and that all permissions are properly set.
* **Permission Configuration Errors**: Double-check the permissions if there are issues with accessing certain functionalities. Ensure that the appropriate permissions are enabled and correctly configured.

{% hint style="info" %}
For troubleshooting tips, check out the [troubleshooting-installation-issues.md](../troubleshooting-installation-issues.md "mention") and [common-issues-with-microsoft-bundle](../common-issues-with-microsoft-bundle/ "mention") pages.
{% endhint %}

## **Best Practices for Microsoft Integrations**

For best practice information please refer to: [Best Practices for Microsoft Integrations](https://docs.rewst.help/documentation/integrations/cloud/authorization-best-practices).

