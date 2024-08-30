# August 30th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Report & Action Disabled M365 Users with Licence
  * Report on users that are disabled, but still have active licences and create a ticket in the PSA with the ability to remove them, or ignore that user in future reports.

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Report & Action Disabled M365 Users with Licence
  * Fixed failures due to missing parenthesis in Jinja
* Fixed Immybot Powershell execution on the shared Run PowerShell workflow
* Restart Offline Agents via Control/Automate
  * Updated workflow to handle changes to Restart Automate Agent API response
* Rewst: User Offboarding v2
  * Fixed "final\_ticket\_update\_subworkflow" Jinja eval error from the "internal\_note" field. It was missing one % at the end of a line of code.
  * "choose\_your\_time" Dropdown Field in "\[Rewst] User Offboarding" form is now properly populating
  * Passed "CTX.forward\_mail\_and\_store" variable to subworkflow to prevent undefined errors.
  * Updated "Begin - Shared Mailbox Permissions" action that was always returning false due to improper Jinja condition
  * Added support for truthy/falsy values
  * Handled PowerShell errors&#x20;
* Report Offline Servers to Teams
  * Fixed `list_computers` action that was failing due to changed CW Control response
* Consolidate and Manage Duplicate Configurations
  * When you entered a client in the client field the workflow would still run for the parent and only the parent's configurations get consolidated. Added functionality to get the correct company ID
* Configure Organizational Variables
  * Added truthy/falsy support that was causing failures
* Rewst: User Onboarding
  * Handling when user has no PSA
* Added error handling for ticket creation failures on shared ticket workflows when no ticket is found
* ITG Documentation Crates
  * Fixed a retry error on EXO - Execute Cmdlet Retry Loop

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

