---
description: >-
  Explore the key concepts of the Rewst platform, from integrations to
  workflows. This guide provides a clear overview of essential terms and
  functionalities.
---

# Rewst Terminology

## **Introduction**

As you embark on your journey with Rewst, you may come across a range of terms and concepts unique to our platform. This guide is designed as a quick reference, helping you dive into each term in-depth and ensuring a smooth and insightful experience. You can navigate through the clickable table of contents or use the search functionality for specific terms.

### **Table of Contents**

1. [#getting-set-up-in-rewst](rewst-terminology.md#getting-set-up-in-rewst "mention")
2. [#building-automation](rewst-terminology.md#building-automation "mention")
3. [#prebuilt-automation](rewst-terminology.md#prebuilt-automation "mention")

***

## Getting Set Up in Rewst

***

### Integrations

The integrations are the various products that Rewst has connections into. You will need to supply various details such as an API key and URL for the product.

For more information, see: [integrations](../../documentation/integrations/ "mention").

***

### Organizations

An organization refers to a group or entity within the Rewst platform that can have its own variables, forms, workflows, and users. It can be managed by an admin who has access to various functionalities and can customize the platform according to the organization's needs.

To create an organization in Rewst, check out: [adding-a-new-client-to-rewst.md](../../documentation/user-management/adding-a-new-client-to-rewst.md "mention")

***

### Organization Variables

Organization variables are used to apply values at the organization and sub-org layers. They are referenced in workflows using the syntax `{{ ORG.VARIABLES.<variable_name> }}`. Organization variables can be inherited by sub-organizations unless a sub-org has the same variable defined, in which case it will override the value.

For more information, see: [organization-variables.md](../../documentation/user-management/organization-variables.md "mention")

***

## Building Automation

***

### Trigger

Triggers are components in Rewst that are used to initiate workflows or perform actions based on specific events or conditions. They can be used to respond to form submissions, webhook events, ticket updates, or other types of triggers. Triggers are configured within workflows and can be customized with various settings, such as integration overrides and trigger types.

For more information, see: [intro-to-triggers.md](../../documentation/triggers/intro-to-triggers.md "mention")

***

### Workflows

Workflows are the bread and butter of automated business processes. They offer a robust action library, customizable tasks, mocking and timeouts for testing, data security options, and ROI measurement. They are the key to unlocking automation in Rewst.

For more information, see: [workflows](../../documentation/workflows/ "mention")

***

### Actions

Actions are what lives inside of a workflow. Each integration has a number of actions within it (and more are added constantly!). You grab these actions from the left menu on a workflow, drag them onto the workflow UI and that is what runs when you run the workflow.

For more information, see: [actions-in-rewst](../../documentation/workflows/actions-in-rewst/ "mention")

***

### Transitions

Transitions are found at the bottom of every action. These determine the path the workflow will take. For example if "Success", then you'll have an arrow coming from that transition to the next action. You also have transitions for failure, always, and custom conditions.

For more information, see:[navigating-between-tasks-with-transitions.md](../../documentation/workflows/configuring-your-workflow-tasks/navigating-between-tasks-with-transitions.md "mention")

***

### Forms

Forms are one of the main ways to get data into a workflow. You can use a selection of fields, both static and dynamic, to retrieve information from a user and then that information is passed into the workflow on submission.

Both dynamic and conditional fields can be used here. For example, if you list groups live from your M365 tenant and then set it to a certain group, you can show other fields as a result of that.

For more information, see: [forms](../../documentation/forms/ "mention")

***

### Templates

Templates can be used as a central store for repeated text. For example, if you always want to create a ticket with the same information you could put that in a template and reference the template within the action itself.

For more information, see: [intro-to-templates.md](../../documentation/templates-messages/intro-to-templates.md "mention")

***

### Jinja

Jinja is a templating language used in the Rewst platform. It is based on Python and allows for more powerful processing of data in workflows. Jinja expressions are encapsulated by double curly braces (`{{ and }}`) and can be used to output the value of variables or expressions. Rewst extends the functionality of Jinja with filters and provides an ever-growing list of filters specific to the platform.

for more information, see: [intro-to-jinja.md](../../documentation/jinja/intro-to-jinja.md "mention")

***

### Context Variables

Context Variables are variables specific to the running workflow. They are referenced in a workflow with `CTX.variable_name`.

***

## Prebuilt Automation

***

### Crates

Crates contain workflows, forms, triggers, templates, and scripts that are packaged together for easy deployment. It allows users to quickly set up automation without having to create workflows from scratch.

For more information, see: [crates](../../prebuilt-automations/crates/ "mention")

***

### Crate Marketplace

The Crate Marketplace is a platform where users can find and install pre-built workflow bundles called Crates. Crates can be found and installed through the Crate Marketplace, which is accessible from the Crates section of the left-hand menu in the app.

For more information, see: [production-crate-list.md](../../prebuilt-automations/crates/production-crate-list.md "mention")

***
