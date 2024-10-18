---
description: Going from one group to many groups.
---

# Updating the Add or Remove User  Form

## Module Overview

For automation efficiency, we've decided to add or remove a user to or from multiple groups with every form submission. That means we need to update the form to let us pick more than one group.

### Video (4_:15 Minutes)_

{% embed url="https://youtu.be/TmHTHXuOqP0" %}

Log into Rewst and complete the following steps

<details>

<summary>Step 1: Adding a Multi-Select Field to the Form</summary>

1. **Navigate** to the Add or Remove user - Microsoft Group Form
2. **Select** the Group Field&#x20;
3. **Che**ck Hidden to hide the Group
4. **A**dd a Multi-Select field

</details>

<details>

<summary>Step 2: Configure the Multi-Select Field</summary>

1. **Configure** the Multi-Select field
   * Field Name: `group_ids`
   * Field Label: Groups
   * Field Description: Select one or more groups
2. **Toggle** Dynamic Options
   * Label Field: displayName
   * Trigger: Option Generator
3. **Check** populate from form field for action under Workflow Inputs
   * **Select** `action`
4. **Check** populate from form field for user\_id under Workflow Inputs
   * **Select** `user_id`
5. **Save** the form
6. **Preview** the form

</details>



### Navigation

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td>Previous Module:</td><td><a data-mention href="using-a-sub-workflow-to-update-multiple-groups.md">using-a-sub-workflow-to-update-multiple-groups.md</a></td><td></td></tr><tr><td>Go to the Next Module:</td><td><a data-mention href="creating-a-new-parent-workflow.md">creating-a-new-parent-workflow.md</a></td><td></td></tr></tbody></table>
