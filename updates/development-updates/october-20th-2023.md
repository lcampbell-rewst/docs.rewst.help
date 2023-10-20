# October 13th 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Add "Include Raw Body" flag to Core.Webhook
* Added "includeFields" field to Datto PSA v2 actions
* Added "extension" field to IT Glue contact actions
* Added DeviceManagementRBAC scope and eDiscovery scope to Microsoft Graph
* Added an option to allow generic http actions to follow redirects
* ConnectWise Manage refactor and added actions for all endpoints

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Add as_bytes kwarg to decode_base64 filter to access raw bytes
* Fixed Datto PSA webhook trigger fields not loading options
* Fixed a bug with ConnectWise Control not showing orgs for mapping in some cases
* Added handling for publish task failures that have valid outgoing transitions

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Refactor Proofpoint and add new actions
* Redact secret org vars from jinja live editor

</details>
