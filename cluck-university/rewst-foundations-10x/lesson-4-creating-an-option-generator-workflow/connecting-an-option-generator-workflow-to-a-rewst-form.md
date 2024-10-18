---
description: >-
  Now all that's left is connecting that workflow to the "Add or Remove User -
  Microsoft Groups" form...the one you created in  the "Building a Basic Form
  and Workflow" lesson.
---

# Connecting an Option Generator Workflow to a Rewst Form

## Module Overview

:bulb: In this last module we'll update the Rewst form to use the Option Generator built in the previous module. If you skipped ahead and don't have that form, or any workflows, don't worry - you can still catch up. So whether you're watching this to continue building what we started earlier in this course, or just to see how Option Generators work, let's jump in to see how it's done!

### Video (5_:55 Minutes)_

{% embed url="https://youtu.be/7TWjgVSnEus" %}



<details>

<summary>Step 1: Connecting a form to an Option Generator Workflow</summary>

1. **Navigate** to the Form created in [101-laying-the-foundations-of-automations-1](../101-laying-the-foundations-of-automations-1/ "mention")
2. **Reorder** the fields, moving "Action" between the User and Group field.
3. **Select** the Group field and **enable** "Workflow Generated".
4. In the "Workflow" field, **select** your Option Generator
   1. You can find it easier by **typing** its title
5. In "Label Field" **enter** "displayName"
6. In Trigger, **select** the trigger to the Option Generator.
7. Under Workflow Inputs:
   * **Select** "Populate from form field" for the action field
     * **Select** `action` from the dropdown
   * **Select** "Populate from form field" for the user\_id field
     * **Select** `user_id`
8. **Save** the Form.

</details>

<details>

<summary>Step 2: Testing the Option Generator</summary>

1. **Select** the View Usages (_List Icon_)
2. **Select "**View Direct URLs" -> "Open the URL for your Organization"
3. **Select** a User
4. **Choose** add or remove.
5. **Click** the Group field dropdown.

</details>

### Action Item

* Test the form to ensure the Group field populates with different options based on the selected action.

## Navigation

<table data-card-size="large" data-column-title-hidden data-view="cards" data-full-width="false"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center">Go to the previous module:<br><a data-mention href="using-jinja-in-data-aliases-and-creating-an-api-request-action.md">using-jinja-in-data-aliases-and-creating-an-api-request-action.md</a></td><td align="center"></td><td></td></tr><tr><td align="center">Go to wrap up the lesson:<br><a data-mention href="./#next-steps">#next-steps</a></td><td align="center"></td><td></td></tr></tbody></table>
