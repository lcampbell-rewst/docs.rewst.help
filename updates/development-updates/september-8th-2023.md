# September 8th 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added tagging to Forms

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Add Retention Policy cmdlets to x-anchormailbox list
* Added new server region options for Datto PSA mapping
* Add a filter to Acronis to allow users to restrict the number of orgs that get returned for org mapping
* Fix the Jinja editor value not updating when the underlying field is edited directly
* Fixed a problem where cron trigger errors were causing Kubernetes pods to crash
* Removed IP restrictions for health endpoints in preparation for Istio
* Spawn new threads for the SentinelOne client to prevent it from blocking the event loop
* Fixed a bug that was preventing users from being able to uninstall integrations
* Fixed a problem with redis connection pool

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Implement Istio in Kubernetes cluster to allow for better observability and control of network traffic
* Improvements to workflow builder UI when viewing workflows that are synced clones or installed via a crate
* Refactor ConnectWise Manage integration
* Liongard integration
* Godaddy integration

</details>
