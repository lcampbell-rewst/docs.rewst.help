# Agent Smith Configuration Overview

Agent Smith operates as an Azure IoT Hub instance, integrated with Rewst workflows for command communication to endpoint agents. The agent software, running as a Windows Service on devices, registers via a webhook trigger in Rewst, creating an IoT Hub entry and receiving configuration data.

## Setup Process

1. **Azure Integration**:
   * Install the [Microsoft Azure Integration](../../documentation/integrations/cloud/microsoft-azure/microsoft-azure-integration-setup.md) and Authorize it if it is not already set up.
   * Note: Azure Key Vault must be setup in your subscription first.
2. **Install Agent Smith Crates**:
   * Install [Agent Smith: Device Provisioning](https://app.rewst.io/marketplace/crates/018c3c3f-bc76-7e33-ae40-d5f185085ef5) first.
   * Follow with [Agent Smith: Service Provisioning](https://app.rewst.io/marketplace/crates/018c3c33-0863-77ab-83d3-a2a1c75f119a).
3. **Provision IoT Hub Service**:
   * The second crate will install a form named `Agent Smith: Service Configuration`
   * Select Create IoT Hub Instance, specify Azure Subscription, desired location, unique IoT Hub Name, and Service Tier.
   * Submit and monitor for success.
4. **Update the Secret Key:**
   * Open the `Agent Smith: Agent Registration Workflow` trigger configuration.
   * Edit the Agent Smith Registration Webhook Trigger
   * In the dropdown selector for Secret Key choose `iothub_registration_secret`
5. **Provisioning Agents:**
   * Access `Agent Smith: Service Configuration` form again.
   * Select `Display Agent Configuration Instructions`.
   * Choose an Organization
   * The form will display instructions for using `PowerShell` to configure the Agent for that organization. It also shows how the ORG ID is filled in, so one could use an existing RMM to deploy the agent using variables.
   * **Ensure PowerShell is up-to-date on devices.** Only up-to-date versions of PowerShell have been tested to work.
   * Begin with a few agents for initial testing.
6. Testing:
   * Return to the form and select `Run PowerShell Code on Agent`.
   * Type some PowerShell code or use what's pre-filled.
   * Monitor workflow status to see the agent return data.

## Troubleshooting

* Ensure admin-level account setup so the service will install as SYSTEM
* Verify recent MS PowerShell version on devices.
* Check device connectivity to Azure IoT Hub via MQTT: `<your_iothub_name>.azure-devices.net:8883`.

<details>

<summary>FAQs and NYAQs</summary>

* **Can I customize Agent Smith?**
  * Yes, you're free to [fork and modify it](https://github.com/RewstApp/rewst\_remote\_agent).

<!---->

* **Will new features be added?**
  * Focus is on simplicity. Essential features missed initially might be considered.

<!---->

* **Support for older operating systems?**
  * No, support for outdated OS is not available.

<!---->

* **MacOS and Linux support?**
  * Planned for the near future.

</details>

