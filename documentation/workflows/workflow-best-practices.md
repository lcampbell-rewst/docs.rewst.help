---
description: >-
  There are often multiple ways to achieve a single goal, however, there are
  certain best practices that should try to be followed when interacting with
  Rewst to ensure you get the best performance.
---

# Workflow Best Practices

## Introduction

This guide presents the best practices for working with Rewst to create and modify workflows, ensuring a consistent and high-quality experience with your integrations. These recommendations align with the standards and guidelines that our internal ROC team and service partners follow when building workflows with Rewst. By adhering to these practices, you can leverage the same principles that guide our experts, enhancing the efficiency, reliability, and maintainability of your automation.

## Design Principles

At Rewst, we believe in designing workflows with simplicity, modularity, and maintainability at their core. Here's how you can benefit from our principles:

* **Simplicity**: Create workflows that are user-friendly and easy to understand.
* **Modularity**: Break down workflows into smaller, reusable components.
* **Maintainability**: Build workflows that are straightforward to update and maintain.

## Automation Build Standards

When building workflows in Rewst, consider the following standards:

* **Consistency**: Standardized practices lead to a consistent experience across different workflows.
* **Quality Assurance**: Adhering to standards makes quality checks more efficient.
* **Reusability**: Modular design enables the reuse of components, speeding up development.
* **Maintainability**: Following standards ensures easy maintenance.
* **Scalability**: Design your workflows to handle increased complexity as your needs grow.
* **Efficiency**: Avoid redundancy by following a standardized approach.
* **Knowledge Transfer**: Standards foster collaboration and knowledge sharing within your team.
* **Flexibility**: Rewst's standards allow easy integration of new features without major rework.

## Designing and Testing Workflows

When designing workflows, consider the following best practices:

* **Utilize Templates**: Start with pre-defined templates to speed up development and ensure adherence to best practices.
* **Testing and Iteration**: Develop and test your workflows in a sandbox or development environment. Make necessary amendments, test, and sync to your live environment.

## Automation Naming and Categorization

Properly naming and categorizing your workflows is essential for clarity and navigation. Here's how our internal teams to make the most of Rewst's features:

### **Naming Conventions**

Adhering to a consistent naming convention helps in understanding the purpose and function of each automation:

* **Generic Automations**: `Function: Brief Description - Stage X: Stage Description`
* **Product-Specific Automations**: `Function - Product: Brief Description - Stage X: Stage Description`

Here's how to interpret each component:

* `Function`: Primary function or system.
* `Brief Description`: Succinct description of the automation.
* `Stage X`: Sequence or stage of the automation.
* `Stage Description`: Role of the specific stage.

### **Categorization Guidelines**

Use categories or tags within Rewst to organize your automations effectively:

* **Source Category**: Indicate the origin or purpose of the automation.
* **Platform Category**: Specify the platform or service it interacts with.
* **Execution Type Category**: Distinguish between main workflows and subworkflows.

Adopting a consistent approach to naming and categorizing will streamline navigation and collaboration within your team.

## Managing Variables and Tasks

### Setting Your Output Variables

In Rewst, every automation can function as either an executing workflow or a module. For example, a `New User` workflow might primarily serve as a `Main` workflow, but some people might want to add a wrapper to enable bulk user addition, transforming it into a `Module`.

To maintain consistency across various implementations, it's essential to ensure that every automation has an output variable. By doing so, you can achieve uniformity in your builds, regardless of whether the automation is used as a main workflow or a module.

Here's a guideline to follow:

* **Output Name**: `automation_log`
* **Output Value**: `{{ CTX.automation_log }}`

By adhering to this practice, you create a consistent structure that enhances the manageability and adaptability of your automations.

### Structuring Your Build

Every build should include three essential tasks:

1. **The First Task**:
   * **Name**: `BEGIN`
   * **Data Alias**: `automation_log`
   * **Value**: `[]`
2. **The Last Task**:
   * **Name**: `END`
3. **The Failures**:
   * **Name**: `failure_detected`
   * **Data Aliases**: Utilize data aliases to handle failures, log information, and provide detailed error messages.

### Automation Log

The automation log in Rewst is a recommended data alias used across all automations for easier debugging, better logging, and filtering based on user requirements.

* **Example**: If there are logs of different types, you can use an Org Variable to filter the logs to be created as ticket notes.

### Handling Data Aliases

When working with data aliases, follow these practices:

* **Separation**: Separate complex data aliases into noops rather than creating them on the actual task doing the API call.
* **Debugging Consideration**: Separating the data aliases makes debugging easier, allowing you to test your code with real data.

### Working with Transitions

Transitions are essential for controlling the flow of your automations. Here are some tips:

* **SUCCEEDED, FAILED Conditions**: Use conditions like `{{ SUCCEEDED and CTX.list_of_things | length > 0 }}` to control the flow based on task success or failure.
* **Transition Order**: Transitions are evaluated from left to right, so order them carefully.
* **Simon Says (Follow All/Follow First)**:
  * **Follow All**: The task will follow every path that meets the criteria.
  * **Follow First**: The task will follow the first criteria that it matches and then stop. Use this when you expect only one condition to be met.

## Limiting API Field Results

In your interactions with Rewst, efficiency and performance are key. Limiting the API field response to only the data you need is an essential practice that supports these goals.

* **Initial Exploration**: If you're unsure about the fields you need, consider running the query without any filtering initially. This approach lets you explore the available fields and understand what information is at your disposal.
* **Selecting Specific Fields**: Once you've identified the necessary fields, be sure to limit the response to include only those. For instance, if you're listing users in Microsoft Graph and only require the UPN (User Principal Name), you should select the `userPrincipalName` and `id` fields.

By adhering to this practice, you minimize unnecessary data retrieval, streamline your workflows, and align with the efficiency standards that guide our internal teams at Rewst.
