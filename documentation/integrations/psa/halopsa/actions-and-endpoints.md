# Actions & Endpoints

## Introduction

The Halo Psa Integration with Rewst delivers a robust set of actions and endpoints for interacting with Halo Psa. Below is a summary of each section, highlighting the diverse capabilities and opportunities provided through the Halo Psa Integration:

* [**Actions**](actions-and-endpoints.md#actions-1)
* [**Agents**](actions-and-endpoints.md#agents)
* [**Appointments**](actions-and-endpoints.md#appointments)
* [**Assets**](actions-and-endpoints.md#assets)
* [**Attachments**](actions-and-endpoints.md#attachments)
* [**Clients**](actions-and-endpoints.md#clients)
* [**Contracts**](actions-and-endpoints.md#contracts)
* [**Generic Request**](actions-and-endpoints.md#generic-request)
* [**Invoices**](actions-and-endpoints.md#invoices)
* [**Items**](actions-and-endpoints.md#items)
* [**Knowledge Base**](actions-and-endpoints.md#knowledge-base)
* [**Opportunities**](actions-and-endpoints.md#opportunities)
* [**Organisations**](actions-and-endpoints.md#organisations)
* [**Projects**](actions-and-endpoints.md#projects)
* [**Quotes**](actions-and-endpoints.md#quotes)
* [**Reports**](actions-and-endpoints.md#reports)
* [**Sites**](actions-and-endpoints.md#sites)
* [**Status**](actions-and-endpoints.md#status)
* [**Suppliers**](actions-and-endpoints.md#suppliers)
* [**Teams**](actions-and-endpoints.md#teams)
* [**Ticket Types**](actions-and-endpoints.md#ticket-types)
* [**Tickets**](actions-and-endpoints.md#tickets)
* [**Toplevel**](actions-and-endpoints.md#toplevel)
* [**Users**](actions-and-endpoints.md#users)

## Actions

### Actions

{% swagger baseUrl="<example>.halopsa.com" path="/Actions" method="get" summary="List Actions" %}
{% swagger-description %}
Returns an object containing the count of actions, and an array of action objects for a given ticket.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Actions/{action_id}" method="get" summary="Get Action" %}
{% swagger-description %}
Returns a single Action object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Actions" method="post" summary="Add or Update Actions" %}
{% swagger-description %}
Adds or updates one or more action(s). If id is included then updates, if not included then creates new. Ticket ID is mandatory
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Actions/{action_id}" method="delete" summary="Delete Action" %}
{% swagger-description %}
Deletes the Action and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Agents

{% swagger baseUrl="<example>.halopsa.com" path="/Agent" method="get" summary="List Agents" %}
{% swagger-description %}
Returns an array of Agents
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Agent/{agent_id}" method="get" summary="Get Agent" %}
{% swagger-description %}
Returns a single Agent object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Agent/me" method="get" summary="Get Configured Agent" %}
{% swagger-description %}
Returns a single agent object based on the agent that the configured access token is for
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Agent" method="post" summary="Add or Update Agents" %}
{% swagger-description %}
Adds or updates one or more agents(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Agent/{agent_id}" method="delete" summary="Delete Agent" %}
{% swagger-description %}
Deletes the agent and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Appointments

{% swagger baseUrl="<example>.halopsa.com" path="/Appointment" method="get" summary="List Appointments" %}
{% swagger-description %}
Returns an array of appointments
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Appointment/{appointment_id}" method="get" summary="Get Appointment" %}
{% swagger-description %}
Returns a single Appointment object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Appointment" method="post" summary="Add or Update Appointments" %}
{% swagger-description %}
Adds or updates one or more appointment(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Appointment/{appointment_id}" method="delete" summary="Delete Appointment" %}
{% swagger-description %}
Deletes the Appointment and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Assets

{% swagger baseUrl="<example>.halopsa.com" path="/Asset" method="get" summary="List Assets" %}
{% swagger-description %}
Returns an object containing the count of Assets, and an array of Asset objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Asset/{asset_id}" method="get" summary="Get Asset" %}
{% swagger-description %}
Returns a single Asset object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Asset" method="post" summary="Add or Update Assets" %}
{% swagger-description %}
Adds or updates one or more asset(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Asset/{asset_id}" method="delete" summary="Delete Asset" %}
{% swagger-description %}
Deletes the asset and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Attachments

{% swagger baseUrl="<example>.halopsa.com" path="/Attachment" method="get" summary="List Attachments" %}
{% swagger-description %}
Returns an array of attachments. Each attachment returned will be in Base64 format.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Attachment/{attachment_id}" method="get" summary="Get Attachment" %}
{% swagger-description %}
Returns the text contents of a single Attachment object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Attachment" method="post" summary="Add or Update Attachments" %}
{% swagger-description %}
Adds or updates one or more attachment(s). If id is included then updates, if not included then creates new. The attachment must be posted in Base64 format.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Attachment/{attachment_id}" method="delete" summary="Delete Attachment" %}
{% swagger-description %}
Deletes the attachment and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Clients

{% swagger baseUrl="<example>.halopsa.com" path="/Client" method="get" summary="List Clients" %}
{% swagger-description %}
Returns an object containing the count of Clients, and an array of Client objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Client/{client_id}" method="get" summary="Get Client" %}
{% swagger-description %}
Returns a single Client object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Client" method="post" summary="Add or Update Clients" %}
{% swagger-description %}
Adds or updates one or more client(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Client/{client_id}" method="delete" summary="Delete Client" %}
{% swagger-description %}
Deletes the Client and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Contracts

{% swagger baseUrl="<example>.halopsa.com" path="/ClientContract" method="get" summary="List Contracts" %}
{% swagger-description %}
Returns an array of contracts
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/ClientContract/{contract_id}" method="get" summary="Get Contract" %}
{% swagger-description %}
Returns a single Contract object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/ClientContract" method="post" summary="Add or Update Contracts" %}
{% swagger-description %}
Adds or updates one or more contract(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/ClientContract/{contract_id}" method="delete" summary="Delete Contract" %}
{% swagger-description %}
Deletes the contract and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Generic Request

{% swagger baseUrl="<example>.halopsa.com" path="/<url_path>" method="get" summary="Halo PSA API Request" %}
{% swagger-description %}
Generic action for making authenticated requests against the Halo PSA API
{% endswagger-description %}
{% endswagger %}

### Invoices

{% swagger baseUrl="<example>.halopsa.com" path="/Invoice" method="get" summary="List Invoices" %}
{% swagger-description %}
Returns an object containing the count of invoices, and an array of invoice objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Invoice/{invoice_id}" method="get" summary="Get Invoice" %}
{% swagger-description %}
Returns a single Invoice object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Invoice" method="post" summary="Add or Update Invoices" %}
{% swagger-description %}
Adds or updates one or more invoice(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Invoice/{invoice_id}" method="delete" summary="Delete Invoice" %}
{% swagger-description %}
Deletes the invoice and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Items

{% swagger baseUrl="<example>.halopsa.com" path="/Item" method="get" summary="List Items" %}
{% swagger-description %}
Returns an object containing the count of items, and an array of item objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Item/{item_id}" method="get" summary="Get Item" %}
{% swagger-description %}
Returns a single Item object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Item" method="post" summary="Add or Update Items" %}
{% swagger-description %}
Adds or updates one or more item(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Item/{item_id}" method="delete" summary="Delete Item" %}
{% swagger-description %}
Deletes the item and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Knowledge Base

{% swagger baseUrl="<example>.halopsa.com" path="/KBArticle" method="get" summary="List Knowledge Base Articles" %}
{% swagger-description %}
Returns an array of knowledge base articles
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/KBArticle/{kb_article_id}" method="get" summary="Get Knowledge Base Article" %}
{% swagger-description %}
Returns a single knowledge base article object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/KBArticle" method="post" summary="Add or Update Knowledge Base Articles" %}
{% swagger-description %}
Adds or updates one or more knowledge base article(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/KBArticle/{kb_article_id}" method="delete" summary="Delete Knowledge Base Article" %}
{% swagger-description %}
Deletes the knowledge base article and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Opportunities

{% swagger baseUrl="<example>.halopsa.com" path="/Opportunities" method="get" summary="List Opportunities" %}
{% swagger-description %}
Returns an object containing the count of opportunities, and an array of opportunity objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Opportunities/{opportunity_id}" method="get" summary="Get Opportunity" %}
{% swagger-description %}
Returns a single Opportunity object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Opportunities" method="post" summary="Add or Update Opportunities" %}
{% swagger-description %}
Adds or updates one or more opportunities. If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Opportunities/{opportunity_id}" method="delete" summary="Delete Opportunity" %}
{% swagger-description %}
Deletes the opportunity and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Organisations

{% swagger baseUrl="<example>.halopsa.com" path="/Organisation" method="get" summary="List Organisations" %}
{% swagger-description %}
Returns an array of organisations
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Organisation/{organisation_id}" method="get" summary="Get Organisation" %}
{% swagger-description %}
Returns a single Organisation object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Organisation" method="post" summary="Add or Update Organisations" %}
{% swagger-description %}
Adds or updates one or more organisation(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Organisation/{organisation_id}" method="delete" summary="Delete Organisation" %}
{% swagger-description %}
Deletes the organisation and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Projects

{% swagger baseUrl="<example>.halopsa.com" path="/Projects" method="get" summary="List Projects" %}
{% swagger-description %}
Returns an object containing the count of projects, and an array of project objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Projects/{project_id}" method="get" summary="Get Project" %}
{% swagger-description %}
Returns a single Project object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Projects" method="post" summary="Add or Update Projects" %}
{% swagger-description %}
Adds or updates one or more project(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Projects/{project_id}" method="delete" summary="Delete Project" %}
{% swagger-description %}
Deletes the project and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Quotes

{% swagger baseUrl="<example>.halopsa.com" path="/Quotation" method="get" summary="List Quotes" %}
{% swagger-description %}
Returns an object containing the count of quotes, and an array of quote objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Quotation/{quote_id}" method="get" summary="Get Quote" %}
{% swagger-description %}
Returns a single Quote object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Quotation" method="post" summary="Add or Update Quotes" %}
{% swagger-description %}
Adds or updates one or more quote(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Quotation/{quote_id}" method="delete" summary="Delete Quote" %}
{% swagger-description %}
Deletes the quote and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Reports

{% swagger baseUrl="<example>.halopsa.com" path="/Report" method="get" summary="List Reports" %}
{% swagger-description %}
Returns an object containing the count of reports, and an array of report objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Report/{report_id}" method="get" summary="Get Report" %}
{% swagger-description %}
Returns a single Report object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Report" method="post" summary="Add or Update Reports" %}
{% swagger-description %}
Adds or updates one or more report(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Report/{report_id}" method="delete" summary="Delete Report" %}
{% swagger-description %}
Deletes the report and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Sites

{% swagger baseUrl="<example>.halopsa.com" path="/Site" method="get" summary="List Sites" %}
{% swagger-description %}
Returns an object containing the count of Sites, and an array of Site objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Site/{site_id}" method="get" summary="Get Site" %}
{% swagger-description %}
Returns a single Site object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Site" method="post" summary="Add or Update Sites" %}
{% swagger-description %}
Adds or updates one or more site(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Site/{site_id}" method="delete" summary="Delete Site" %}
{% swagger-description %}
Deletes the site and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Status

{% swagger baseUrl="<example>.halopsa.com" path="/Status" method="get" summary="List Statuses" %}
{% swagger-description %}
Returns an array of Statuses
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Status/{status_id}" method="get" summary="Get Status" %}
{% swagger-description %}
Returns a single Status object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Status" method="post" summary="Add or Update Statuses" %}
{% swagger-description %}
Adds or updates one or more status(es). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Status/{status_id}" method="delete" summary="Delete Status" %}
{% swagger-description %}
Deletes the status and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Suppliers

{% swagger baseUrl="<example>.halopsa.com" path="/Supplier" method="get" summary="List Suppliers" %}
{% swagger-description %}
Returns an array of suppliers
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Supplier/{supplier_id}" method="get" summary="Get Supplier" %}
{% swagger-description %}
Returns a single Supplier object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Supplier" method="post" summary="Add or Update Suppliers" %}
{% swagger-description %}
Adds or updates one or more supplier(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Supplier/{supplier_id}" method="delete" summary="Delete Supplier" %}
{% swagger-description %}
Deletes the supplier and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Teams

{% swagger baseUrl="<example>.halopsa.com" path="/Team" method="get" summary="List Teams" %}
{% swagger-description %}
Returns an array of Teams
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Team/{team_id}" method="get" summary="Get Team" %}
{% swagger-description %}
Returns a single Team object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Team" method="post" summary="Add or Update Teams" %}
{% swagger-description %}
Adds or updates one or more team(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Team/{team_id}" method="delete" summary="Delete Team" %}
{% swagger-description %}
Deletes the team and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Ticket Types

{% swagger baseUrl="<example>.halopsa.com" path="/TicketType" method="get" summary="List Ticket Types" %}
{% swagger-description %}
Returns an array of Ticket Types
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/TicketType/{ticket_type_id}" method="get" summary="Get Ticket Type" %}
{% swagger-description %}
Returns a single Ticket Type object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/TicketType" method="post" summary="Add or Update Ticket Types" %}
{% swagger-description %}
Adds or updates one or more ticket type(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/TicketType/{ticket_type_id}" method="delete" summary="Delete Ticket Type" %}
{% swagger-description %}
Deletes the ticket type and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Tickets

{% swagger baseUrl="<example>.halopsa.com" path="/Tickets" method="get" summary="List Tickets" %}
{% swagger-description %}
Returns an object containing the count of tickets, and an array of ticket objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Tickets/{ticket_id}" method="get" summary="Get Ticket" %}
{% swagger-description %}
Returns a single Ticket object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Tickets" method="post" summary="Add or Update Tickets" %}
{% swagger-description %}
Adds or updates one or more ticket(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Tickets/{ticket_id}" method="delete" summary="Delete Ticket" %}
{% swagger-description %}
Deletes the ticket and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Toplevel

{% swagger baseUrl="<example>.halopsa.com" path="/Toplevel" method="get" summary="List Top Levels" %}
{% swagger-description %}
Returns an object containing the count of top levels, and an array containing the top level tree
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Toplevel/{top_level_id}" method="get" summary="Get Top Level" %}
{% swagger-description %}
Returns a single top level object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Toplevel" method="post" summary="Add or Update Top Levels" %}
{% swagger-description %}
Adds or updates one or more top level(s). If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Toplevel/{top_level_id}" method="delete" summary="Delete Top Level" %}
{% swagger-description %}
Deletes the top level and related objects with the specified id
{% endswagger-description %}
{% endswagger %}

### Users

{% swagger baseUrl="<example>.halopsa.com" path="/Users" method="get" summary="List Users" %}
{% swagger-description %}
Returns an object containing the count of Users and an array of User objects
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Users/{user_id}" method="get" summary="Get User" %}
{% swagger-description %}
Returns a single User object
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Users" method="post" summary="Add or Update Users" %}
{% swagger-description %}
Adds or updates one or more Users. If id is included then updates, if not included then creates new.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example>.halopsa.com" path="/Users/{user_id}" method="delete" summary="Delete User" %}
{% swagger-description %}
Deletes the User and related objects with the specified id
{% endswagger-description %}
{% endswagger %}
