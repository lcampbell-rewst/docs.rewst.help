# August 16th 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Workflow overwrite notification
* Added right click context menu to form builder
* Enabled multi-tenancy for TDSynnex (allows for Canadian clients)
* ServiceNow integration

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Optimized the query to check_pending_tasks by reducing the number of database locks required
* Improved setup instructions for ServiceNow integration
* Fixed a bug with creating workflow tags related to version control
* Added a close icon to the roborewsty loading screen to allow users to cancel the request
* Added v2 actions for List and Get Site for ConnectWise PSA
* Fixed a bug with the Liongard generic request action for the follow_redirects parameter
* Added a debounce to form fields so there is a slight delay to ensure users are done typing before setting field values
* Improved the collapse section behavior on integration override sections in triggers
* Virtualized org variable dropdown to improve UI performance for scenarios where there are a large number of options
* Fixed a bug with custom integrations v2 where a null label would cause the UI to crash
* Fixed a typo in Webroot notifications actions for Start Date
* Fixed a bug with Webroot integration org mapping
* Fixed an invalid error when saving OpenAI Azure integration
* Fixed some malformed action parameters in DNS Filter actions
* Fixed a client side error in App Platform when navigating between pages
* Split WorkflowInput component into multiple new component types (TextField, Switch, Dropdown, and NumberInput)

</details>

<details>

<summary><strong>Deployed behind feature flags awaiting release</strong></summary>

* IT Portal integration (QA review)
* Webroot integration (QA review)
* New dashboard (Awaiting enhancements)
* New Org Picker (Awaiting enhancements)

</details>

<details>

<summary><strong>In code review, QA testing, and development</strong></summary>

* Addigy integration (In QA)
* Synnex Australia integration (Code Review)
* Cove integration (Code Review)
* Github integration (In development)
* Granular forms permissions (In code review)
* Building out new Rewst environments in Europe, Australia, and US-West (In development)
* Syncing of Crate Marketplace items across environments (In development)

</details>
