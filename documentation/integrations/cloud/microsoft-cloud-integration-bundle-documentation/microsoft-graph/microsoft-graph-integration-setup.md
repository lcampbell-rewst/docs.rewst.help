# Microsoft Graph Integration Setup

{% hint style="warning" %}
**New: Microsoft Cloud Integration Bundle!** 🌟 We've combined our Microsoft integrations into a single, streamlined package for easier management and enhanced security. While individual integration guides are still here, we recommend checking out the new bundle for a simplified setup. Learn more on the [Microsoft Cloud Integration Bundle](../) page.
{% endhint %}

## **Introduction**

The Microsoft Graph integration within the Rewst Microsoft Cloud Integration Bundle facilitates seamless interaction with Microsoft services like Office 365, Azure Active Directory, SharePoint, and more. This integration is designed to simplify access to a wide array of Microsoft products through a single API endpoint.

## **Key Features**

* **Unified API Access**: Connect to multiple Microsoft services through one API for efficient data management.
* **Data Management**: Read and write data across various Microsoft platforms.
* **User and Access Management**: Manage user identities and access permissions seamlessly.
* **Enhanced Workflow Integration**: Automate and integrate workflows to enhance productivity across services like Outlook, Teams, and OneDrive.
* **Analytics and Reporting**: Perform analytics on user activities and generate reports to drive decision-making.

***

## **Setup Instructions**

### **Step 1: Access the Integration Bundle**

* Log into the Rewst dashboard.
* Navigate to `Integrations`.
* Select `Microsoft Cloud Integration Bundle`.

### **Step 2: Select Graph Integration**

* Under `Select Integrations`, choose `Microsoft Graph` along with any other services you wish to configure.
* Click `Next` to proceed.

### **Step 3: Configure Authentication and Permissions**

* On the configuration parameters page, choose from:
  * **Rewst Microsoft Cloud Connector**: Recommended for streamlined integration.
  * **Owned App Registration**: For those with existing setups wishing to use their own app registrations.
  * **Legacy Rewst App (Deprecated)**: Not recommended; being phased out.

### **Step 4: Setup Graph-Specific Permissions**

* You will be presented with a list of necessary permissions for Microsoft Graph, which typically includes operations like reading and writing data, managing users, accessing calendars and contacts, and more.
* Recommended permissions are pre-selected, but you can adjust them according to your organizational needs.
* Click `Next` to proceed to the authorization step.

{% hint style="info" %}
For more information on Graph Permissions See the [#microsoft-graph-permissions](../microsoft-cloud-permissions.md#microsoft-graph-permissions "mention") section of the [microsoft-cloud-permissions.md](../microsoft-cloud-permissions.md "mention") page
{% endhint %}

### **Step 5: Authorize Integration**

* On the `Authorize Integrations` step, click the `Authorize` button to initiate the Microsoft login window for authentication.
* Follow the on-screen prompts to complete the authorization process, ensuring to use the same account as used for other Microsoft service integrations if necessary.

***

## **Troubleshooting Tips**

* **Authorization Issues**: Ensure that you are using the correct account and that all permissions are properly configured before authorization.
* **Permission Errors**: If you encounter errors related to permissions, verify that all selected permissions are essential and correctly set up in the Rewst Microsoft Cloud Connector.

{% hint style="info" %}
For more Troubleshooting tips, check out the [troubleshooting-installation-issues.md](../troubleshooting-installation-issues.md "mention") and [common-issues-with-microsoft-bundle](../common-issues-with-microsoft-bundle/ "mention") pages.
{% endhint %}
