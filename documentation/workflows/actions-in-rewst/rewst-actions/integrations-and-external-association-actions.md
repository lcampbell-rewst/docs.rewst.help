# Integrations & External Association Actions

## **List Integrations For Organization**

**Description:** Retrieve a list of the integrations currently installed for an organization.

**Parameters:**

* **Organization ID:** Identifier of the organization to fetch the integrations for. This ID is unique for each organization within Rewst.

**Output:** Outputs a list of integrations, each integration includes its ID, Name, Reference, Pack Configurations, applied triggers, and foreign object references.

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

***

### Get External Reference

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
