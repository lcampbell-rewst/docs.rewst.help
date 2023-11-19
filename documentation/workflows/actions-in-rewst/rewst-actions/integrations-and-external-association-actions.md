# Integrations & External Association Actions

## **List Integrations For Organization**

**Description:** This action retrieves a comprehensive list of integrations installed for a specific organization in Rewst, providing a detailed overview of each integration's attributes.

**Parameters:**

* **Organization ID:** The unique identifier for an organization in Rewst. This parameter is required to fetch the specific integration details pertinent to the organization.

**Output:**

The action generates a detailed list of integrations, including:

* **Integration ID, Name, and Reference:** Basic identifiers providing clarity on each integration.
* **Pack Configurations:** In-depth details of configurations applied to each integration, offering insights into their setup and customization.
* **Applied Triggers:** Information on workflow triggers linked to each integration, useful for understanding operational dynamics.
* **Foreign Object References:** Crucial data points that link integrations to external references, enhancing cross-platform data synchronization and management.

{% hint style="info" %}
Check out the documentation for the[view-rewst-integration-org-variables.md](../../../../prebuilt-automations/existing-crate-documentation/view-rewst-integration-org-variables.md "mention") crate, to see a practical example of how to leverage this action within your Rewst workflows.
{% endhint %}

***

## Get External Reference

**Description**: Facilitates the retrieval of details about these external references. You can use it to fetch all external references associated with a specific organization in Rewst or to find the organization associated with a specific external reference ID.

#### **Parameters**:

* **Org ID**: (Optional) The ID of the organization in Rewst. If provided, the action returns all external references linked to this organization.
* **Identifier**: (Optional) A specific identifier type for the external resource.
* **Reference ID**: (Optional) The unique identifier of the external resource. If provided, the action returns the organization in Rewst associated with this reference.

#### **Output**:

* Returns detailed information about the external reference(s), such as the `org_id` in Rewst linked to it, the type of `identifier`, and the external `reference_id`. This information is helpful for cross-system data synchronization and management.

{% hint style="info" %}
Check out the documentation for the[view-rewst-integration-org-variables.md](../../../../prebuilt-automations/existing-crate-documentation/view-rewst-integration-org-variables.md "mention") crate, to see a practical example of how to leverage this action within your Rewst workflows.
{% endhint %}

***

## **Associate External Object**

**Description:** Lets you associate a resource in some other system, i.e., a PSA ticket, with a particular workflow execution.

**Parameters:**

* **Reference ID:** The ID of the external resource.
* **Identifier:** An identifier for the external resource, i.e. "cwm\_ticket".
* **Fail On Conflict:** Set to true to fail the task if a `reference_id`/`identifier` pair already exists for the supplied values. It is a boolean parameter.

**Output:** The action returns information about the associated external object.
