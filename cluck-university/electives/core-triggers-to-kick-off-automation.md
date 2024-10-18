# Core Triggers to Kick-off Automation

{% embed url="https://youtu.be/pyaKTRP6-BI" %}

In this video, we will explore various types of triggers that are foundational for automating workflows. We'll cover everything from form submission triggers to time-based and webhook triggers, providing you with all the knowledge you need to set up and manage automation effectively.

## Core Trigger Types

**1. Form  Triggers**

* **Overview**: Form submission is a common trigger that initiates automation when a user submits a form.
* **Setup**:
  1. Create a form relevant to your automation.
  2. Connect the form to your workflow.
  3. Set the form submission as a trigger so that the automation starts as soon as the form is submitted.
* **Example Usage**: Automating data entry into a database when a customer fills out a contact form.

**2. Time-Based Triggers**

* **Time Interval Trigger**:
  * **Description**: This trigger activates an automation at regular intervals.
  * **Configuration Options**: You can set intervals like every five minutes, hourly, daily, or weekly.
* **Cron Trigger**:
  * **Description**: More specific than time interval triggers, Cron triggers allow you to specify complex schedules using Cron syntax.
  * **Setup**:
    1. Choose the time and frequency (e.g., 4 AM every Monday).
    2. Configure the Cron schedule using the correct syntax.
    3. Set your time zone, typically UTC by default, which can be adjusted as needed.
  * **Example**: Running a backup script at midnight every Friday.

**3. Webhook Triggers**

* **Overview**: Webhook triggers are used to start an automation based on events that occur within external services that support webhooks.
* **Implementation**:
  1. Obtain the webhook URL from the platform you are integrating with.
  2. Insert the secret key (if required) to authenticate the incoming data.
  3. Set the webhook as the trigger in your automation platform.
* **Example Usage**: Triggering an automation when receiving new feedback on a platform like Canny.

## Setting Up Your Triggers

To set up a trigger, navigate to the automation platform's workflow canvas:

1. **Access the Triggers Section**: Click on the lightning bolt icon at the top of the workflow canvas.
2. **Add a New Trigger**: Click to add a new trigger and provide a name for it.
3. **Configure Trigger Settings**: Choose the type of trigger and configure any necessary parameters.
4. **Enable the Trigger**: Activate the trigger when your setup is complete.

## Conclusion

Triggers are essential components in automating tasks and processes. By understanding and utilizing different types of triggers, you can significantly enhance the efficiency and reliability of your automated systems.&#x20;

{% hint style="success" %}
For more on Triggers, check out our [rewst-foundations](../rewst-foundations/ "mention") training where we work through a full automation example.
{% endhint %}
