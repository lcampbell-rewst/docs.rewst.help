# Agent Smith Configuration Overview

Agent Smith operates as an Azure IoT Hub instance, integrated with Rewst workflows for command communication to endpoint agents. The agent software, running as a Windows Service on devices, registers via a webhook trigger in Rewst, creating an IoT Hub entry and receiving configuration data.

## Setup Process

### 1. Microsoft Azure Integration
* Install and Authorize: (If not already set up)


### 2. Agent Smith Crates Installation
* Device Provisioning: Install first.
* Service Provisioning: Install second.


### 3. IoT Hub Service Provisioning
* The second crate will install a form named Agent Smith: Service Configuration
* Navigate to this form and choose Action: Create IoT Hub Instance
  * Select the proper Azure Subscription, desired location, type in a unique IoT Hub Name, and select the desired Service Tier
  * Submit the Form and monitor workflow results for Success


### 4. Workaround for Installation Bug
* Agent Registration Workflow: Update the secret key in the trigger configuration.
  * Open Agent Smith: Agent Registration Workflow.
  * Update the Agent Smith Registration Webhook Trigger.
* In the dropdown selector for Secret Key choose iothub_registration_secret


### 5. Provisioning Agents
* Return to the same form and choose Display Agent Configuration Instructions
* Choose an Organization
* The form will display instructions for using PowerShell to configure the Agent for that organization. It also shows how the ORG ID is filled in, so one could use an existing RMM to deploy the agent using variables.
* Only Up-to-date versions of PowerShell have been tested to work. Make sure your devices are updated!
* Provision one or a few agents to test with


### 6. Testing
* Return to the form and choose Run PowerShell Code on Agent
* Type some PowerShell code or use what's pre-filled.
* Monitor workflow status to see the agent return data.


### 7. Using with new or existing Workflows
* Agent Smith uses the Microsoft Azure integration, so you will need to add that as an Integration Override to any workflows which will use it.
* This includes anything that calls the "Run PowerShell" sub-workflows, such as New Employee, etc.


### 8. Optional - Agent Smith: Track Agent Inventory In Azure Tables Crate
* This Marketplace Crate will Add some additional capabilities to your Agent Smith Deployments
* It uses Azure Tables to store additional information about your agent endpoints.
 * Automatic (via Task Scheduler) Agent Data Collection Check-Ins including Installed Applications and Services
 * Automatic Restart of the agent (via Task Scheduler) if the Service stops


## Uninstalling

#### Windows
The Agent installs itself as a Service. You can use PowerShell or the sc command to modify / remove the service.
Application logs and data are installed in C:\ProgramData\RewstRemoteAgent (or whatever root path you've overridden that to in you environment)
Application Program files are in %ProgramFiles%\RewstRemoteAgent folders



## Troubleshooting

* Ensure admin-level account setup so the service will install as SYSTEM
* Verify recent MS PowerShell version on devices.
* Ensure that no firewalls are not preventing communications with Rewst or your IoT Hub. Check the [Rewst Security Configuration Page](https://docs.rewst.help/security) for details.
* Ensure that endpoint security software is not preventing executions or comms.
* Check device connectivity to Azure IoT Hub via MQTT: `<your_iothub_name>.azure-devices.net:8883`.
* Get Packet Captures from the agent while workflows are running. This can help us determine if the Agent is properly communicating with the IoT Hub and/or the Rewst Engine.



## FAQs and NYAQs (not-yet-asked-questions)

* **Can I customize Agent Smith?**
  * Yes, you're free to [fork and modify it](https://github.com/RewstApp/rewst\_remote\_agent).

* **Will new features be added?**
  * Focus is on simplicity. Essential features missed initially might be considered.

* **Can you add Feature X?**
  * Probably not! Our goal is super simplicity. IF people are asking for something that we really should have thought of from the beginning, we may add it, but...
  * If you're wanting to add functionality that could be done by writing a PowerShell script and kicking it off with a workflow: Do that.

* **Support for older operating systems?**
  * No, support for outdated OS is not available.

* **MacOS and Linux support?**
  * Planned for the near future.


