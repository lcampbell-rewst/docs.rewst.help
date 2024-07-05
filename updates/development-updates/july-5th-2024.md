# July 5th 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Update text input for App Platform accordions to use Monaco editor
* Added ability to use page variables and query params value(s) as workflow inputs on page load in App Platform
* Added validation to prevent mapping multiple CSP customer tenants to the same Rewst organization and add alerting for customers

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed App Platform bug where you could't drag new components on to canvas in custom components and certain components created from the tree view.
* Fixed ConnectWise PSA Create Company action - Company id and Company types were being sent incorrectly
* Corrected ConnectWise PSA Create Service Ticket action Status parameter action options generator that is supposed to return service ticket statuses. Instead of doing that it was using an endpoint that returned CWM project tickets.
* Fixed exception handling for writing workflow stats to the db from the redis cache
* Upgrade to React 18
* Fixed bug where task level pack overrides were not being correctly reflected within a workflow when reverting, causing an issue when saving.
* Corrected issues causing failures in the Create Organization dialog for CSP customers
* Optimized auto instrumentations on the graph api
* Fixed issue where there was an error message showing when you selected a workflow in the workflows list.

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* IT Portal integration (In QA)
* ServiceNow integration (In code review)
* DNS Filter Integration (In code review)
* Addigy Integration (In code review)
* Kaseya X Integration (In code review)
* Granular forms permissions (In code review)

</details>
