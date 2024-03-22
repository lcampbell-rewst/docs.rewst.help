# March 22nd 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added the ability to select a preset page type when creating a new page in App Platform. Options include: Basic, Blank, Grid, Home, Login
* Custom Components v2 for App Platform
* Custom Integrations v2 (Released internally for testing)
* Added tags to Create and Update Organization Actions for the Rewst integration
* Added the `enabled` attribute to triggers the List Workflows action for the Rewst integration
* Implemented a proxy service to avoid IP based rate limiting in IT Glue
* Added grouping and aggregation to DataTables in App Platform
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed a bug with Synnex "suggest matches" on org mapping
* Fixed a bug where redis connection handler was attempting to use a dead connection
* Segmented trigger_polls, crons, and database_notifications to their own Kafka consumer groups
* Added a minimum width to the sidebar component in App Platform
* Fixed a bug with copy to clipboard on Workflow Tasks
* Fixed a bug in the SQL Database integration to handle colons being interpreted as parameterized queries
* Fixed a bug in App Platform where the color input could cause page crashes
* Fixed a bug with editing or deleting the name of page in the page navigator in App Platform
* Set triggers to `disabled` when importing a workflow bundle

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Highlight connected tasks when a transition is selected (In Review)
* ITPortal integration (In Review)
* New permission system starting with App Platform (In Review)
* Workflow version control (In Review)
* Microsoft refactor to allow for better permission system (In Review)

</details>
