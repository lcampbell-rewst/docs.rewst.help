# Microsoft Azure Integration Setup

### **Overview**

The Microsoft Azure integration with Rewst offers extensive cloud services that:

{% hint style="info" %}
Note that a key vault is required in your Azure subscription. If you receive an "Invalid Client" error message when authorizing it is likely due to a missing key vault. Creating an empty key vault should resolve the issue.&#x20;
{% endhint %}

* Enable scalable infrastructure.
* Provide robust data storage.
* Support advanced analytics and AI services.
* Facilitate the efficient building, deployment, and management of applications.
* Ensure high availability, security, and scalability.

Moreover, the integration includes Azure Active Directory for comprehensive identity management and data protection.

### **Steps to Integrate Microsoft Azure with Rewst**

1. **Navigate to Integrations:** Access the integrations page in Rewst.
2. **Select Microsoft Azure:** Click on the Microsoft Azure integration option.
3. **Fill Configuration Form:** Input all required details, ensuring you include your Microsoft Tenant ID.
4. **Authorize OAuth Configuration:** Click the OAuth Configuration Authorize/Re-Authorize button and follow Microsoft's authorization prompts.
5. **Save Configuration:** Finalize the integration by clicking the "Save Configuration" button.

### How to Find Your Microsoft Tenant ID:

The Tenant ID is crucial for a successful integration. Here are the various ways to retrieve your Microsoft Tenant ID:

#### **Through Azure Portal:**

1. Log in to the [Azure Portal](https://portal.azure.com/).
2. Go to "Azure Active Directory".
3. Your Tenant ID will be displayed on the overview page.

#### **Via 'What Is My Tenant ID' Tool:**

1. Visit [What Is My Tenant ID](https://www.whatismytenantid.com/).
2. Enter your domain name.
3. The site will display your Tenant ID.

#### **Using Rewst Core HTTP Request Action within a Workflow:**

1. Start with the [**Core HTTP Request Action**](../../../workflows/actions-in-rewst/core-actions.md#a-d-hoc-http-requests).&#x20;
2. Set the Publish Results As name to something like: `get_tenant_info`.
3. Send a **GET request** to the below URL, substituting `{{ CTX.domain }}` if necessary.

```bash
https://login.microsoftonline.com/{{ CTX.domain }}/.well-known/openid-configuration
```

4. The successful results of this execution will provide a JSON object with details about your tenant. To extract the Tenant ID for subsequent tasks, add a data alias during your task transition named `tenant_id` and use this Jinja statement:

```django
{{ CTX.get_tenant_info.data.authorization_endpoint.split('/')[3] }}
```

{% hint style="info" %}
**Note:** Once your Microsoft CSP integrations are setup and mapped, you can use the `ORG.MAPPING.ms_tenant_id` organizational variable to return the executing organizations Tenant ID
{% endhint %}
