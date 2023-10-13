# 105 - Improve Group Management to Support Exchange

{% embed url="https://youtu.be/yG6h679xnfk" %}

{% hint style="success" %}
Sign up for our **LIVE** training sessions below!
{% endhint %}

<table data-card-size="large" data-view="cards"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-type="content-ref"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center"><mark style="color:blue;"><strong>Rewst 105</strong></mark></td><td align="center">Improve Group Management to Support Exchange</td><td><a href="https://calendly.com/cluck-u/rewst-105">https://calendly.com/cluck-u/rewst-105</a></td><td><a href="https://calendly.com/cluck-u/rewst-105">https://calendly.com/cluck-u/rewst-105</a></td></tr><tr><td align="center"><mark style="color:blue;"><strong>Cluck U Office Hours</strong></mark></td><td align="center">Come and Get Help!</td><td><a href="https://calendly.com/cluck-u/roc-ama">https://calendly.com/cluck-u/roc-ama</a></td><td><a href="https://calendly.com/cluck-u/roc-ama">https://calendly.com/cluck-u/roc-ama</a></td></tr></tbody></table>

## Introduction

Hello and welcome to Rewst 105, where we focus on managing groups using Microsoft's APIs. We'll learn how to differentiate between different types of groups, whether they are managed using Microsoft Graph or Microsoft Exchange Online. Additionally, we'll explore how to implement feedback messages and handle errors effectively within our workflow.

When you've completed this training, [don't forget to get credit](105-improve-group-management-to-support-exchange.md#get-credit)!

{% hint style="danger" %}
These steps below require [Rewst 102](102-building-a-basic-workflow.md) and [Rewst 104](104-options-generators-and-generic-api-requests.md) to be completed prior to starting the exercise.
{% endhint %}

***

## Managing Groups: Microsoft Graph vs. Exchange Online

Let's talk about how to manage groups efficiently using Microsoft Graph and Microsoft Exchange Online. Understanding the type of group is crucial, as it dictates the API we should use. Here's a breakdown of the group types and their corresponding management methods:

1. #### Dynamic Membership Groups:
   * Dynamic membership groups are identified by the presence of "Dynamic membership" in the group type property. These groups cannot be directly modified through APIs.
2. #### Unified Groups:
   * Unified groups are managed using Microsoft Graph API. They are groups where "unified" is present in the group types property or when mail-enabled is set to false.
3. #### Security Groups:
   * Security groups can be managed using Exchange Online if mail-enabled is set to true. If mail-enabled is false, they are managed by Microsoft Graph API.
4. #### Distribution Groups:
   * Distribution groups are also managed using Exchange Online.

***

### Get Group Object

We'll start by retrieving the group object using the group ID. This action is performed using the Microsoft Graph API.

<details>

<summary>Step 1: Getting the Properties of a Group</summary>

<mark style="color:red;">⚠️ These steps assume you have completed the full steps from Rewst 104 You can find the instructions to make this form on the Rewst 104 Page</mark>

**Add a Get Group Action**

1. **Open** the _Add or Remove from AzureAD Group_ workflow.
2. **Add** a _Get Group_ action from the _Microsoft Graph_ category.
3. **Move** the _Get Group_ action to top of the workflow.
4. **Rename** the _Get Group_ action to "get\_group".
5. **Set** _Group ID_ to `{{ CTX.group_id }}` under _Parameters_.
6. **Click** the _On Success_ transition of _Get Group_.
7. **Create** a Data Alias:
   * _Key_: `group`
   * _Value_: `{{RESULT.result.data.value}}`

</details>

***

### Determine Group Type

Next, we'll use conditional logic to determine the group type based on the group object properties. Depending on the type, the workflow branches out to the corresponding actions.

<details>

<summary>Step 2: Differentiating Group Types</summary>

**Create a Fork in the Workflow**

1. **Add** a noop below the _get\_group_ action to create a new fork in the workflow.
2. **Connect** the _On Success_ transition from _get\_group_ to the new noop.
3. **Click** the noop.
4. **Rename** the noop "check\_group\_type".
5. **Click** Advanced.
6. **Set** the _Transition Mode_ to _Follow First_.

**Identify Dynamic Membership Groups**

1. **Click** the _On Success_ transition on _check\_group\_type_.
2. **Add** "Dynamic Group" as the Custom Label.
3. **Set** the _Custom Condition_ as `{{ "DynamicMembership" in CTX.group.groupTypes }}`.

**Identify Unified and non-Mail Enabled Groups**

1. **Add** another transition labeled "Graph" for _check\_group\_type_.
2. **Set** the _Custom Condition_ as `{{ "Unified" in CTX.group.groupTypes or not CTX.group.mailEnabled }}`.
3. **Connect** the _Graph_ transition to the _add\_or\_remove_ noop.

**Add a Transition for Exchange Online Managed Groups**

1. **Add** another transition labeled _Exchange Online_ for _check\_group\_type_.
2. **Copy** _adding\_or\_removing_.
3. **Rename** the copy to "_adding\_or\_removing\_exo_".
4. **Move** _adding\_or\_removing\_exo_ below and to the right of _check\_group\_type_.
5. **Connect** the _Exchange Online_ transition from _check\_group\_type_ to _adding\_or\_removing\_exo_.

</details>

***

### Add or Remove Users

For Unified and Security Groups managed by Microsoft Graph or Distribution Groups managed by Exchange Online, we'll implement actions to add or remove users based on the group type.

<details>

<summary>Step 3: Implementing Add Using Microsoft Exchange Online</summary>

**Implement Add-DistributionGroupMember**

1. **Add** an _InvokeCommand_ action from the _Microsoft Exchange_ category.
2. **Move** the _InvokeCommand_ action under the _Add_ transition of _adding\_or\_removing\_exo_.
3. **Connect** the _Add_ transition to the _InvokeCommand_ action.
4. **Click** the _InvokeCommand_ action.
5. **Rename** the action "exo\_add\_group\_member"
6. **Enter** `Add-DistributionGroupMember` for _Cmdlet Name_.
7. **Add** the parameters:
   * _Member_: `{{ CTX.user_id }}`
   * _Identity_: `{{ CTX.group_id }}`
   * _BypassSecurityGroupManagerCheck_: `{{ true }}`

</details>

<details>

<summary>Step 4: Implementing Remove Using Microsoft Exchange Online</summary>

**Implement Remove-DistributionGroupMember**

1. **Copy** _exo\_add\_group\_member_.
2. **Click** the copied _exo\_add\_group\_member_.
3. **Rename** the action "_exo\_remove\_group\_member_"
4. **Move** _exo\_remove\_group\_member_ under the _Remove_ transition of _adding\_or\_removing\_exo_.
5. **Connect** the _Remove_ transition to the _exo\_remove\_group\_member_ action.
6. **Enter** `Remove-DistributionGroupMember` for _Cmdlet Name_
7. **Check** the parameters are set:
   * _Member_: `{{ CTX.user_id }}`
   * _Identity_: `{{ CTX.group_id }}`
   * _BypassSecurityGroupManagerCheck_: `{{ true }}`

</details>

***

### Handle Errors and Provide Feedback

Next, we'll incorporate error-handling mechanisms by providing feedback messages for successful or failed actions. This ensures a seamless user experience and clear communication in case of issues.

<details>

<summary>Step 5: Implementing Feedback Messages to Microsoft Graph Actions</summary>

**Output Variable Setup**

1. **Click** Configure Workflow Variable (Pencil icon)
2. **Add** an Output Variable:
   * _Field Name_: `group_result`
   * _Value_: `{{ CTX.group_result }}`
3. **Click** Submit.
4. **Click** Configure Workflow Variable to exit.

**Add On Success and On Failure Messages to \_microsoft\_graph\_add\_group\_member**\_

1. **Click** the _On Success_ transition for _microsoft\_graph\_add\_group\_member_.
2. **Create** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: User was added to MS Graph Group `{{ CTX.group.displayName | d }}`.
3. **Add** a new transition.
4. **Click** the new transition.
5. **Click** _On Failure_ under _Condition_.
6. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: Failed adding the user to Graph Group `{{ CTX.group.displayName | d }}`.

**Add On Success and On Failure Messages to \_microsoft\_graph\_remove\_group\_member**\_

1. **Click** the _On Success_ transition for _microsoft\_graph\_remove\_group\_member_.
2. **Create** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: User was removed from MS Graph Group `{{ CTX.group.displayName | d }}`.
3. **Add** a new transition.
4. **Click** the new transition.
5. **Click** _On Failure_ under _Condition_.
6. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: Failed removing the user from Graph Group `{{ CTX.group.displayName | d }}`.

</details>

<details>

<summary>Step 6: Implementing Feedback Messages to Exchange Online Actions</summary>

**Add On Success and On Failure Messages to \_exo\_add\_group\_member**\_

1. **Click** the _On Success_ transition for _exo\_add\_group\_member_.
2. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: User was added to Exchange Group `{{ CTX.group.displayName | d }}`.
3. **Add** a new transition.
4. **Click** the new transition.
5. **Click** _On Failure_ under _Condition_.
6. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: Failed adding the user to Exchange Group `{{ CTX.group.displayName | d }}`.

**Add On Success and On Failure Messages to \_exo\_remove\_group\_member**\_

1. **Click** the _On Success_ transition for _exo\_remove\_group\_member_.
2. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: User was removed from Exchange Group `{{ CTX.group.displayName | d }}`.
3. **Add** a new transition.
4. **Click** the new transition.
5. **Click** _On Failure_ under _Condition_.
6. **Create** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: Failed removing the user from Exchange Group `{{ CTX.group.displayName | d }}`.

</details>

***

### Workflow Completion and Success

Finally, we'll set up the workflow completion criteria, ensuring that the workflow is considered successful if at least one parent task succeeds.

<details>

<summary>Step 7: Finishing Touches</summary>

**Add an On Failure Message for get\_group**

1. **Create** a new transition for _get\_group_.
2. **Click** the new transition.
3. **Click** _On Failure_ under _Condition_.
4. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: Failed to get Group information for `{{ CTX.group_id }}`.

**Add a Message for Dynamic Groups**

1. **Click** the _Dynamic Group_ transition on _check\_group\_type_
2. **Add** a _Data Alias_:
   * _Key_: `group_result`
   * _Value_: The Group `{{ CTX.group.displayName | d }}` is a Dynamic Group and can not be directly modified. You will need to edit its Membership Rules to modify this.

**Add a Finish to the Workflow**

1. **Add** a noop towards the bottom of the workflow.
2. **Click** the newly added noop.
3. **Rename** the noop "finish".
4. **Set** the _Task Transition Criteria Sensitivity_ to _1_ under _Advanced_.
5. **Connect** the transitions from _graph\_add\_group\_member_, _graph\_remove\_group\_member_, _exo\_add\_group\_member_, and _exo\_remove\_group\_member_ to the finish noop.

</details>

<details>

<summary>Step 8: Test it</summary>

**Try it for yourself**

1. **Choose** a User.
2. **Click** Add or Remove.
3. **Select** a Group.
4. **Check** the results of the workflow to see which action is executed.

</details>

***

### Conclusion

Rewst 105 equips you with the knowledge and skills to manage groups effectively in Rewst. By understanding the nuances of different group types and employing the appropriate APIs, you can efficiently handle group operations within your applications.&#x20;

***

## Get Credit

{% hint style="warning" %}
To get credit for completing this session offline, please [submit this form](https://app.rewst.io/form/4f233131-a105-496f-8904-3153af0a95ba).
{% endhint %}

## Additional Resources

{% hint style="info" %}
For more information on Microsoft Exchange PowerShell Commandlets, check out their documentation:

* [Exchange PowerShell Commandlets](https://learn.microsoft.com/en-us/powershell/module/exchange/?view=exchange-ps)
{% endhint %}
