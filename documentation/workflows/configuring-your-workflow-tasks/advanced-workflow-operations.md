# Advanced Workflow Operations

### Introduction

Welcome to the guide for Advanced Workflow Operations in Rewst! This document will empower you to take full advantage of Rewst's advanced features, helping you to create more complex and powerful workflows.

Here's a quick peek into what we're going to unpack:

* [**Transition Modes**](advanced-workflow-operations.md#transition-modes): Explore the routes your workflows can take.
* [**Run as Org**](advanced-workflow-operations.md#run-as-org): Learn how to execute actions under different organizational contexts.
* [**With Items**](advanced-workflow-operations.md#with-items): Iterate like a pro and manage bulk operations efficiently.
* **Items Concurrency**: Control how many processes your workflow can juggle at once.
* **Task Timeout**: Learn to adjust the ticking clock for your workflow tasks.

Whether you are tweaking the transition rules for your actions, iterating through items, or adjusting task timeouts, this guide will provide you with the necessary know-how.

Remember, the only limit in Rewst is your imagination (or your API rate limits!). Let's dive right in!

***

### Transition Modes

Transition modes in Rewst are responsible for determining how transitions attached to a workflow action are followed. There are two primary modes:

* **Follow All**: This is the default mode. If your workflow action has multiple conditions attached, the "Follow All" mode attempts to follow all of the specified transitions. In the workflow visualization, this mode is represented by the standard color (see screenshot below).
* **Follow First**: In this mode, conditions are evaluated from left to right and as soon as the first condition is satisfied, the remaining conditions are disregarded. To differentiate these transitions in the workflow visualization, they are color-coded orange (see screenshot below).

{% hint style="info" %}
The colors of transitions in your workflow visualization are indicative of the transition modes. The standard color stands for the "Follow All" mode while orange denotes the "Follow First" mode.
{% endhint %}

### Run as Org

The "_Run as Org_" option allows the workflow action to run in the context of another organization.

### With Items

"With Items" is the equivalent to your "foreach" in other languages.

With this, you can pass a number of objects into a certain action and collect the results from each and then do something.

In our example below, we're going to list every user that is enabled in our tenant and then create or update a contact for each one.

We will make certain assumptions with you reading this that you understand the basics of Rewst. However, if you need a refresher, then read all about workflow inputs and outputs [here](https://docs.rewst.help/documentation/workflows/data-input-and-output).

Below, we have the workflow itself. We are listing all enabled users and then outputting this to a data alias called

```django
{{ CTX.all_users }}
```

The data alias has the following Jinja:

{% code overflow="wrap" %}
```django
{{ [users for users in TASKS.m365_list_users.result.result.data.value if users.enabled == true] }}
```
{% endcode %}

We then have a subworkflow that creates or updates a contact. As per the best practice, we are using a subworkflow with our "With Items"

In the Advanced tab, we then set the "With Items" field with this data alias.

The action now has the additional icon indicating that it has a "With Items" set on it.

During testing or for example if creating tickets from an alert, you may sometimes want to limit the amount of noise you get during this phase.

For example if you have 100 users, you probably only want to test the workflow on 3/4 of them initially to make sure it works as expected.

If you create an input variable on the workflow called "max\_tickets\_to\_create\_per\_action" (this doesn't have to be the exact name, it makes it easier to identify in the future) and set it to the max number of times you want that "With Items" to run.

If you have it set to 1, it'll only run on a single object within CTX.all\_users.

The below code is that what you would use in the "With Items" field in the Advanced tab.

```django
{{ CTX.all_users[:CTX.max_tickets_to_create_per_action | int] }}
```

### You've now created a "With Items" action, but how do I use inputs now?

Because you are iterating through CTX.all\_users on the action, you cannot use \{{ CTX.all\_users.X \}} as the property for the input.

Instead, you must use `{{ item() }}`

Say you want to get the first name of each user as an input, on your With Items action you would do:

```django
{{ item().firstName }}
```

### Items Concurrency

If you're running a workflow action with items, this allows you to set how many of these processes run at the same time. It is recommended that not more than 10 concurrent actions be performed at a time for performance reasons.

### Task Timeout

This allows you to adjust the number of seconds to wait for a task to complete. The default value is 10 minutes.

**Want more practice?**

{% hint style="success" %}
[Check out our Rewst Foundations Courses](../../../cluck-university/rewst-foundations-10x/).
{% endhint %}
