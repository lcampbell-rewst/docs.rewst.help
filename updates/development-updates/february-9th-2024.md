# February 9th 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Jinja live editor improvements
* Added support for Opportunities in ConnectWise PSA
* Added support for extra request headers in Custom Integrations
* Added support for Ticket Categories to Datto PSA
* Backend for persistant Time Saved metrics
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Increased the number of engine pods from 120 to 180 and the number of workers per pod from 3 to 5
* Fixed a bug where the frontend would crash if a workflow task was deleted before the parameters form loaded
* Added an error message to Sonicwall integration when it can't determine the Tenant
* Fixed a formatting issue with Liongard metrics action
* Fixed a bug with decoding string responses to json
* Changed Datto PSA webhook creation to use synchronous requests to add/remove fields to webhooks to avoid being rate limited
* Fixed a bug in cloning and syncing where very large bundles would cause a failure
* Fixed IT Glue Delete Organization Action
* Added `_issuerupdate` parameter to Halo PSA create actions
* Added Microsoft Graph permissions for Bookings, AppRoleAssignment, and AccessReview
* Fixed a bug in App Platform where websocket connections weren't using the correct domain name

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Custom integrations v2 (In Review)
* Microsoft refactor to allow for better permission system (In Development)
* Workflow version control (In Development)

</details>
