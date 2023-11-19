# Integrations & External Association Actions

**List Integrations For Organization**

**Description:** Retrieve a list of the integrations currently installed for an organization.

**Parameters:**

* **Organization ID:** Identifier of the organization to fetch the integrations for. This ID is unique for each organization within Rewst.

**Output:** Outputs a list of integrations, each integration includes its ID, Name, Reference, Pack Configurations, applied triggers, and foreign object references.

***

**Associate External Object**

**Description:** Lets you associate a resource in some other system, i.e., a PSA ticket, with a particular workflow execution.

**Parameters:**

* **Reference ID:** The ID of the external resource.
* **Identifier:** An identifier for the external resource, i.e. "cwm\_ticket".
* **Fail On Conflict:** Set to true to fail the task if a `reference_id`/`identifier` pair already exists for the supplied values. It is a boolean parameter.

**Output:** The action returns information about the associated external object.

***

**Get External Reference**

**Description:** Retrieves details about an external reference in the system.

**Parameters:**

* **Org ID:** The organization's ID.
* **Identifier:** An identifier for the external resource.
* **Reference ID:** The ID of the external resource.

**Output:** The action returns information about the specified external reference, including its `org_id`, `identifier`, and `reference_id`.
