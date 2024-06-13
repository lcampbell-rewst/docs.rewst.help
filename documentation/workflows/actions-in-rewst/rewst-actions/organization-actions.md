# Organization Actions

## **Get Organization**

**Description:** Retrieve data for a single organization in Rewst.

**Parameters:**

* **Organization ID:** Identifier of the organization to fetch data for. This ID is unique for each organization within Rewst.

**Output:** Outputs the details of the organization, which includes the Organization ID, Domain, Name, Managing Organization ID, and Enabled Status.

***

## **Bulk Create Organizations**

**Description:** Create multiple organizations at once within Rewst.

**Parameters:**

* Managing **Organization ID:** The ID of the managing organization. If not provided, the organization that initiated the operation will be set as the managing organization.
* Organizations (Required): List of organization details to be created. Each entry in the list should contain the following parameters:
  * Is Enabled: Boolean indicating if the organization should be enabled.
  * Name: The name of the organization in Rewst. The name must be unique.
  * Domain: The domain name of the organization's website, excluding protocol.

**Output:** Outputs a list of newly created organizations, each with its corresponding Organization ID, Domain, Name, Managing Organization ID, and Enabled Status.

***

## **Create Organization**

**Description:** Create a single organization within Rewst.

**Parameters:**

* Name (Required): The name of the organization to be created. This name must be unique within Rewst.
* Domain (Optional): The domain of the new organization, excluding protocol.
* Managing **Organization ID:** Identifier of the managing organization. If not provided, the organization that initiated the operation will be set as the managing organization.
* Is Enabled (Optional, default is true): A boolean indicating whether the new organization is enabled or not.

**Output:** Outputs the details of the newly created organization, which includes the Organization ID, Domain, Name, Managing Organization ID, and Enabled Status.

***

## **List Organizations**

**Description:** Fetch a list of all organizations in Rewst.

**Parameters:**

* Managing **Organization ID:** Identifier of the managing organization to fetch organizations for. This ID is unique for each organization within Rewst.
* Name (Optional): Name of the organization to search for. The name must be unique within Rewst.

**Output:** Outputs a list of organizations, each with its corresponding Organization ID, Domain, Name, Managing Organization ID, and Enabled Status.

***

## **Update Organization**

**Description:** Update details of an existing organization within Rewst.

**Parameters:**

* **Organization ID:** Identifier of the organization to be updated. This ID is unique for each organization within Rewst.
* Name (Optional): New name for the organization. This name must be unique within Rewst.
* Domain (Optional): New domain for the organization, excluding protocol.
* Is Enabled (Optional): Updated enabled status for the organization. It is a boolean value.

**Output:** Outputs the updated details of the organization, which includes the Organization ID, Domain, Name, Managing Organization ID, and Enabled Status.

***

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
