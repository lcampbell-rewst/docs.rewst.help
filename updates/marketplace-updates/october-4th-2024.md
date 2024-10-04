# October 4th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Create ticket workflow
  * Adjusted to:
    * Not use any deprecated actions
    * Added the automation log
    * Use publish results as
    * Use sub-workflows when appropriate
* Update ticket workflow
  * Adjusted to:
    * Not use any deprecated actions
    * Add the automation log
    * Use publish results as
    * Use sub-workflows when appropriate

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* M365: Set Calendar Permissions
  * Moved actions using with-items (e.g. `resolve_existing_perm_names` action) to sub-workflows and added error handing.
* Ad-Hoc Install/Uninstall Software via Chocolatey
  * Updated the value of the `device_list` key in the publish section of a task.
  * Added an additional condition in the list comprehension for the `device_list`.
  * Narrowed down the list of devices to those associated with a specific customer by only including items where `item.customerId` equals `ORG.VARIABLES.nable_customer_id|int`.

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* New Crate - Sonicwall Firmware Update
  * Initiate a firmware update via NSM
  * Support one or more firewall firmware upgrades at once
  * Support scheduling of firmware updates and restart times
* New Crate - Workstation Offboarding
* Utility crate - Error Handling and Reporting

</details>

