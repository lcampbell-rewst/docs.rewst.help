# September 6th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* NEW CRATE - [Compromised User Response](https://app.rewst.io/marketplace/crates/01918ee2-c646-7309-a27d-15c26b81dfb8)
  * Manage user accounts and generate detailed reports based on selected actions within an organization. It helps administrators enforce security policies, monitor user activities, and audit mailbox configurations efficiently.
* NEW CRATE - [Report & Action Disabled M365 Users with Licence](https://app.rewst.io/marketplace/crates/01917503-bea7-711f-8ba3-4e7a2968563e)
  * Report on users that are disabled, but still have active licences and create a ticket in the PSA with the ability to remove them, or ignore that user in future reports.
* Document Shared Mailboxes
  * Refactored to use less calls to IT Glue

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Rewst: User Onboarding
  * Added missing inputs to ImmyBot subworkflow to ensure workflow running against on premise Exchange when ImmyBot and Exchange are configured.
  * Updated the Purchase Licence via CSP subworkflow to check date when finding active subscription&#x20;
* Add Users to Rewst via Group
  * Added failure transition to first MS Graph action
  * Removed parallel execution causing failures when organizations are not mapped
  * Added transitions when specified groups were not found resulting in failures
* CW PSA Pod: Technician Toolbox
  * Fixed 'Not Authorized' error on `rewst_get_microsoft_csp_customer` step of the workflow caused by incorrect CSP ID
* Fixed Ninja-RMM subworkflow: Run Powershell on Org DC or Endpoint not matching to Preferred DC

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* New Crate - Sonicwall Firmware Update
  * Initiate a firmware update via NSM
  * Support one or more firewall firmware upgrades at once
  * Support scheduling of firmware updates and restart times
* New Crate - M365 - Email Compromise Response
* New Crate - Workstation Offboarding
* Utility crate - Error Handling and Reporting

</details>

