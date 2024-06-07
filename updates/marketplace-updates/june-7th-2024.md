# June 7th, 2024

Explore the new changes to the Marketplace in the last week!

This can be anything from new crates, enhancements, or bug fixes!

<details>

<summary><strong>New crates and enhancements</strong></summary>

* Alert When Users Mailboxes are Reaching Quota
  * Added an action to the crate that checks for an existing ticket and if one exists it updates that ticket or at least does not create a new ticket.
  * Added ability to exclude mailboxes from alerting with a comma delimited list in the org variable `excluded_quota_monitoring_emails`

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Amend Calendar Permission on User
  * Fixed `check_delegate` action Jinja where `CTX.delegate_type` always returning `false` due to being a list.

</details>

<details>

<summary><strong>Coming soon!</strong></summary>

* Rewst: User Offboarding
  * On-prem AD support
* Document M365 Environment
  * Support for Hudu
* Document User Details
  * Support for Hudu
* Document Group Details
  * Support for Hudu
* Document Shared Mailbox Details
  * Support for Hudu
* Liongard MFA Remediation
  * Liongard detects when MFA is not enabled properly, logs it to a PSA ticket, Rewst enables MFA and updates the ticket.

</details>
