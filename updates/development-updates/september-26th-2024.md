# September 26th, 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* New dashboard - Deployed to all customers

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Added a missing parameter to the Synnex AU integration for the Google Workspace action
* Deployed warrant to workos permission system behind a feature flag
* Fixed a bug where the `DELETED` prefix was not being removed from soft deleted orgs when they're restored
* Fixed a problem where form load times were very slow for when there were large numbers of activated orgs for the form
* Applied the production feature flagging system to all production environments
* Fixed jinja boolean values being converted to strings for default values causing the result to always be `True`. It will now convert properly so falsey values in jinja will render `False` in the UI
* Fixed a bug in the Create Gist action for new Github integration causing crashes
* Added automatic conversion to json when using generic http requests when the content type is set to application/json and the `data` field contains a dictionary or list that can be converted to json
* Updated the daily time saved rollup query to include the end date and added validation to prevent data beyond the end date from being included
* Fixed a bug with host validation in app platform apps to handle schemas for future production environments
* Fixed a number of bugs discovered by QA for DNS Filter integration
* Fixed a bug with the "select all" button on CSP permissions
* Fixed text spacing issues on new dashboard
* Optimized the List Workflow Executions With Time Savings V2 action for the Rewst integration

</details>

<details>

<summary><strong>Deployed behind feature flags awaiting QA review and feedback</strong></summary>

* Granular forms permissions (QA review)
* IT Portal integration (QA review)
* Synnex Australia integration (QA review)
* Cove integration (QA review)
* Github integration (QA Review)
* New Org Picker (Awaiting enhancements)

</details>

<details>

<summary><strong>In code review and development</strong></summary>

* Multi-player workflows V1 (In code review)
* Bitdefender integration (In development)

</details>
