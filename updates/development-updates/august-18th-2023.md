# August 18th 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* New action to look up warranty information for a device
* Added workflow name, time savings, and original execution to workflow listeners
* Added new Transform actions: Transform List Objects, Merge Lists, Diff Lists, Set Object Attribute, Convert List to Object, and Append With Items Results
* Added custom overrides for property and session group in ConnectWise Control

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Focus the cursor in the code editor when the Jinja Burger is clicked
* Fix for the NinjaRMM Modify Ticket action
* Refresh Sonicwall NSM token more frequently to avoid token expiration
* Fix query parameters for ConnectSecure List Assets action
* Added output schemas for Sophos actions
* Fixed a bug for Sophos when making requests to the Partner API
* Renamed Parse JSON to Parse Text
* Ensure delay\_info keys are deleted from Redis after a workflow completes
* Fixed a bug where code editor auto complete would crash if it received an invalid schema
* Update ConnectWise Automate Script Schedule Task to use correct DateTime formate that the endpoint expects
* Added a re-try mechanism for TimeoutErrors when making requests from the engine to the graphql server

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Fix a bug where Datto PSA webhooks are not adding excluded users correctly
* Crate marketplace UI overhaul
* Refactor ConnectWise Manage integration

</details>

If you'd like to see these in action, review the latest Open Mic recording here.
