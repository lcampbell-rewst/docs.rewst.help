# Issue Alerts

<details>

<summary> ⚠️  Slow User Interface (UI) Load Times (October 3rd, 2024)</summary>

**Date:** Thursday, October 3rd, 2024

**Time:** 22:00 UTC / 6:00 PM EDT

October 3, 2024 at 22:00 UTC Rewst was notified of slow user interface (UI) load times and reduced accessibility of the platform. This was escalated internally for review per standard process. Rewst traced the issue to a slow-running common request. This resulted in Rewst Forms and UI elements not loading for some users and reduced functionality for other users from 22:00 to 23:15 UTC. Rewst is currently operating as normal while we continue to investigate the root cause of this issue. More information will be provided as it becomes available.

</details>

<details>

<summary> ⚠️  Update To Disable Forms (September 30th, 2024)</summary>

### **Issue Identified**

**Date**: Monday, September 30th, 2024

We released an update that corrected an issue where some forms marked as "disabled" were still functioning. If you had disabled form triggers within a workflow, they may now be correctly inactive. We’ve noticed a few customers were using these forms in production, and the update has properly disabled them.&#x20;

If you’re impacted by this change, simply re-enable the form in your trigger settings.

</details>

<details>

<summary> ⚠️ Lost Form Access (September 12th, 2024)</summary>

### **Issue Identified**

**Date**: Thursday, September 12, 2024\
**Time**: 11:17 PM EDT

An update aimed at improving load times for custom forms was implemented at 3 PM EDT. This update unintentionally caused some users to lose access to forms.

### Issue Resolved

**Date**: Thursday, September 12, 2024\
**Time**: 11:55 PM EDT

Following standard procedures, the update was rolled back, and the issue was resolved.

If you have any questions or concerns, please contact the ROC support team via Discord or contact your Customer Success Manager.

Thank you for your understanding and patience as we work to improve our platform!

</details>

<details>

<summary> ⚠️ Planned Service Maintenance Notification (August 14th, 2024)</summary>

**Date**: Friday, August 16th, 2024\
**Time**: 6:00 PM - 7:00 PM EST

We will be performing a scheduled update to our platform to prepare for some awesome new features that should be released soon! While most users won't notice any disruption, the following features will be temporarily unavailable for approximately 10 to 20 minutes during this period:

* Loading Action Options
* Cloning, Syncing, Exporting, and Importing
* RoboRewsty functionality
* Jinja Rendering and Live Editor
* App Platform page rendering
* Unpacking Crates
* Processing of workflow completion handlers (pending tasks will resume after the update)

**⚠️ Please note that all other workflows and webhooks will operate normally during this time. ⚠️**

If you have any questions or concerns, please contact the ROC support team via Discord or contact your Customer Success Manager.

Thank you for your understanding and patience as we work to improve our platform!

</details>

<details>

<summary> ⚠️ Update Service Ticket Action Failure (August 7th, 2024)</summary>

**⚠️ We are pleased to inform you that the issue affecting workflows containing the ConnectWise Update Service Ticket (v1) action has been successfully resolved. Normal functionality has resumed. All services should now be operating as expected. ⚠️**

### Technical Update for Rewst Users

**Issue**: We detected an issue affecting workflows that update PSA tickets.&#x20;

**The action affected is**: ConnectWise Update Service Ticket (v1). Workflows that contain this action are failing.

This also affects crates that use this action, such as User Onboarding and User Offboarding V1 and V2. Once the recovery process is complete, we will re-run all failed New User Workflows.

### Current Status

Our team is actively working on restoring the system from backup, and we expect to resume normal functionality within the next hour.&#x20;

We appreciate your patience and will provide updates once we have more information.&#x20;

### Updates&#x20;

Thank you for your understanding and cooperation.&#x20;

Please contact our support team if you have any questions or need further assistance.

* **Discord** - The ROC is always available here: [https://discord.gg/rewst](https://discord.gg/rewst)
* **Create a Ticket** - [E-mail the team](mailto:roc@rewst.io) and someone will be in touch ASAP!

</details>

<details>

<summary> ⚠️ Forms Users Experiencing Login Delays and Timeouts (July 16th, 2024)</summary>

**⚠️ This issue has been successfully resolved and we are closing this alert. An RCA report will be available upon request. ⚠️**

### Technical Update for Rewst Users

**Issue**: Intermittent Delays or Timeouts During Login. We have received reports from users assigned the "Forms" role experiencing intermittent delays or timeouts when logging into Rewst.&#x20;

### Current Status:&#x20;

* **Affected Users**: Users with the "Forms" role
* **Symptom**: Intermittent delays or timeouts during login
* **Investigation**: Ongoing to determine the root cause and implement a solution

Our team is actively working to identify and resolve the underlying problem. We appreciate your patience and will provide updates once we have more information.

### Next Steps:

* We are closely monitoring the system.
* We are working to identify the root cause.&#x20;
* **Optional Workaround:** MSPs may temporarily add the Read Only Role to affected users.&#x20;

### Updates:&#x20;

Thank you for your understanding and cooperation.&#x20;

For the latest information, please refer to [https://status.rewst.io/](https://status.rewst.io/)

Please contact our support team if you have any questions or need further assistance.

* **Discord** - The ROC is always available here: [https://discord.gg/rewst](https://discord.gg/rewst)
* **Create a Ticket** - [E-mail the team](mailto:roc@rewst.io) and someone will be in touch ASAP!

</details>

<details>

<summary> ⚠️ The new UI enhancement highlights any Rewst Organization linked to multiple CSP Customers (July 3rd, 2024)</summary>

### **Error Indication**&#x20;

The error message displayed is: _One or more organizations are linked to multiple customers. This will cause errors when attempting to run Microsoft actions on these organizations._\
![](<../.gitbook/assets/Screenshot 2024-07-03 at 3.55.42 PM.png>)

### Problem Scenario&#x20;

If a Rewst Organization is mapped to more than one CSP Customer, it causes ambiguity in workflow execution. Since workflows can only follow the most recent mapping, this can result in:&#x20;

* Workflows failing to execute correctly.&#x20;
* Unexpected actions being performed on the wrong CSP Customer.&#x20;

### Solution Steps&#x20;

To resolve this issue, ensure that each Rewst Organization is mapped to a single CSP Customer. Follow these guidelines:&#x20;

1. Single Mapping Per Rewst Organization:&#x20;
   * Each Rewst Organization should be linked to only one CSP Customer.&#x20;
   * **Example**: Rewst Organization A → CSP Customer 1.&#x20;
2. Multiple Rewst Organizations to One CSP Customer:&#x20;
   * You can map the same CSP Customer to multiple Rewst Organizations.&#x20;
   * **Example**: Rewst Organization A, Rewst Organization B, and Rewst Organization C can all be mapped to CSP Customer 1 if they represent the same underlying CSP customer.&#x20;
3. Avoid Multiple CSP Customers for One Rewst Organization:&#x20;
   * The new error message ensures a Rewst Organization is not linked to multiple CSP Customers to avoid conflicts.&#x20;
   * **Example**: Rewst Organization A should not be mapped to CSP Customer 1, CSP Customer 2, and CSP Customer 3.&#x20;

### Example Explanation

In this example, the Rewst Organization "The Kewp" is mapped to two different CSP Customers: "thekewp" and "Rewst Development." This setup triggers an error message indicating a conflict: _"One or more organizations are linked to multiple customers. This will cause errors when attempting to run Microsoft actions on these organizations."_&#x20;

<img src="../.gitbook/assets/Screenshot 2024-07-03 at 3.57.05 PM.png" alt="" data-size="original">

### Resolution Steps&#x20;

To resolve these errors, you need to ensure that "The Kewp" Rewst Organization is mapped to only one CSP Customer. Follow these steps:&#x20;

1. **Map** Rewst Organization "The Kewp" → CSP Customer "thekewp".&#x20;
2. **Remove** the relationship mapping between Rewst Organization "The Kewp" and CSP Customer "Rewst Development".&#x20;

After making these changes, save your results to ensure the workflow executes correctly without conflicts.&#x20;

### Practical Mapping Example&#x20;

Here’s how to correctly set up your mappings:&#x20;

* **Correct Setup Example 1**:&#x20;
  * Rewst Organization A → CSP Customer 1.&#x20;
  * Rewst Organization B → CSP Customer 2.&#x20;
  * Rewst Organization C → CSP Customer 3.&#x20;
* **Correct Setup Example 2**:&#x20;
  * Rewst Organization A → CSP Customer 1.&#x20;
  * Rewst Organization B → CSP Customer 1.&#x20;
  * Rewst Organization C → CSP Customer 1.&#x20;
* **Incorrect Setup (Conflict)**:&#x20;
  * Rewst Organization A → CSP Customer 1, CSP Customer 2, CSP Customer 3.&#x20;

By following these mapping rules, you can ensure that your workflows are executed correctly and directed to the appropriate CSP Customer, preventing any unexpected issues.&#x20;

</details>
