---
description: Welcome to the sixth course in the Rewst Foundations series!
---

# 106 - Sub-Workflows and With Items

## Introduction

Hello and welcome! In Rewst 106, we'll complete our workflow and explore how to use Sub-Workflows and With Items in Rewst. Sub-Workflows enable us to utilize workflows within other workflows, creating a parent-child relationship. With Items is a feature in Rewst that allows actions or workflows to run on all items in a list simultaneously. We'll demonstrate how to leverage these functionalities to manage group memberships efficiently.&#x20;

When you've completed this training,[ don't forget to get credit!](https://app.rewst.io/form/1339a9d0-a298-4e2e-8d40-2fa1626509a8)

## Watch the video and follow along with the steps below

{% embed url="https://youtu.be/r2LMDkzp3ac" %}

## Get Credit

{% hint style="success" %}
To get credit for completing this session offline, please [submit this form](https://app.rewst.io/form/1339a9d0-a298-4e2e-8d40-2fa1626509a8).
{% endhint %}

## Follow Along

### Part 1: Creating a Parent Workflow in Rewst

First, we're going to build a new parent workflow that starts by getting the User from the form.&#x20;

<details>

<summary>Step 1: Building the new Parent Workflow</summary>

**Setting Input Configuration Variables**

1. **Create** a new workflow named "Add or Remove User from Multiple Groups".
2. **Add** Input Configuration variables:
   * _action_
   * _user\_id_
   * _group\_ids_
3. **Set** type to _List_ for group\_ids.
4. **Click** Submit.

**Adding **_**Get User**_** Action**&#x20;

1. **Add** a _Get User_ action from the Microsoft Graph category.
2. **Rename** the action _get\_user_.
3. **Set** the parameter _User ID_ to `{{ CTX.user_id }}`.
4. **Click** the _On Success_ transition.
5. **Create** a Data Alias:
   * _Key_: `target_user`
   * _Value_: `{{ RESULT.result.data.value }}`

</details>

### Part 2: Adding a Sub-Workflow and Utilizing With Items

Next, we're going to add our original workflow as the Sub-Workflow and modify the form and Form Trigger to take advantage of With Items.

<details>

<summary>Step 2: Adding a Sub-Workflow into the Parent Workflow</summary>

**Add the **_**Add or Remove Group Membership**_** workflow**

1. **Add** the _Add or Remove from AzureAD Group_ workflow from the _Workflows_ category.
   1. This is the workflow that was updated in Rewst 105; adding this action makes it a Sub-Workflow.
2. **Connect** _On Success_ transition of _get\_user_ to the sub-workflow.
3. **Rename** the Sub-Workflow to "modify\_group\_member".
4. **Set** _With Items_ in the Advanced tab to `{{ CTX.group_ids }}`.
5. **Configure** the _Parameters_ of the sub-workflow.
   * _action_: `{{ CTX.action }}`
   * _user\_id_: `{{ CTX.user_id }}`
   * _group\_id_: `{{ item() }}`

</details>

<details>

<summary>Step 3: Modifying the Form Trigger</summary>

**Configuring **_**Add or Remove User from AzureAD Group Form**_

1. **Navigate** to _Add or Remove from AzureAD Group_ form.
   * (Optional): Clone the form, to keep a copy of the form, and work on the cloned copy going forward.
   * (Optional): Rename the form to _Add or Remove from AzureAD Groups Form_.
2. **Add** a Multi-Select Field to the form.
3. **Configure** the Multi-Select field:
   * _Field Name_: `group_ids`
   * _Field Label_: Groups
   * _Field Description_: Select the groups to add to or remove from.
   * _Dynamic Options_: Enabled
   * _Workflow Generated_: Enabled
   * _Workflow_: Option Generator for Groups based on User Membership
   * _Label Field:_ displayName
   * _Trigger:_ Option Generator
   * _Workflow Inputs:_ Note the variable at the end of the name. Check _Populate from form field_ and select the variable that corresponds with each input.
4. **Remove** the previous Group field.

**Add the Form as a Trigger for the Parent Workflow**

1. **Return** to the parent workflow.
2. **Add** a form trigger to Add or Remove User from Multiple Groups
   * _Name_: Form Trigger
   * _Enabled_ toggled
   * _Trigger Type_: Core - Form Submission
   * _Form_: Add or Remove User from AzureAD Groups
3. **Click** Submit.

</details>

### Part 3: Collect the Modification Results and Send Email Notifications

Next, we're going to capture the results and store them in a list in order to send the information via email.

<details>

<summary>Step 4: Sending Feedback to the User</summary>

**Get the Results**

1. **Add** a noop below _modify\_group\_member_.
2. **Rename** it "collect\_modification\_results".
3. **Connect** modify\_group\_member's On Success transition to _collect\_modification\_results_.
4. **Click** _collect\_modification\_results_'s transition.
5. **Create** a Data Alias:
   * key: `modification_results`
   * value:

```django
{{
    [    
        modification.result.group_result    
        for modification in TASKS.modify_group_member.collected_results
    ]
}}
```

**Set Up Rewst to Email the Results**

1. **Add** a Core sendmail action below _collect\_modification\_results_.
2. **Connect** _collect\_modification\_results_'s transition to _core\_sendmail_.
3. **Click** _core\_sendmail_.
4. **Set** the Parameters:
   * Recipient: `{{ CTX.user.username }}`.
   * Subject: User `{{ CTX.target_user.displayName | d }}` Group Modification
   * Title: User `{{ CTX.target_user.displayName | d }}` Group Modification
   * Message:

{% code overflow="wrap" %}
```django
The group memberships for {{ CTX.target_user.displayName|d }} have been modified:


* {{ CTX.modification_results | join('\n* ') }}
```
{% endcode %}

</details>

### Part 4: Testing the Workflow

Finally, we'll test it all out to see how it works!

<details>

<summary>Step 5: Test It</summary>

**Adding or Removing a User to Multiple Groups**

1. **Access** the form.
2. **Select** a user.
3. **Select** Add or Remove.
4. **Select** multiple groups.
5. **Confirm** that an email is received with the feedback messages.

</details>

## Conclusion

Thank you for watching! We hope this course helps you effectively utilize Sub-Workflows and With Items in Rewst for efficient workflow management. If you have any questions or need further assistance, don't hesitate to reach out. Happy automating!

## What Did You Learn?

Take a quick quiz and get instant feedback!

{% embed url="https://www.surveymonkey.com/r/KC106" %}
Knowledge Check
{% endembed %}

## Additional Resources

{% hint style="info" %}
For more information about With Items and Sub-Workflows, check out our documentation:

* [With Items](../../documentation/workflows/configuring-your-workflow-tasks/advanced-workflow-operations.md#with-items)
* [Sub-workflows](../../documentation/workflows/different-types-of-workflows.md#subworkflow)
{% endhint %}

## Need more guidance?&#x20;

{% hint style="warning" %}
MAJOR UPDATE: The last live training sessions for Rewst 101-106 are happening August 12-14 (for Rewst 101 - 103) and August 19-21 (for Rewst 105 - 106).

Office Hours remain open, so sign up for live support on Thursdays at the link below.

Stay tuned for exciting new self-paced content and special live sessions for beginners coming in September 2024!
{% endhint %}

<table data-card-size="large" data-view="cards"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center"><mark style="color:blue;"><strong>Rewst 106</strong></mark></td><td align="center">Sub-Workflows and With Items</td><td><a href="https://calendly.com/cluck-u/rewst-106">https://calendly.com/cluck-u/rewst-106</a></td></tr><tr><td align="center"><mark style="color:blue;"><strong>Cluck U Office Hours</strong></mark></td><td align="center">Come and Get Help!</td><td><a href="https://calendly.com/cluck-u/office-hours">https://calendly.com/cluck-u/office-hours</a></td></tr><tr><td align="center"><a data-mention href="foundations-certification.md">foundations-certification.md</a></td><td align="center">Get certified!</td><td></td></tr></tbody></table>
