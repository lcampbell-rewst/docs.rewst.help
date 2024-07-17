# Issue Alerts

<details>

<summary> ⚠️ Forms Users Experiencing Login Delays and Timeouts (July 16th, 2024)</summary>

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

Thank you for your understanding and cooperation. Please contact our support team if you have any questions or need further assistance.

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
