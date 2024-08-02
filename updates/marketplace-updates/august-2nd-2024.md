# August 2nd, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Rewst: User Onboarding
  * Added N-Able N-Central to the list of integration overrides on the minimalist form trigger
  * Added the run as org function to the first get-user action.
* Billing Report
  * Changed all variable names that had sentinel in them to sentinelone. E.g. `sentinel_user_count` is now `sentinelone_user_count`. The workflow dynamically selects the integration ids based off the name of the variables and the integration id for sentinel one is sentinelone and not sentinel therefore it was filling 0s for all sentinel counts.

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Manage Mailbox Permissions
  * Added the run as org function to the first get-user action.
  * Added soft failure when the main workflow is not run as part of the form.
* Rewst: User Onboarding
  * Fixed jinja that was evaluating to true on an empty list, causing failures. When doing on-prem exchange actions, the workflow was running the Exchange shared mailbox workflow even though no shared mailbox was selected.
* CWM: Technician Toolbox via Pod
  * Fixed failure at `get_ms_reference_id` by updating workflow with new action `rewst_get_microsoft_csp_customer.` This task is designed to get data for a single Microsoft CSP customer in Rewst. It has two transitions, one that triggers when the tenant information is not available and another that triggers when the task succeeds.
* Rewst: User Offboard v2
  * Updated remove supervisor references to `on_prem` from `onprem`
  * Removed Jinja reference to data alias that was no longer in context and no longer used.

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* New Crate - Sonicwall Firmware Update
  * Initiate a firmware update via NSM
  * Support one or more firewall firmware upgrades at once
  * Support scheduling of firmware updates and restart times
* Add VSA X to:
  * Rewst: User Onboarding
  * Rewst: User Offboarding v2
  * Configure Organizational Variables
  * Organizational Setup Report
  * Add Client to Rewst (form)
* New Crate - GDAP Configuration
  * Crate to help speed up the process of configuring GDAP

</details>

