# Part 1: Introduction to Completion Handlers

{% embed url="https://youtu.be/F5qS8LWQE6Y" %}

## Introduction

\
Completion Handlers in Rewst provide a mechanism to extend or modify existing workflows without altering their core structure. They offer flexibility, especially for pre-built automations or 'Crates.' This documentation will guide you through configuring Completion Handlers to either trigger another workflow after the existing one finishes or execute the current workflow when another workflow is completed.

***

## Terminology

* Completion Handler: An event that fires upon the completion of a workflow.
* Workflow Listener: Another term for a completion handler.
* Crates: Pre-built Rewst Workflows that you can use directly or modify according to your needs.

***

## Steps to Configure a Completion Handler

1. Locate Existing Workflow: Navigate to the Rewst dashboard and find the workflow you wish to extend, for example, "Hello World."
2. Completion Handler Options: Click on the workflow's settings and locate the 'Completion Handlers' section. You will see two options:
   1. Run this workflow when another one completes
   2. When this workflow is completed, do something
3. Define Trigger Conditions:
   1. Choose the workflow to trigger.
   2. Specify the conditions such as `succeeded`, `failed`, `timed out`, or `canceled` under which it will trigger.
4. Save Settings: Click on the 'Submit' or 'Save' buttons to apply your changes.

***

## Hands-on: Creating a New Workflow as a Handler

{% hint style="warning" %}
If you don't have the Hello World workflow made, [you can build it here](../../getting-started/hello-world.md).
{% endhint %}

1. Navigate to Automation: Go back to the dashboard and find the 'Workflows' section.
2. Create New Workflow: Click 'Create New' and give it a name, for example, "I'm Listening to Hello World."
3. Add Actions: Add the required actions; in this example, a simple 'Send Email' action suffices to demonstrate the completion handler.
4. Publish Workflow: Once configured, publish the new workflow.
5. Set Up the Handler: Return to your original "Hello World" workflow and set up a completion handler to trigger the new workflow.
6. Execute Workflow: Trigger the original workflow by filling out its associated form.
7. Verify Outcome: Check your email to confirm that you received two emails, one from the original workflow and another triggered by the completion handler.

***

## Conclusion

\
Completion handlers provide a versatile way to extend the functionalities of existing workflows, be they custom-built or from Crates. They allow for a layered approach to automation, enabling additional actions based on the outcomes of other workflows, without requiring you to alter the original workflows.
