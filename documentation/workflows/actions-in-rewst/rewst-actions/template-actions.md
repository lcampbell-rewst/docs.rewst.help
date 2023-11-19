# Template Actions

## **Create Template**

**Description:** Lets you create a new template.

**Parameters:**

* **Name:** The name of the template.
* **Description:** A brief description of the template.
* **Body:** The actual template content.
* **Content Type:** The type of content used in the template.
* **Language:** The language used in the template. Options include: `html`, `markdown`, `powershell`, `python`, `yaml`.

**Output:** The action returns the newly created template's information, including its `id`.

***

## **Get Template**

**Description:** Lets you retrieve the details of an existing template.

**Parameters:**

* **Template ID**: The ID of the template you wish to retrieve.

**Output:** The action returns the requested template's information, including its `name`, `description`, `body`, `content_type`, and `language`.

***

## **List Templates**

**Description:** Lets you retrieve a list of all existing templates.

**Parameters:** _No parameters are required for this action._

**Output:** The action returns a list of all templates, with each entry including information about a template, such as its `id`, `name`, `description`, `body`, `content_type`, and `language`.

***

## **Update Template**

**Description:** Lets you update the details of an existing template.

**Parameters:**

* **Template ID:** The ID of the template you wish to update, it is a required field.
* **Body:** The new content of the template.
* **Content Type:** The new type of content used in the template. The options are `message` and `script`.
* **Description:** A brief description of the template.
* **Language:** The new language used in the template. The options include: `html`, `markdown`, `powershell`, `python`, `yaml`.

**Output:** The action returns the updated template's information, including its `id`.

***

## **Delete Template**

**Description:** Lets you delete an existing template.

**Parameters:**

* **Template ID**: The ID of the template you wish to delete.

**Output:** The action does not return any specific output, but its execution status indicates whether the deletion was successful.
