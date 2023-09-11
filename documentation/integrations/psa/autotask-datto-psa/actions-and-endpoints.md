# Actions & Endpoints

<details>

<summary>Companies &#x26; Contacts</summary>

* List Contacts by Search v2
  * Description: This action allows users to retrieve a list of contacts based on a search query.
  * Endpoint: `/V1.0/Contacts/query`
  * Method: POST

<!---->

* List Contacts by Filter v2
  * Description: This action allows users to filter contacts based on specific criteria.
  * Endpoint: `/V1.0/Contacts/query`
  * Method: POST

<!---->

* Get Contact v2
  * Description: This action retrieves detailed information about a specific contact.
  * Endpoint: `/V1.0/Contacts/{id}`
  * Method: GET

<!---->

* List Company Contacts v2
  * Description: This action lists all contacts associated with a specific company.
  * Endpoint: `/V1.0/Companies/{companyId}/Contacts`
  * Method: GET

<!---->

* Create Contact v2
  * Description: This action allows users to create a new contact associated with a specific company.
  * Endpoint: `/V1.0/Contacts`
  * Method: POST

<!---->

* Update Contact v2
  * Description: This action allows users to update the information of an existing contact.
  * Endpoint: `/V1.0/Contacts`
  * Method: PATCH

<!---->

* List Companies by Search v2
  * Description: This action allows users to retrieve a list of companies based on a search query.
  * Endpoint: `/V1.0/Companies/query`
  * Method: POST

<!---->

* List Companies by Filter v2
  * Description: This action allows users to filter companies based on specific criteria.
  * Endpoint: `/V1.0/Companies/query`
  * Method: POST

<!---->

* Get Company v2
  * Description: This action retrieves detailed information about a specific company.
  * Endpoint: `/V1.0/Companies/{id}`
  * Method: GET

<!---->

* Create Company v2
  * Description: This action allows users to create a new company.
  * Endpoint: `/V1.0/Companies`
  * Method: POST

<!---->

* Update Company v2
  * Description: This action allows users to update the information of an existing company.
  * Endpoint: `/V1.0/Companies`
  * Method: PATCH

</details>

<details>

<summary>Contracts</summary>

* List Contracts by Search v2
  * Description: This action allows users to retrieve a list of contracts based on a search query.
  * Endpoint: `/V1.0/Contracts/query`
  * Method: POST

<!---->

* List Contracts by Filter v2
  * Description: This action allows users to filter contracts based on specific criteria.
  * Endpoint: `/V1.0/Contracts/query`
  * Method: POST

<!---->

* Get Contract v2
  * Description: This action retrieves detailed information about a specific contract.
  * Endpoint: `/V1.0/Contracts/{id}`
  * Method: GET

<!---->

* Create Contract v2
  * Description: This action allows users to create a new contract.
  * Endpoint: `/V1.0/Contracts`
  * Method: POST

<!---->

* Update Contract v2
  * Description: This action allows users to update the information of an existing contract.
  * Endpoint: `/V1.0/Contracts`
  * Method: PATCH

<!---->

* Adjust Contract Services v2
  * Description: This action allows users to adjust the services of a contract.
  * Endpoint: `/V1.0/Contracts/AdjustServices`
  * Method: POST

<!---->

* Adjust Child Contract Services v2
  * Description: This action allows users to adjust the services of a child contract.
  * Endpoint: `/V1.0/Contracts/AdjustChildServices`
  * Method: POST

</details>

<details>

<summary>Documents</summary>

* List Documents by Search v2
  * Description: This action allows users to retrieve a list of documents based on a search query.
  * Endpoint: `/V1.0/Documents/query`
  * Method: POST

<!---->

* List Documents by Filter v2
  * Description: This action allows users to filter documents based on specific criteria.
  * Endpoint: `/V1.0/Documents/query`
  * Method: POST

<!---->

* Get Document v2
  * Description: This action retrieves detailed information about a specific document.
  * Endpoint: `/V1.0/Documents/{id}`
  * Method: GET

<!---->

* List Document Categories by Search v2
  * Description: This action allows users to search for document categories.
  * Endpoint: `/V1.0/DocumentCategories/query`
  * Method: POST

<!---->

* List Document Attachments by Search v2
  * Description: This action allows users to search for document attachments.
  * Endpoint: `/V1.0/DocumentAttachments/query`
  * Method: POST

<!---->

* List Document Attachments by Filter v2
  * Description: This action allows users to filter document attachments based on specific criteria.
  * Endpoint: `/V1.0/DocumentAttachments/query`
  * Method: POST

<!---->

* Get Document Attachment v2
  * Description: This action retrieves detailed information about a specific document attachment.
  * Endpoint: `/V1.0/DocumentAttachments/{id}`
  * Method: GET

<!---->

* List Attachments on Document v2
  * Description: This action allows users to list all attachments associated with a specific document.
  * Endpoint: `/V1.0/Documents/{documentId}/Attachments`
  * Method: GET

<!---->

* Create Attachment on Document v2
  * Description: This action allows users to create a new attachment on a specific document.
  * Endpoint: `/V1.0/Documents/{documentId}/Attachments`
  * Method: POST

<!---->

* Get Attachment on Document v2
  * Description: This action retrieves detailed information about a specific attachment on a document.
  * Endpoint: `/V1.0/Documents/{documentId}/Attachments/{attachmentId}`
  * Method: GET

</details>

<details>

<summary>Projects</summary>

* List Projects by Search v2
  * Description: This action allows users to retrieve a list of projects based on a search query.
  * Endpoint: `/V1.0/Projects/query`
  * Method: POST

<!---->

* List Projects by Filter v2
  * Description: This action allows users to filter projects based on specific criteria.
  * Endpoint: `/V1.0/Projects/query`
  * Method: POST

<!---->

* Get Project v2
  * Description: This action retrieves detailed information about a specific project.
  * Endpoint: `/V1.0/Projects/{id}`
  * Method: GET

<!---->

* Create Project v2
  * Description: This action allows users to create a new project.
  * Endpoint: `/V1.0/Projects`
  * Method: POST

<!---->

* Update Project v2
  * Description: This action allows users to update an existing project.
  * Endpoint: `/V1.0/Projects`
  * Method: PATCH

<!---->

* List Phases on Project v2
  * Description: This action allows users to list all phases associated with a specific project.
  * Endpoint: `/V1.0/Projects/{projectId}/Phases`
  * Method: GET

<!---->

* Update Phase on Project v2
  * Description: This action allows users to update an existing phase of a project.
  * Endpoint: `/V1.0/Projects/{projectId}/Phases/{phaseId}`
  * Method: PATCH

<!---->

* Create Phase on Project v2
  * Description: This action allows users to create a new phase on a specific project.
  * Endpoint: `/V1.0/Projects/{projectId}/Phases`
  * Method: POST

<!---->

* Get Phase on Project v2
  * Description: This action retrieves detailed information about a specific phase on a project.
  * Endpoint: `/V1.0/Projects/{projectId}/Phases/{phaseId}`
  * Method: GET

<!---->

* List Tasks on Project v2
  * Description: This action allows users to retrieve a list of tasks associated with a specific project.
  * Endpoint: `/V1.0/Projects/{projectId}/Tasks`
  * Method: GET

<!---->

* Create Task on Project v2
  * Description: This action enables users to create a new task associated with a specific project.
  * Endpoint: `/V1.0/Projects/{projectId}/Tasks`
  * Method: POST

<!---->

* Update Task on Project v2
  * Description: This action allows users to update an existing task associated with a specific project.
  * Endpoint: `/V1.0/Projects/{projectId}/Tasks/{taskId}`
  * Method: PATCH

<!---->

* Get Task on Project v2
  * Description: This action retrieves detailed information about a specific task associated with a project.
  * Endpoint: `/V1.0/Projects/{projectId}/Tasks/{taskId}`
  * Method: GET

</details>

<details>

<summary>Resources</summary>

* List Resources by Search v2
  * Description: This action allows users to retrieve a list of resources based on a search query.
  * Endpoint: `/V1.0/Resources/query`
  * Method: POST

<!---->

* List Resources by Filter v2
  * Description: This action allows users to filter resources based on specific criteria.
  * Endpoint: `/V1.0/Resources/query`
  * Method: POST

<!---->

* Get Resource v2
  * Description: This action retrieves detailed information about a specific resource.
  * Endpoint: `/V1.0/Resources/{id}`
  * Method: GET

</details>

<details>

<summary>Surveys</summary>

* List Surveys by Search v2
  * Description: This action allows users to retrieve a list of surveys based on a search query.
  * Endpoint: `/V1.0/Surveys/query`
  * Method: POST

<!---->

* List Surveys by Filter v2
  * Description: This action allows users to filter surveys based on specific criteria.
  * Endpoint: `/V1.0/Surveys/query`
  * Method: POST

<!---->

* Get Survey v2
  * Description: This action retrieves detailed information about a specific survey.
  * Endpoint: `/V1.0/Surveys/{id}`
  * Method: GET

</details>

<details>

<summary>Tickets &#x26; Ticket Notes</summary>

* List Notes on Ticket v2
  * Description: This action allows users to retrieve a list of notes associated with a specific ticket.
  * Endpoint: `/V1.0/Tickets/{ticketId}/Notes`
  * Method: GET

<!---->

* Create Ticket Note v2
  * Description: This action enables users to create a new note associated with a specific ticket.
  * Endpoint: `/V1.0/Tickets/{ticketId}/Notes`
  * Method: POST

<!---->

* Update Ticket Note v2
  * Description: This action allows users to update an existing note associated with a specific ticket.
  * Endpoint: `/V1.0/Tickets/{ticketId}/Notes/{noteId}`
  * Method: PATCH

<!---->

* Get Child Ticket Note v2
  * Description: This action retrieves detailed information about a specific note associated with a ticket.
  * Endpoint: `/V1.0/Tickets/{ticketId}/Notes/{noteId}`
  * Method: GET

<!---->

* List Ticket Notes by Search v2
  * Description: This action allows users to search for ticket notes based on specific criteria.
  * Endpoint: `/V1.0/TicketNotes/query`
  * Method: POST

<!---->

* List Ticket Notes by Filter v2
  * Description: This action allows users to filter ticket notes based on specific criteria.
  * Endpoint: `/V1.0/TicketNotes/query`
  * Method: POST

<!---->

* Get Ticket Note v2
  * Description: This action retrieves detailed information about a specific ticket note.
  * Endpoint: `/V1.0/TicketNotes/{id}`
  * Method: GET

<!---->

* List Ticket Categories by Search v2
  * Description: This action allows users to search for ticket categories based on specific criteria.
  * Endpoint: `/V1.0/TicketCategories/query`
  * Method: POST

<!---->

* List Ticket Categories by Filter v2
  * Description: This action allows users to filter ticket categories based on specific criteria.
  * Endpoint: `/V1.0/TicketCategories/query`
  * Method: POST

<!---->

* Get Ticket Category v2
  * Description: This action retrieves detailed information about a specific ticket category.
  * Endpoint: `/V1.0/TicketCategories/{id}`
  * Method: GET

<!---->

* Update Ticket Category v2
  * Description: This action allows users to update an existing ticket category.
  * Endpoint: `/V1.0/TicketCategories`
  * Method: PATCH

<!---->

* List Tickets by Search v2
  * Description: This action allows users to search for tickets based on specific criteria.
  * Endpoint: `/V1.0/Tickets/query`
  * Method: POST

<!---->

* List Tickets by Filter v2
  * Description: This action allows users to filter tickets based on specific criteria.
  * Endpoint: `/V1.0/Tickets/query`
  * Method: POST

<!---->

* Get Ticket v2
  * Description: This action retrieves detailed information about a specific ticket.
  * Endpoint: `/V1.0/Tickets/{id}`
  * Method: GET

<!---->

* Create Ticket v2
  * Description: This action enables users to create a new ticket.
  * Endpoint: `/V1.0/Tickets`
  * Method: POST

<!---->

* Update Ticket v2
  * Description: This action allows users to update an existing ticket.
  * Endpoint: `/V1.0/Tickets`
  * Method: PATCH

</details>

<details>

<summary>Time Entries</summary>

* List Time Entries by Search v2
  * Description: This action allows users to search for time entries based on specific criteria.
  * Endpoint: `/V1.0/TimeEntries/query`
  * Method: POST

<!---->

* List Time Entries by Filter v2
  * Description: This action allows users to filter time entries based on specific criteria.
  * Endpoint: `/V1.0/TimeEntries/query`
  * Method: POST

<!---->

* Get Time Entry v2
  * Description: This action retrieves detailed information about a specific time entry.
  * Endpoint: `/V1.0/TimeEntries/{id}`
  * Method: GET

<!---->

* Delete Time Entry v2
  * Description: This action allows users to delete a time entry.
  * Endpoint: `/V1.0/TimeEntries/{id}`
  * Method: DELETE

<!---->

* Create Time Entry v2
  * Description: This action enables users to create a new time entry.
  * Endpoint: `/V1.0/TimeEntries`
  * Method: POST

<!---->

* Update Time Entry v2
  * Description: This action allows users to update an existing time entry.
  * Endpoint: `/V1.0/TimeEntries`
  * Method: PATCH

</details>

<details>

<summary>Datto PSA API Request</summary>

The Datto PSA API Request is a powerful and flexible action that enables developers to interact with the Datto PSA API in a generic manner. By leveraging this action, users can perform any desired HTTP request against the Datto PSA endpoints, including data retrieval, modification, deletion, or custom interactions.

**Parameters**

Here's an overview of key parameters:

* **Request Method:** HTTP method to use (`HEAD`,`GET`, `POST`, `PUT`, `DELETE`, `OPTIONS`, `TRACE`, `PATCH`, `PURGE`).
* **URL Path:** URL path for the API endpoint, excluding the hostname or API prefix.
* **Body:** The body content to send with the request.
* **Cookies:** Any cookies to send with the request.
* **Headers:** Custom HTTP headers to include in the request.
* **JSON Object:** A JSON object body to send with the request.
* **Paginate Request:** If set to true, all multiple pages of results will be requested at once.
* **Query Params:** Any query parameters to be included in the HTTP request.
* **Raw JSON:** If the JSON Object field is too restrictive, paste your JSON body here.

</details>

<details>

<summary>Filter Operations Explaination</summary>

* **beginsWith**: Selects items where the specified field begins with the given value. Useful for searching for items starting with particular characters or patterns.
* **eq**: Stands for "equals." Selects items where the specified field exactly matches the given value.
* **noteq**: Stands for "not equals." Selects items where the specified field does not match the given value.
* **gt**: Stands for "greater than." Selects items where the specified field is greater than the given value.
* **gte**: Stands for "greater than or equal to." Selects items where the specified field is greater than or equal to the given value.
* **lt**: Stands for "less than." Selects items where the specified field is less than the given value.
* **lte**: Stands for "less than or equal to." Selects items where the specified field is less than or equal to the given value.
* **endsWith**: Selects items where the specified field ends with the given value. Useful for searching for items ending with particular characters or patterns.
* **contains**: Selects items where the specified field contains the given value. Useful for searching for items that include particular characters or patterns anywhere within the field.
* **exists**: Selects items where the specified field exists, regardless of its value. Useful for filtering items based on the presence of a particular attribute or property.
* **notExists**: Selects items where the specified field does not exist. Useful for filtering items based on the absence of a particular attribute or property.
* **in**: Selects items where the specified field's value is in a given list of values. Useful for filtering items that match one of several specific values.
* **notIn**: Selects items where the specified field's value is not in a given list of values. Useful for filtering items that do not match any of several specific values.

</details>
