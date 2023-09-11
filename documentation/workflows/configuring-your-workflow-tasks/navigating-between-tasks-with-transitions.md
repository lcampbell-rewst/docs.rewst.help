---
description: >-
  Explore how to direct workflow progression using task transitions, set
  conditions for task outcomes, and manage data efficiently with Data Aliases.
---

# Navigating Between Tasks With Transitions

## **What Are Task Transitions?**&#x20;

Task transitions are represented by the small rectangles found directly beneath each task. They determine the sequence of task execution, specifying the path from one task to the next. Depending on the criteria set, one task might branch out to multiple subsequent tasks. When you interact with these rectangles by clicking on them, a configuration panel appears.

**Transition Configuration Options**:

* **Edit Transition**: Buttons beside the Edit Transition title give you options to either clone the current transition, or remove it if it's no longer needed.
* **Custom Label**: An editable field allowing you to give a meaningful name to the transition, aiding clarity as your workflow grows.
* **Move Left/Right**: These are controls that allow you to rearrange the sequence in which transitions are evaluated and executed.
* **Condition**: It's the criteria that governs the task's progression based on the options defined below. Depending on the outcome of this task, this rule determines which path to follow next.&#x20;
* **Data Aliases**: Tool for labeling specific data for later use. This is especially useful when you need to reference specific task results or parameters in future tasks. Clicking the `plus` button lets you define an alias to be passed through on this transition.

**Available Transition Criteria**:

* **Success**: Chosen when you want the next task(s) to be triggered only if the current one completes successfully.
* **Failure**: Use this option if you want a subsequent task to be initiated of the failure of this task.
* **Always**: A catch-all criterion. No matter the outcome of the current task, the next task(s) under this criterion will always be executed.
* **Custom**: For those times when you need a specific, detailed condition. Use Jinja evaluations to articulate nuanced transition rules.

***

## **Diving into Data Aliases**&#x20;

For a seamless and efficient workflow, how you handle data is paramount. This is where `Data Aliases` come into play.

* **What is a Data Alias?**: Think of it as a custom label you assign to specific data. When the workflow runs, you can access these through `CTX` variables.
* **Example**: If you set an alias like `my_task_result -> {{ RESULT }}`, later tasks can refer to this data using `{{ CTX.my_task_result }}`.
* **Key -> Value Mapping**: When adding a new data alias, you'll need the following:
  * **Key**: The name you assign to specific data.
  * **Value**: The actual data it corresponds to. The code editor button allows for the use of Jinja customization for intricate data or expressions
