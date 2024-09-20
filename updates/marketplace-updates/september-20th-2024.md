# September 20th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Rewst: User Onboarding
  * Updated create new AD user powershell to post back exception message if unable to set password settings
* View Rewst Integration Org Variables
  * Added `_policy_id` to the int\_endings list so that it picks up Addigy integration IDs
* Rewst: User Offboarding v2
  * Added support for PSA and RMM parent/child relationships

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Rewst: User Onboarding
  * Added Tasks to handle errors:
    * `update_ticket_failed_to_sync_to_ad`
    * `wait_for_AD_to_sync_to_azure`
    * `check_for_azure_ad_user`
    * `delay_for_ad_sync`
  * Fixed issue where workflow was overpurchasing M365 licences when they aren't provisioned in time
* Send Email with Attachment function workflow
  * Switched to use correct response header for webhook.
  * Changed title to be a space so it didn't get rendered as None in the email on the core send.&#x20;
  * Modified message body to actually contain the webhook url.&#x20;
* Billing Count Report
  * Fixed CSV generation so that the company field is always the first column.
* Configure CWM Agreement for Duo Sync
  * Made the `cwm_company_id` field required to prevent failures.

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* New Crate - Sonicwall Firmware Update
  * Initiate a firmware update via NSM
  * Support one or more firewall firmware upgrades at once
  * Support scheduling of firmware updates and restart times

<!---->

* New Crate - Workstation Offboarding
* Utility crate - Error Handling and Reporting

</details>

