# September 27th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Check back next week!

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* RMM-Ninja: Run PowerShell on Org DC or Endpoint workflow
  * Added missing `VMWARE_VMGUEST` node class that was causing workflow to fail.
* Deactivate ConnectWise PSA Contacts when their Company is Deactivated
  * Added failure transitions to account for ConnectWise Manage config issues
* Rewst: user Onboarding
  * Added logic to M365: Purchase Licences workflow to account for a `None` type being returned when getting the subscription id
  * Added waits when purchasing licences through Sherweb to procure the right amount of licenses
* Alert on Expiring Secrets
  * Fixed failure if an org is disabled by updating Jinja for data alias `to_run_against`
* RMM: Report Offline Servers to Teams
  * Updated ConnectWise Control - ConnectWise Control API Request used to list computers to a POST request.

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

