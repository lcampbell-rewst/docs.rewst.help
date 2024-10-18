---
description: >-
  Implement the sketch from the previous module by creating an Options
  Generator, configuring its initial inputs and output, and setting up the
  appropriate trigger.
---

# How to Create, Configure, and Trigger an Option Generator Workflow

## Module Overview

:bulb: Planning a workflow before building speeds up the process by sorting out logistics upfront, so you can focus on execution later. The inputs and outputs are key to this module—without them, the options generator won't work.

### Video (4_:23 Minutes)_

{% embed url="https://youtu.be/cXp2GFEb4iU" %}

Log into Rewst and complete the following steps.

<details>

<summary>Step 1: Create a Workflow</summary>

1. **Create** a new workflow called "Option Generator for Microsoft Groups."
   * Personalize the name and add tags to your liking.
2. **Select** the pencil icon to configure the workflow settings.
3. **Select** "Option Generator" for the workflow type.
   * As a bonus, this will add an "option gen" tag to your workflow, so you can easily filter for those in your list of all the workflows.
4. **Add** Time Saved
5. **Add** the _Input Configurations_
   * `user_id`
   * `action`
6. **Add** the _Output Configuration_
   * Field Name: options
   * **Select** the Jinja Editor Icon
   * **Enter** `CTX.group_list`

7: **Select** _Submit_ to save the settings

</details>

<details>

<summary>Step 2: Add Workflow Trigger</summary>

1. _**Select**_ the lightning bolt to add a workflow trigger.
2. **Enter** "option generator" for the name
3. **Toggle** Enabled to enable the trigger.
4. **Search** for "always" in the "trigger type" dropdown
5. **Select** 'Core - Always Pass.'
   * The workflow will trigger as soon as we have a "user" and an "action" selected - before the form is submitted.
6. **Select** Microsoft Graph for integration override.
7. **Select** your own organization
   * Test with a user you're comfortable with (maybe yourself).
   * If you want to use this process for your customers, refer to the special instructions on the Rewst 104 tutorial page in Cluck University
8. **Submit** to save the trigger.

</details>

### Action Item

* Create a workflow and configure its properties, inputs, and outputs to function as an Option Generator.
* Setup a trigger for the Option Generator workflow.
* Add an Integration Override to the Option Generator so it can be used across all your managed organizations. This ensures the workflow is flexible and scalable for different environments

## Navigation

<table data-card-size="large" data-column-title-hidden data-view="cards" data-full-width="false"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center">Go to the previous module:<br><a data-mention href="introduction-to-option-generators.md">introduction-to-option-generators.md</a></td><td align="center"></td><td></td></tr><tr><td align="center">Go to the next module:<br><a data-mention href="using-jinja-in-data-aliases-and-creating-an-api-request-action.md">using-jinja-in-data-aliases-and-creating-an-api-request-action.md</a></td><td align="center"></td><td></td></tr></tbody></table>
