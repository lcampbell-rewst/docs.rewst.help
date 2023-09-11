# Different Types of Workflows

### Overview

Within this guide, we will discuss the different types of workflows and in which situation you would use each one.

### Standard Workflow

This is the most basic of all workflows. As soon as you hit Create on the workflow page, that is what is made, and can then start adding actions to it.

### Subworkflow

This is the same as a standard workflow, except that it is also a part of another workflow. In the example below, we have a main workflow called "Create Ticket" in which we choose which PSA the organization has. Once that has been decided, we then go to a sub-workflow (note the pink border and icon on the action) which has the actual creation of the ticket.

<figure><img src="../../.gitbook/assets/subworkflow-example.png" alt=""><figcaption></figcaption></figure>

There are a few reasons to do this such as:

1. Ensuring a "tidy" workflow - rather than having 20 steps per PSA on a single workflow, we can split it up and make it convenient to read and understand.
2. When doing something on various objects, the equivalent of a "for each", we can pass all of the objects to a sub-workflow and get the output back of each.

Note that you can click the pink icon on a sub-workflow to go directly to it. You can also view sub-workflows on the main workflow page, indicated by the green "Subworkflow" button. This can be clicked to see which workflow it is a part of.

### Option Generator

An option generator is used directly with a form.

If you have a form with a dropdown where you want to list all the users in a tenant, you would use an Option Generator workflow. There are a few things to bear in mind to make sure this works properly, as below

1. Ensure that the workflow type is set to "Options Generator" by clicking the icon at the top. This should be as per the image below

<figure><img src="../../.gitbook/assets/option-generator-workflow.png" alt=""><figcaption></figcaption></figure>

2. Every option generator workflow must have an [output variable](data-input-and-output.md#workflow-output) called options, containing the data that you want to display.
3. You must have a trigger set up on the workflow, which is then selected on the form when selecting the dynamic workflow.

More can be found on [workflow-generated options here](workflow-generated-options.md).

**Want more practice?**

{% hint style="success" %}
[Check out our Rewst Foundations Courses](../../cluck-university/rewst-foundations-10x/).
{% endhint %}
