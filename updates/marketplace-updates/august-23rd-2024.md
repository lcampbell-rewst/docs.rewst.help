# August 23rd, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Rewst: User Onboarding
  * Add ability to purchase licenses through TD Synnex&#x20;
  * Added documentation to the crate detail page
* Document Group Details
  * Refactor the crate to batch requests, making it more efficient and running fewer tasks/calls to IT Glue
* Document User Details
  * Added documentation to the crate detail page
* ServiceNow has been added to the following crates:
  * Rewst: User Onboarding
  * Rewst: User Offboarding
* Configure Organizational Variables
  * Added documentation to the crate detail page

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* M365: Amend Mailbox Permissions
  * Fixed bug where workflow was failing to run as org with an invalid ID on the first EXO action.
* Rewst: User Onboarding
  * Added various "soft fails"
* Rewst: User Offboarding v1
  * Added error handling for PSA Contact Disablement
* Rewst: User Offboarding v2
  * Updated delay to up to 30 days in the future to prevent unwanted failures.
  * Fixed issue where on-prem only offboarding was failing due to O365 tenant\_id not being found. No O365 tenant is expected.
* Consolidate And Manage Duplicate Configurations
  * The task named `connect_wise_manage_update_configuration` has been removed.
  * **BEGIN:** This task does nothing and is now placed at the beginning of the workflow.
  * **list\_config\_statuses:** This task makes a GET request to the `/company/configurations/statuses` endpoint and publishes the result as `config_statuses`.
  * **connect\_wise\_psa\_update\_configuration:** This task updates a configuration with a set of parameters.
  * **END:** This task does nothing and is placed at the end of the workflow.
  * The new task order is as follows: `BEGIN`, `list_config_statuses`, `connect_wise_psa_update_configuration`, and `END`.
  * The `next` field of each task has been updated to reflect the new task order.
  * The `publish` field of the `list_config_statuses` task has been updated with a new key-value pair
* On-Premises Active Directory Password Expiration Alerts
  * Added a "soft fail" in the scenario when a user doesn't have an SMTP address or email address attribute.

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* New Crate - Sonicwall Firmware Update
  * Initiate a firmware update via NSM
  * Support one or more firewall firmware upgrades at once
  * Support scheduling of firmware updates and restart times
* New Crate - M365 - Email Compromise Response
* New Crate - Workstation Offboarding

</details>

