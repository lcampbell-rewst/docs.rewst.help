---
description: >-
  While it's easy for us, as the builders, to spot errors in the workflow
  execution results, it's much harder for someone filling out the form.
---

# Implementing Error Handling with Feedback Messages

## Module Overview

Looking at every possible "ending point", we'll want to communicate to the person that submits the request form what happened. We'll do this via email, but first we need a handy way to get those feedback messages describing what happened.

### Video (5_:18 Minutes)_

{% embed url="https://youtu.be/CaTi4rl-sm8" %}

Log into Rewst and complete the following steps

<details>

<summary>Step 1: Adding a Feedback Message for Dynamic Groups</summary>

1. Select the "Dynamic" transition of the "check\_group\_type" action
2. Add a Data Alias:
   * **Key**: feedback\_message
   * **Value**: The Group`{{ CTX.group.displayName | d }}`is a Dynamic Group and can not be directly modified. You will need to edit its membership Rules to modify this.

</details>

<details>

<summary>Step 2: Adding Feedback Messages for Graph Add Action</summary>

1. **Select** the On Success Transition of add\_group\_member\_graph
2. **Add** a Data Alias:
   * **Key:** feedback\_message
   * **Value:** User was successfully added to Graph Group `{{ CTX.group.displayName | d }}`.
3. **Select** the On Failure Transition of add\_group\_member\_graph
4. **Add** a Data Alias:
   1. **Key:** feedback\_message
   2. **Value:**  Failed to add User to Graph Group `{{ CTX.group.displayName | d }}`.

</details>

<details>

<summary>Step 3 Adding Feedback Message for Graph Remove Action</summary>

1. **Select** the On Success Transition of remove\_group\_member\_graph
2. **Add** a Data Alias:
   * **Key**: feedback\_message
   * **Value**: User was successfully removed from Graph Group `{{ CTX.group.displayName | d }}`.
3. **Select** the On Failure Transition of remove\_group\_member\_graph
4. **Add** a Data Alias:
   * **Key**: feedback\_message
   * **Value**: Failed to remove User from Graph Group `{{ CTX.group.displayName | d }}`.

</details>

<details>

<summary>Step 4: Adding Feedback Messages for Exchange Online Add Actions</summary>

1. **Select** the On Success Transition of add\_group\_member\_ex
2. **Add** a Data Alias:
   * **Key**: feedback\_message
   * **Value**: User was successfully added to Exchange Online Group `{{ CTX.group.displayName | d }}`.
3. **Select** the On Failure Transition of add\_group\_member\_ex
4. **Add** a Data Alias:
   * Key: feedback\_message
   * Value: Failed to add User to Exchange Online Group `{{ CTX.group.displayName | d }}`.

</details>

<details>

<summary>Step 5: Adding Feedback Messages for Exchange Online Remove Actions</summary>

1. **Select** the On Success Transition of add\_group\_member\_ex
2. **Add** a Data Alias:
   * **Key**: feedback\_message
   * **Value**: User was successfully added to Exchange Online Group `{{ CTX.group.displayName | d }}`.
3. **Select** the On Failure Transition of add\_group\_member\_ex
4. **Add** a Data Alias:
   * **Key**: feedback\_message
   * **Value**: Failed to add User to Graph Group `{{ CTX.group.displayName | d }}`.
5. **Publish** the Workflow.

</details>

### Action Item

Test the workflow and check the workflow results to find the feedback\_message Data Alias as a context variable.

### Navigation

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td>Previous Module:</td><td><a data-mention href="adding-error-handling-to-workflow-actions.md">adding-error-handling-to-workflow-actions.md</a></td><td></td></tr><tr><td>Go to Wrap Up the Lesson:</td><td><a data-mention href="./#next-steps">#next-steps</a></td><td></td></tr></tbody></table>

