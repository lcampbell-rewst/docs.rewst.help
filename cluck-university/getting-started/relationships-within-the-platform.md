# Relationships within the Platform

## Introduction

There are a number of different components to Rewst and whilst we will delve deeper into the specific components throughout the guides on the site, it's important to understand how these link together.

## Inputs and Outputs

At a high level, it's important to consider what inputs and outputs you need in your automation. Some good questions to consider are the following:

1. What needs to kick off the workflow?
2. What steps are needed in the workflow?
3. What error handling should be in your automation?
4. What is the expected output when the automation is complete?

With this, let's look at how to handle Inputs in Rewst.

## Triggers

Every automation needs something to kick it off. On the platform, we do this through the use of _Triggers._ Triggers can be from a Form, a webhook, or some specific integration triggers, such as creating a ticket in Halo.

### Triggers and Integrations

In a workflow, there are triggers that have a field called "Integration Overrides." These overrides control the client's ability to use the top-level integration. For instance, if you add "Datto PSA" to the override on a trigger, it enables the client to create a ticket using the API keys configured on your account.

### Triggering a Workflow with Forms

One of the most common use cases is using forms to trigger a workflow. Forms can be created and presented to the user. When the form is filled out, and the user clicks _Submit,_ it can trigger an automation. This means that every form must be added to a workflow as a form trigger. Once a form is added as a form trigger, Rewst generates a URL to access the form.

###
