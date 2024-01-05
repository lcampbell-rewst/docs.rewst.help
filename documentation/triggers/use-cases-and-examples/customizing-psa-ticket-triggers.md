# Customizing PSA Ticket Triggers

## Introduction

In Rewst, setting specific trigger criteria for PSA Ticket triggers can be crucial to ensuring that workflows are initiated only under certain conditions. This page provides a step-by-step approach to customizing these triggers.

***

## Getting Started with Trigger Setup

### **Navigate to Workflow Creation**

* Go to [Rewst](https://app.rewst.io).
* Select `Workflows` > `Create`.
* Enter a workflow name, like `Trigger Criteria Finder`.
* Click `Submit` to proceed to a blank workflow creation screen.
* Add a single [no-op](../../workflows/actions-in-rewst/core-actions.md#no-operation-noop) action to the canvas, name it `BEGIN` and then click `Publish` to save your workflow. (No other actions are needed, as we will just be working with triggers.)

### **Accessing Trigger Configuration**

Click the lightning bolt icon at the top to `Add Trigger`.

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

### **Setting up the Trigger**

* Name & Enable your trigger.
* Choose the trigger type relevant to your PSA ticket system:
  * **ConnectWise PSA:** `Ticket Record Saved`.
  * **Datto PSA**: `Ticket Webhook` (Ensure webhooks are enabled as per [Rewst Documentation](https://docs.rewst.help/documentation/integrations/psa/autotask-datto-psa/webhook-configuration)).
  * **Halo PSA:** `New Ticket Record`.
* Under `Trigger Criteria`, select the graph icon.

<div align="left">

<figure><img src="../../../.gitbook/assets/image (18).png" alt="" width="404"><figcaption></figcaption></figure>

</div>

The trigger is now active and will capture data when a new ticket is submitted. This screen is listening for your ticket records to be saved, and will show you live results as they come in.

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

***

## Testing the Trigger with a PSA Ticket

To see the trigger in action follow the below steps&#x20;

### **Creating a Test Ticket**

* In your PSA system, create and classify a new ticket with desired criteria.
* Submit the ticket.
* You should see the ticket record appear in Rewst.

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
Once the ticket is visible in Rewst, click the pause button to stop more tickets from coming in while you're building your trigger criteria.
{% endhint %}

### **Selecting Criteria**

Find and click the values in the ticket you want as trigger criteria. They will have their corresponding path entered into the Trigger Criteria on the right.

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

***

## Finalizing and Implementing Trigger Criteria

### **Saving Your Criteria**

* After selecting all desired criteria, click `Save` then `Close`.
* Your trigger criteria are now set and visible.

### **Applying Criteria to Workflows**

* Copy these criteria values.
* Paste them into other workflows you are configuring.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

***

## Conclusion

This process allows for precise control over when your workflows are triggered, enhancing the automation's effectiveness. Experiment with different criteria to tailor your workflows to specific needs.
