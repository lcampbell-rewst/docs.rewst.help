# Core Triggers

Core triggers in Rewst are predefined mechanisms that initiate workflows without depending on external integrations. There are five main types of core triggers currently supported by Rewst:

### Always Pass

&#x20;This trigger is primarily used to apply integration overrides. It does not initiate any actions but is crucial for setting up Options Generators that require integration overrides.

### Cron

Cron Triggers are used to schedule tasks that need to run automatically at specific times or intervals. This flexibility allows for a wide range of scheduling options such as daily, monthly, or yearly tasks.

* **Examples**:
  * Daily at 6:00 AM
  * Annually on March 24th
  * On the first Monday of each month
  * During the second week of the month

### Form Submission

This trigger activates a workflow based on the submission of a Rewst form. It is an effective way to automate processes immediately after data collection from form inputs.

### Time Interval

&#x20;Time intervals can be set to trigger a workflow repeatedly over specified periods. This trigger is suitable for workflows that need to recur on a regular basis.

* **Examples**:
  * Every 5 minutes
  * Every hour
  * Daily
  * Weekly

### Webhook

&#x20;A webhook trigger allows external services to initiate a workflow by sending data directly to Rewst. This is particularly useful for integrating with other applications or services that support webhooks.

{% hint style="success" %}
Check out our [using-webhook-triggers.md](use-cases-and-examples/using-webhook-triggers.md "mention") page for a more detailed example!
{% endhint %}
