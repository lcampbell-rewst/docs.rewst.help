---
description: Real-world Application
---

# Part 2: How to Take Action on Workflow Results

{% embed url="https://youtu.be/cahSSPTLM7E" %}

## Introduction

In this video, we discuss how to apply the concept of completion handlers to Rewst crates. The focus is on utilizing completion handlers to enhance the new employee onboarding workflow and notify MSP clients of successful onboarding. The goal is to create an email template, and a new completion handler, and connect it to the employee onboarding workflow.

***

## Importance of Completion Handlers in Rewst

By keeping workflows synced, users can benefit from updates and optimizations pushed by Rewst. The alternative, unsyncing a workflow for customization, is discouraged if your use case doesn't require it, as it might lead to missing out on valuable updates.

Completion handlers offer a solution. They allow users to customize workflows without unsyncing them, providing flexibility while still leveraging the benefits of synced workflows.

***

## Understanding Data from Employee Onboarding Workflow

The key to creating a meaningful completion handler is to understand the data available in a workflow, such as user information (name, last name, email)

To verify the data, we use the Jinja live editor, ensuring that the right information is accessible for customization without breaking the workflow.

***

## Building the Email Template

Once the data is identified, we can create an email template using Jinja syntax. The template includes variables for first name, last name, and email address. This ensures that the email notification to the company includes essential information about the successfully onboarded user.

***

## Creating a Completion Handler Workflow

The completion handler workflow is designed to initiate when the employee onboarding workflow is completed. We keep it simple and work through the process of creating a simple workflow with three steps:

1. **Begin**: A noop (no operation) to initiate the workflow.
2. **Organization Validation**: A noop that checks if the organization is correct using a custom condition based on the completed workflow tag.
3. **Send Email**: Uses the core send mail action to send the previously created email template.

***

## Turning the Workflow into a Completion Handler

The final step involves configuring the workflow as a completion handler. We demonstrate how to set it up to run when the triggering workflow (employee onboarding) is completed. This ensures that the completion handler reacts to successful onboarding events.

***

## Conclusion

In conclusion, we highlight the simplicity of the process and encourage users to apply this example to other Rewst crates. Completion handlers, combined with synced workflows, offer immediate value and flexibility for MSPs. Users can customize their workflows without sacrificing updates and enhancements provided by Rewst.

Feel free to reach out in the Cluck U channel on Discord or consult your Customer Success Manager if you have any questions. Happy optimizing, and we'll see you in the next video!
