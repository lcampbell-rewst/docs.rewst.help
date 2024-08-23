# August 23rd 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added a query_params input for ServiceNow actions
* Added a generic api request action for Microsoft CSP
* Added append_domains parameter to DNS Filter Create Policy action

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fix handling of unauthorized graph-api requests to log and return 401 instead of throwing a NoInviteError
* Restrict multiline edits to string based columns in App Platform data tables
* Fixed error handling for Generic HTTP requests with pagination set to true for methods that don't support pagination
* Update the name parameter to be required for DNS Filter Schedule Policy action

</details>

<details>

<summary><strong>Deployed behind feature flags awaiting release</strong></summary>

* Granular forms permissions (QA review)
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
* Github integration (Code Review)

</details>
