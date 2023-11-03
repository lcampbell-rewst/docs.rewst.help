# Configuring Your Workflow Tasks

## Introduction

In this guide, we'll walk you through the journey of a workflows task—from selecting the action in the sidebar to its configuration on the canvas. You'll learn about the different options available, their functions, and how to use them effectively to shape your workflows to your requirements.

***

## Placing an Action onto the Canvas

Each action your workflow will take begins its life in the sidebar, residing under the Actions panel within its [respective integration](../../integrations/). To bring a task into the canvas, simply drag and drop it onto your workflow. Now, it's time to give this task a closer look.

Click on the task, and a configuration window opens up, featuring a set of basic details at the top and four distinct tabs beneath: `Parameters`, `Advanced`, `Mocking`, `Time Savings`, and `Security`. Each of which are described below:

### Task Basic Details

These are the first things you see when you click on a task:

* **Name**: A user-editable field for the task's identifier.
* **Reference**: The Integration pack and workflow name this task belongs to.
* **Output**: Specifies where the task's output gets stored in the task logs.
* **Task ID**: The unique ID for referencing this task.
* **Description**: A user-fillable text box for additional task information.
* **Publish Result As**: A friendly name you assign for the task's results that you can use as an a context variable for calling it's content in future tasks.

***

### Task Configuration Tabs

These tabs hold specific configuration options for your task:

#### Parameters

Unique to each task, this tab houses options for defining the task's behavior during execution, including settings for endpoints, filters, conditions, and query parameters.

#### Advanced

In this tab, you'll set the rules for your task's path and behavior within the workflow. Options include Transition Mode, Task Transition Criteria Sensitivity, Run as Org, With Items, Items Concurrency, and Task Timeout.

{% hint style="info" %}
See more about this on the [Advanced Workflow Operations](advanced-workflow-operations.md) page.
{% endhint %}

#### Mocking

The Mocking tab provides the option to simulate the task's function with a user-defined result, useful for testing and debugging.

#### Time Savings

In this tab, specify your estimate of the time a human would need to complete the task. This is used for creating Time Entries in PSA platforms.

{% hint style="info" %}
See more about this on the [Adding Time Saved to a Workflow](adding-time-saved-to-a-workflow.md) page.
{% endhint %}

#### Security

The Security tab in Rewst allows for meticulous redaction of sensitive information within workflow tasks. This is especially vital when using generic HTTP actions for services without official integrations, where API tokens or other sensitive data in headers could be exposed in results.

**Quick Guide:**

* **Redact on Hover**: Use the new eyeball icon next to parameter labels to quickly redact values.
* **JSONPath Queries**: Customize redaction with [JSONPath queries](https://jsonpath.com/) for both input and output parameters.
* **Layered Security**: Securely store secrets and ensure they are redacted from all task logs and results to maintain data confidentiality.

For a hands-on demonstration, see how to securely handle sensitive information in workflows from the April 21st Open Mic. The relevant portion of the video is shared below:

{% embed url="https://youtu.be/oJA16EXizzY?t=694" %}
See the timestamped walkthrough of our redact functionality here
{% endembed %}

***

### Task Transitions

Task transitions are the bridges that connect different tasks, ensuring that workflows move forward as designed. They represent the conditions under which a task progresses to the next step(s) in the workflow.

<figure><img src="../../../.gitbook/assets/task_transition.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
To dive deeper into task transitions, criteria, and advanced configurations, refer to the [Navigating between Tasks With Transitions](navigating-between-tasks-with-transitions.md) page of this documentation.
{% endhint %}

***

As you configure your tasks, remember that the real power of Rewst lies in its flexibility. So, personalize your tasks and let your workflows reflect the uniqueness of your process requirements.
