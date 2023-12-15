# December 15th 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* N-Able integration v2
* App platform domain provisioning for *.rew.st domains
* Added a Create Invitation action to Microsoft Graph
* Added new Rewst actions to List Workflows and List Workflow Executions (including Time Saved)
* Added new Core action to fail a workflow manually
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed the logo link so that it takes users to the dashboard instead of an empty page
* Removed duplicate fields for ConnectWise PSA actions
* Added more verbose error messages for ConnectWise Control
* Fixed a bug where outdated subworkflows in crate bundles could cause failures when unpacking the crate
* Removed the `remove_put` option from Ninja RMM actions
* Added automatic retries for Redis connections
* Fixed a bug where the impersonation header wasn't being passed for Datto PSA action options requests
* Improved RoboRewsty JSON parsing ability by attempting to fix malformed JSON returned by OpenAI
* Fixed bugs with live page rendering in App Platform

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Improved Time Saved functionality with Task level Time Saved and persistence beyond workflow execution retention
* Continue work on App Platform to get ready for users
* Continue work on platform performance and stability

</details>
