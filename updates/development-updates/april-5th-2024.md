# April 5th 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added the ability to render Jinja in html components in App Platform
* Added an accordion component to App Platform
* Allow for de-branding of Microsoft Teams Actions
* Highlight connected tasks when a transition is selected
* Microsoft Cloud Integration Bundle
* Added drag and drop re-ordering of Workflow Notes
* Added an option to toggle hiding of Text/Markdown components in Forms
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed a bug with custom components in app platform to account for unpublished changes
* Removed an unnecessary serialize/deserialize step in postgres jsonb columns to improve performance
* Fixed the name for Get Service Ticket Note action for ConnectWise PSA
* Optimized the scheduling of "With-Items" tasks in workflows to improve performance
* Made selecting stacked tabs in App Platform more intuitive
* Additional fixes to pagination for SentinelOne
* Added an optional argument to `json_dump` and `json_stringify` Jinja filters to accept `as_bytes`
* Fixed an issue with Custom Integrations not respecting extra request_headers
* Modified Custom Components query to return only components for the currently selected org instead of all components the user has access to
* Fixed intellisense for filters that stopped working in the code editor
* Fixed a bug where empty object fields in the task form would cause errors on the frontend
* Fixed a bug with Microsoft Graph Login Distance Trigger
* Added EmployeeID param to the Update User action for Microsoft Graph
* Fixed a bug when mocking "With-Items" tasks in workflows
* Fixed a bug with Microsoft Graph Polling Sensor failures
* Fixed a bug where Microsoft Teams Message confirmations were not respecting Jinja customizations
* Updated the App Platform icon
* Updated the Home Page preset in App Platform with patched components
* Fixed typos in Nerdio API reference
* Fixed the default URL path for Kaseya BMS List Contacts action
* Increased the max page limit for ConenctWise PSA to 20
* Increased the max page limit for Hubspot to 300
* Added pagination parameter properties to GoDaddy and Liongard clients
* Improved "in" and "not in" filters for Datto PSA
* Removed the "required" flag from GoDaddy sandbox configuration
* Performance improvements for Workflow Results page
* Modified the default response for SMS messages when a user replies to an SMS sent from Rewst
* Added allowed expected server IDs to Discord
* Fixed the ordering of fields for the Datto PSA integration configuration
* Adjusted Sophos page size and increased the max page limit
* Fixed a frontend bug with deleting users in the platform
* Added error handling for non-fatal authorization errors in the Microsoft Bundle


</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* ITPortal integration (In Review)
* New permission system starting with App Platform (In Review)
* Workflow version control (In Review)
* Visual workflow processing and debugging (In Review)

</details>
