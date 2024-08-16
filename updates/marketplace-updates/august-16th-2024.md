# August 16th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* NEW CRATE: [Configure New GDAP Relationship](https://app.rewst.io/marketplace/crates/019100c6-5290-7f70-a353-70c628cc7f2e)
  * This new crate creates brand new GDAP relationships and ensures consistency in how roles are applied to the relevant auto created groups.
* NEW CRATE: [On-Premises Active Directory Password Expiration Alerts](https://app.rewst.io/marketplace/crates/019136e0-874a-7fee-abfd-3c0149fdaed6)
  * This new crate identifies on-premises users with passwords expiring in 14, 7, 3, and 1 days. and automatically sends email notifications to these users, reminding them to change their passwords before the expiration date.
* NEW CRATE: [Enterprise Application Creation Alert](https://app.rewst.io/marketplace/crates/019136b0-a777-7148-ba1f-68915993fb3e)
  * This new crate automatically monitors Microsoft Entra daily for new enterprise apps and creates tickets in your PSA system.
* Added VSA X to:
  * Rewst: User Onboarding
  * Rewst: User Offboarding v2
  * Configure Organizational Variables
  * Organizational Setup Report
  * Add Client to Rewst (form)

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Rewst: User Onboarding
  * Updated to check the full UPN instead of just the username, which was causing errors.
  * Fixed bug where licences weren't being purchased when Synnex is set as the licensing provider
* Rewst: User Offboard v2
  * Fixed timeouts for workflows where delay is >60 minutes.
  * Removed a leading space in an input field on the update\_ticket\_with\_groups action.
* Rewst: User Offboard v1
  * Handle errors for PSA Contact Disablement
* Consolidate And Manage Duplicate Configurations
  * Removed hardcoded value on cwm update configuration action.
* Sync ADD Users to CW Manage Contacts
  * Fixed bug where workflow could create duplicate contacts that did not have email.
* M365: Amend Mailbox Permissions
  * Fixed bug where workflow was failing to run as org with an invalid ID on the first EXO action.

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* New Crate - Sonicwall Firmware Update
  * Initiate a firmware update via NSM
  * Support one or more firewall firmware upgrades at once
  * Support scheduling of firmware updates and restart times
* Support  in crates for ServiceNow as a PSA

</details>

