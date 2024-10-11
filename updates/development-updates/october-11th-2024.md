# October 11th, 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added a couple design improvements to the new dashboard like hover state for links in the news section
* Added a few design improvements to the new org picker like colors, spacing, and dividers
* Added a JSON RPC base class to abstract implementation of integrations using that protocol and make them easier to build

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed a bug in the Rewst action to List Workflow Executions With Time Savings
* Fixed a bug where deleted roles were still being displayed on the permissions page
* Removed padding from the Blank page preset in App Platform
* Fixed a bug where the Refresh Token wasn't being displayed in Custom Integrations V2
* Fixed a bug with Custom Integrations V2 where Incorrect Datatype Expectation was causing errors
* Changed the expires_at field to not be required for Custom Integration V2 oAuth
* Fixed DNSFilter integration test action to fail for on invalid API keys
* Reduced the amount of data being stored in Redis Streams to prevent that system from filling up storage
* Added a toggle to allow users to hide/show other users cursors for multiplayer on workflow editor
* Made crate un-packing more resilient by adding error handling to the integration overrides portion of that process
* Fixed a feature flag check for integration export
* Fixed a bug in Custom Integrations V2 to prevent iterating required fields that have a null value which would stop users from being able to add properties
* Fixed a bug preventing Triggers for being saved in some cases where integration overrides were being used during Crate Unpacking
* Added handling to prevent the legacy Microsoft configuration from being used in some cases where the integration had already been upgraded to use V2

</details>

<details>

<summary><strong>Deployed behind feature flags awaiting QA review and feedback</strong></summary>

* New Org Picker (Launching soon)
* Multi-player workflows V1 (Launching soon)
* Bitdefender integration (QA review)
* Granular forms permissions (QA review)
* IT Portal integration (QA review)
* Synnex Australia integration (QA review)
* Cove integration (QA review)
* Github integration (QA Review)
* SQL Database integration refactor (QA Review)

</details>

<details>

<summary><strong>In code review and development</strong></summary>

* Crushbank integration (Code review)
* Nodeware integration (Code review)
* Webroot Triggers (Code review)


</details>
