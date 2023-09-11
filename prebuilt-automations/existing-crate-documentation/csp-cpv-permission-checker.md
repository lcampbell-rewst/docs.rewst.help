---
description: >-
  Easily identify any missing GDAP roles within your managed Microsoft tenants
  required for Rewst to perform it's necessary actions.
---

# CSP/CPV Permission Checker

<details>

<summary><strong>Crate Specifications</strong></summary>

**Creation Date**: August 27th, 2023

**Required Integrations**: [Microsoft Graph](../../documentation/integrations/cloud/microsoft-graph/microsoft-graph-integration-setup.md)

**Components**:

* **Parent Workflow:** \[ROC] M365: CSP/CPV Permission Checker
* **Sub-Workflows:**&#x20;
  * \[ROC] M365: Get Tenant Info by Domain
  * \[ROC] M365: Get Role Assignments

**Trigger:**&#x20;

Uses the `Core- Always` Pass [trigger](../../documentation/triggers/intro-to-triggers.md) with an integration override for Microsoft Graph

</details>

{% hint style="success" %}
If you're interested in taking advantage of the CSP/CPV Permission Checker within your Rewst organization, [unpack it from the Crate Marketplace](https://app.rewst.io/marketplace/crates/94d861ee-2fb9-45df-8af5-63cc73b351de).
{% endhint %}

## Overview

Your Rewst service account that is used to manage your Microsoft tenants requires [specific GDAP roles in order to perform it's various actions](../../documentation/integrations/cloud/authorization-best-practices.md#recommended-roles-for-gdap), without them you can run into a slew of issues. This workflow is designed to identify if any of these roles are missing at a specified client location.

## Usage&#x20;

### Installing the Crate

* Refer to the instructions in the [Unpack a Crate](../crates/#unpacking-a-crate) section of the documentation.
* Before unpacking, make sure to enable the necessary organizations in the trigger configuration section. This can be done by toggling `Activate for all current and future managed organizations` or by selecting from the available organization list.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

### **Execute the Workflow**

* Within the **\[ROC] M365: CSP/CPV Permission Checker** main workflow, click `Test`.
* From the dropdown menu, select the tenant you want to check permissions for. This list is derived from the organizations enabled in your trigger configuration.
* Provide any domain associated with the managing organization's tenant to fetch it's ID.

### **Workflow Steps**

#### **Gather Tenant Info**

* The **\[ROC] M365: Get Tenant Info by Domain** sub-workflow uses the collected domain, represented as `{{ CTX.primary_domain }}`.
* A `GET` request is made to:\
  `https://login.microsoftonline.com/{{ CTX.provided_domain }}/.well-known/openid-configuration`

#### **Determine Tenant ID**

A data alias is created for the `msp_tenant_id`, which is extracted from the returned tenant info using the following Jinja statement:

```django
{{ CTX.tenant_info.authorization_endpoint.split('/')[3] }}
```

#### **Assess Roles**

* The **\[ROC] M365: Get Role Assignments** sub-workflow is initiated.
* The [Necessary GDAP roles](../../documentation/integrations/cloud/authorization-best-practices.md#recommended-roles-for-gdap) are confirmed through a `GET` request to the following Graph endpoint:
  * Base URL: `https://graph.microsoft.com/beta`
  * Endpoint: `/roleManagement/directory/roleAssignments?$filter=roleDefinitionId eq '{{ CTX.role_id }}'&$expand=principal`
* The output differentiates between present and absent roles, with results set for comparison in the subsequent step.

**Compile and Analyze Results**

* A comparison is conducted between the `msp_tenant_id` and the IDs from the returned roles to ensure appropriate permissions.
* A summary of the roles is generated, and a `missing roles` data alias is defined.

Example Output:

```json
"missing_roles": [
  {
    "ID": "No ID associated with no user",
    "Name": "Security Administrator",
    "Note": "No users assigned to this role.",
    "Found": false,
    "Principal Organization IDs": []
  },
  {
    "ID": "No ID associated with no user",
    "Name": "Authentication Policy Administrator",
    "Note": "No users assigned to this role.",
    "Found": false,
    "Principal Organization IDs": []
  }
]
```
