# Microsoft Azure Integration Setup

{% hint style="warning" %}
**New: Microsoft Cloud Integration Bundle!** 🌟 We've combined our Microsoft integrations into a single, streamlined package for easier management and enhanced security. While individual integration guides are still here, we recommend checking out the new bundle for a simplified setup. Learn more on the [Microsoft Cloud Integration Bundle](../) page.
{% endhint %}

## **Overview**

The Microsoft Azure integration, as part of the Rewst Microsoft Cloud Integration Bundle, offers streamlined management of Azure services, providing tools and capabilities that are essential for building scalable infrastructure, robust data storage solutions, advanced analytics, and comprehensive application management.

## **Key Features**

* **Scalable Infrastructure**: Dynamically adjust your computational and storage resources based on your needs.
* **Robust Data Storage**: Leverage Azure's secure and scalable storage solutions for all types of data.
* **Advanced Analytics and AI**: Utilize Azure's machine learning and analytics tools to enhance decision-making and innovation.
* **Application Management**: Deploy and manage applications efficiently using Azure’s DevOps and management tools.

## **Detailed Setup Instructions**

### **Step 1: Access the Integration Bundle**

* Log into the Rewst dashboard.
* Navigate to `Integrations`.
* Select `Microsoft Cloud Integration Bundle`.

### **Step 2: Select Azure Integration**

* Under `Select Integrations`, choose `Microsoft Azure` along with any other Microsoft services you want to configure such as Microsoft Graph, Exchange Online, or Microsoft CSP.
* Click `Next` to proceed.

### **Step 3: Configure Authentication and Permissions**

* On the configuration parameters page, choose your preferred authentication app registration method from:
  * **Rewst Microsoft Cloud Connector**: Recommended for most users.
  * **Owned App Registration**: For users with an existing setup who wish to utilize their own app registrations.
  * **Legacy Rewst App (Deprecated)**: Not recommended and is being phased out.

### **Step 4: Setup Tenant Permissions**

* You will see a list of permissions for Graph, Exchange Online, CSP, and Azure. Necessary permissions for Azure may include:
  * **Key Vault Impersonation**
  * **Service Management User Impersonation**
  * **Storage User Impersonation**
* Recommended options are pre-selected, but you can customize based on your needs.
* Click `Next` to proceed to the authorization step.

{% hint style="info" %}
For more information on Azure Permissions, see the [#microsoft-azure-permissions](../microsoft-cloud-permissions.md#microsoft-azure-permissions "mention") section of the [microsoft-cloud-permissions.md](../microsoft-cloud-permissions.md "mention") page
{% endhint %}

### **Step 5: Authorize Integration**

* In the 'Authorize Integrations' section, click the 'Authorize' button. This will open a Microsoft login window for authentication.
* Follow the prompts to complete the authorization process.

{% hint style="info" %}
Note that a key vault is required in your Azure subscription. If you receive an "Invalid Client" error message when authorizing it is likely due to a missing key vault. [Creating an empty key vault](https://learn.microsoft.com/en-us/azure/key-vault/secrets/quick-create-portal) should resolve the issue.&#x20;
{% endhint %}

## **Troubleshooting Tips**

* **Authorization Issues**: Ensure that you are using the correct account and that all permissions are properly configured before authorization.
* **Permission Errors**: If you encounter errors related to permissions, verify that all selected permissions are essential and correctly set up in the Rewst Microsoft Cloud Connector.

{% hint style="info" %}
For more Troubleshooting tips, check out the [troubleshooting-installation-issues.md](../troubleshooting-installation-issues.md "mention") and [common-issues-with-microsoft-bundle](../common-issues-with-microsoft-bundle/ "mention") pages.
{% endhint %}
