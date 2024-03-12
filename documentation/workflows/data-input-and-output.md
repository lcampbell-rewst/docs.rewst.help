# Data Input and Output

### Overview

In this guide we will discuss:

* Workflow actions
* How inputs are passed into a workflow
* Outputs from workflows or individual actions

### Workflow Actions

Workflow actions refer to the pre-built interfaces that Rewst has available to interface with another platform. Below are descriptions of different parts of workflow actions.

#### Workflow Action Configuration

<figure><img src="../../.gitbook/assets/workflow_action (1).png" alt=""><figcaption></figcaption></figure>

1. **Workflow name**: The workflow name should be descriptive of what it does to help readability in your workflow.
2. **Workflow Action Description:** This tells you what workflow action type.
3. **Task ID:** This is a unique value that you can use when trying to identify issues with workflows.
4. **Description**: This is a field used for humans to store information regarding extended information of the action's purpose.
5. **Publish Result As:** This field allows you to set a [context variable](../../cluck-university/getting-started/rewst-terminology.md#context-variables) with the workflow action results as the value.
6. **Parameters**: These are options that can be passed to the workflow to generate meaningful results. Parameters with a red asterisk are required. You can supply variables as parameters by hitting the green symbol next to the field and entering the replacement using Jinja. For example _"\{{ CTX.ticketnumber \}}"_.
7. **Advanced**: There are a couple of options here. These are covered in the [Advanced Workflow Operations](configuring-your-workflow-tasks/advanced-workflow-operations.md) section.
8. **Mocking**: While mocked a task will not run its typical function and will instead return a user-defined result. You can define a JSON result to return instead.
9. **Time Savings:** This field contains the time saved by this action that would otherwise have to be done by a human.

**Workflow Transitions**

Workflow transitions refer to the means by which a Rewst workflow moves from one workflow action to another. In the advanced options in the workflow body, you can opt to either follow the first (left to right) transition condition that returns true or to follow all transitions from the action. Data transitions are an important part of workflows and are covered later in this workflow action output.

### Workflow Input

Workflow inputs are commonly known as input variables. The role of input variables is to provide data that can be used by tasks within the workflow, or into a sub-workflow.

Input variables can be broken down into two parts, a key and the specific data or values that vary, (hence the name _variables)_.

This would be an example of a variable where \[first\_name] is the key and Ashley is the value:

&#x20;               \[first\_name] : "Ashley"

You can add new variables, or modify existing ones, by going to "Configure Workflow Settings"  >> "Input Configuration".

Press the plus (+) next to Input Configuration to see a number of new fields.

1. **Name (Required):** This can be a unique entry relevant to what the aim of the input is going to be. This should not contain spaces.&#x20;
2. **Label:** This text field is used to set a friendly name. It's the field name visible at the time of input.&#x20;
3. **Type:** Short for data type, this field defines what format the data will be in. The most common types are Text (general string), Integer (whole number), and String (a combo of characters).&#x20;
4. **Default Value:** You can specify a value that will be used if no other input is specified manually.
5. **Description:** You can give a better description of what the field is used for.

The input variables get their values in a Rewst workflow through the workflows initial trigger event.

> Any data type that is valid in JSON can be used as an input variable.

#### Example

An example of an input variable, using static data, can be seen below:

<div align="center">

<figure><img src="../../.gitbook/assets/input-configuration-example (1).png" alt=""><figcaption></figcaption></figure>

</div>

### Workflow Action Inputs

We now have variables created within our workflow, they become [Context Variables](../../cluck-university/getting-started/rewst-terminology.md#context-variables) and can be used directly in action inputs.

In our example below, we are creating a user in Microsoft 365 using three variables:

1. First Name
2. Last Name
3. Domain

For now, these are all specified directly on the workflow rather than being submitted via a form, etc.

<figure><img src="../../.gitbook/assets/input-configuration-example (2).png" alt=""><figcaption></figcaption></figure>

We have then created an action by dragging it from the integration list on the left menu.

<figure><img src="../../.gitbook/assets/m365-create-user-example-action.png" alt=""><figcaption></figcaption></figure>

When you click on this action, you get a number of inputs on the right-hand side.

<figure><img src="../../.gitbook/assets/m365-create-user-example-inputs.png" alt=""><figcaption></figcaption></figure>

Clicking the icon to the right of the field opens up a Monaco editor, the same type that VSCode uses, to allow us to enter code.

You can learn more about the [code that Rewst uses, called Jinja, here](../jinja/intro-to-jinja.md).

In our image below, we can see how to use the variables by using CTX, which stands for Context, and then the name of the variable. This will autocomplete to make it easier for you to reference.

![](../../.gitbook/assets/workflow-action-outputs1.png)

```django
{{ CTX.first_name }}
{{ CTX.last_name }}
{{ CTX.domain}}
```

Despite the data being static at this point, the process is the same regardless of where the data is coming from.

### Workflow Output

Similarly to the above, you can configure an output of a workflow. These are generally used in two situations:

1. In an [Options Generator](workflow-generated-options.md) workflow, the output is what is passed through to the form. For example, if you have a workflow that lists users in a variable called `{{ CTX.users }}` - you would configure an output variable of options mapped to this variable, as per the below image. This then, in the form, would list the users in a dropdown field. This is how dynamic data works in form - more about that in [types of workflows](different-types-of-workflows.md).

<figure><img src="../../.gitbook/assets/output-configuration-example.png" alt=""><figcaption></figcaption></figure>

2. The other time this would be used is if you have a sub-workflow. A sub-workflow is no different from a standard workflow, except for the fact it lives within another workflow. If you were passing data back from the sub-workflow into the main workflow, this would be done via an output variable.

### Workflow Action Outputs

This is probably one of the most important sections because the entire point of Rewst is that you can integrate various platforms into that workflow and use data from each to do something else.

In our example, we will get a list of users where the userPrincipalName matches X, then create a ticket using information from that request.

First, we will take the action of "List Users" from the Graph integration on the left menu. There are no inputs required here, it will list every user on the tenant that it is integrated with / or the [trigger](../triggers/intro-to-triggers.md) is set for.

<figure><img src="../../.gitbook/assets/output-configuration-example (1).png" alt=""><figcaption></figcaption></figure>

If you run this now, you'd get the list of users, but you wouldn't be able to use that data anywhere.

This is where [Transitions](../../cluck-university/getting-started/rewst-terminology.md#transitions) come into play.

If you click the "On Success" transition on the action, you have the option to create a Data Alias.

A data alias allows you to create a variable, similar to an input variable, but with data direct from an action API request. In our example below, we are creating a variable with the key called "user\_details" and populating it with the data of the user using Jinja.

<figure><img src="../../.gitbook/assets/data-aliases-example.png" alt=""><figcaption></figcaption></figure>

{% code overflow="wrap" %}
```django
{{ [ user for user in TASKS.m365_list_users.result.result.data.value if user.userPrincipalName == "RewstDocs@rewst.io" ] }}
```
{% endcode %}

We will then take our "Create Ticket" action from our respective PSA from the integrations menu on the left. In our example, we'll use Datto PSA.

<figure><img src="../../.gitbook/assets/transitions-example.png" alt=""><figcaption></figcaption></figure>

Using our newly created data alias, we can then add our inputs onto that "Create Ticket" input.

<figure><img src="../../.gitbook/assets/data-alias-ticket-title-example.png" alt=""><figcaption></figcaption></figure>

```django
User Exists {{ CTX.user_details.displayName }}
```

This would create a ticket with the title "User Exists RewstDocs@rewst.io".
