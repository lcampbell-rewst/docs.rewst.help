# Intro to Triggers

### Overview

In this guide, we will discuss what triggers are and how to use them in association with both workflows and forms.

There are two ways to use a trigger currently

1. A trigger is used on any form input that requires a workflow. If you, on a form, click the "Dynamic" button then you absolutely must also create a trigger on the workflow associated.
2. A trigger is also used to run a workflow. This can either be in testing or in production.

### How to create a trigger

Click into a workflow and across the top bar, there is a icon.

<div align="left">

<figure><img src="../../.gitbook/assets/add-trigger.png" alt=""><figcaption></figcaption></figure>

</div>

Pressing this brings up a small form for you to fill in. Note that you can have multiple triggers per workflow, such as a webhook and a trigger that runs when a ticket gets saved in the PSA.

<figure><img src="../../.gitbook/assets/add-trigger-form.png" alt=""><figcaption></figcaption></figure>

The above image contains every setting for a trigger.

<table data-full-width="false"><thead><tr><th width="267">Item</th><th>Description</th></tr></thead><tbody><tr><td>Name</td><td>The name of the trigger. Can be anything you want.</td></tr><tr><td>Enabled</td><td>On or Off</td></tr><tr><td>Organizations</td><td>Select all the orgs that exist within Rewst that may need to use this workflow. If you add a new client, they will have to be ticked in that workflow trigger.</td></tr><tr><td>Integration Override</td><td>When a workflow is triggered by, and is thus running within the context of, a managed organization, by default they only have access to "their own" integrations/configurations (i.e. the managed org's Microsoft Graph tenant). In order to give the workflow access to integrations/credentials owned by the parent organization (i.e. the MSP) that default behavior must be explicitly overridden to say "regardless of who this workflow is running for, use the ConnectWise Manage integration belonging to the MSP". In the above image, the trigger allows your clients to use your PSA, RRM and Licencing integration.</td></tr><tr><td>Trigger Type</td><td>There are a number of types to choose from, such as a webhook, form submission, ticket saved, M365 alerts etc</td></tr><tr><td>Form</td><td>If your trigger type is a form submission, you would select the form that the workflow links to</td></tr></tbody></table>

### How to use a trigger on a form

Once the trigger has been created on a workflow, it can be used on a form. NB: This MUST be an Options Generator workflow, [whose requirements can be found here](../workflows/different-types-of-workflows.md).

<figure><img src="../../.gitbook/assets/form-trigger.png" alt=""><figcaption></figcaption></figure>

The above is a snippet from a form where a dropdown field has been selected and the output will be based on the workflow output. When running the form, so long as the client is added on the trigger and the trigger is set on the form, the workflow will run and the options put into the form field.

**Want more practice?**

{% hint style="success" %}
[Check out our Rewst Foundations Courses](../../cluck-university/rewst-foundations-10x/).
{% endhint %}
