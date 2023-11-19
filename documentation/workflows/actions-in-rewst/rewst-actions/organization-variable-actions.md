# Organization Variable Actions

***

## List Organization Variables

**Description:** Lists all organization variables visible to the selected organization.

**Parameters:**

* **Organization ID:** (Optional) A dropdown list of the labels that correlate with the ID (visible in the code editor window) of an organization you'd like to retrieve.

**Output:** Returns a list of objects. Each object represents an organization variable and includes the ID, name, value, organization ID, category, timestamps, associated organization, and more.

***

## Get Organization Variable

**Description:** Retrieves a specific organization variable for a selected organization using the variable's name or value.

**Parameters:**

* **Name:** (Optional) The name of the organization variable.
* **Organization ID:** (Optional) A dropdown list of the labels that correlate with the ID of an organization you'd like to retrieve.
* **Value:** (Optional) The value of the organization variable.

**Output:** Returns an object (or list of objects) representing the organization variable, including the ID, name, value, organization ID, category, timestamps, associated organization, and more.

***

## Create Organization Variable

**Description:** Creates a new organization variable that's available for use within an organization's workflow context.

**Parameters:**

* **Name:** The name of the organization variable.
* **Value:** The value of the organization variable.
* **Category:** The category used to define the organization variable. Options include: `general`, `contact`, `system`, `secret`.
* **Use as default:** If true, this variable's value will be used as the default value for any managed organizations without a defined value.
* **Organization ID:** (Optional) The ID of the organization.

**Output:** Returns an object containing the new variable details including the ID, name, value, organization ID, category, timestamps, associated organization, and more.

***

## Bulk Upsert Organization Variables

**Description:** Performs a bulk operation to create or update organization variables.

**Parameters:**

* **Organization Variables:** A list of objects where each object represents an organization variable to be created or updated. Each object must include:
  * **Name:** The name of the organization variable.
  * **Value:** The value of the organization variable.
  * **Category:** The category used to define the organization variable. Options include: `general`, `contact`, `system`, `secret`.
  * **Use as default:** If true, this variable's value will be used as the default value for any managed organizations without a defined value.
  * **Organization ID:** (Optional) The ID of the organization.

**Output:** Returns a list of objects. Each object represents an upserted organization variable and includes properties such as ID, name, value, organization ID, category, timestamps, associated organization, and more.

***

## Delete Organization Variable

**Description:** Deletes a specific organization variable for a selected organization using the variable's name.

**Parameters:**

* **Organization ID:** The ID of an organization.
* **Name:** The name of the organization variable to be deleted.

**Output:** Returns an object indicating the success of the operation, including the name of the deleted variable and the ID of the organization from which it was deleted.
