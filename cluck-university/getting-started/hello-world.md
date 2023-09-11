# Hello World

{% embed url="https://www.youtube.com/watch?v=ZrSLd-ybfaA" %}

***

### **Introduction:**

Imagine a support automation scenario where you want to send an email notification whenever someone fills out a form. Instead of tackling the entire complex process right away, we'll start by creating an automation that sends a basic email notification. Let's proceed step by step.

***

### Hello World Automation Exercises

Follow these steps to build your first Hello World automation!

<details>

<summary>Step 1: Create a Basic Form to Enter a Message</summary>

**Add a Form**

1. **Go to** _Automations_ → _Forms_ in the menu.
2. **Click** _Add_ at the top right to add a new Form.
3. **Type** _Hello World Form_ for the name.
4. **Click** Submit.

**Add a Text Input field**

1. **Drag and Drop** a _Text Input_ field.
2. **Click** on the field to open the field settings.
3. **Type** "send\_message" for the _Field Name_.
4. **Replace** the default _Field Label_ text with "Send Message".
5. **Type** "Type in a message to send here" for the _Field Description_ text.
6. **Click** the _Required_ checkbox.

**Save the form**

1. **Click** the _Save_ button at the top right of the form builder.
2. **Click** _Submit_ on the pop-up to confirm.

</details>

<details>

<summary>Step 2: Build a Workflow to Send an Email</summary>

**Create a New Workflow**

1. **Go to** _Automations_ → _Workflows_ in the menu.
2. **Click** _Create_ at the top right to add a new Workflow.
3. **Type** _Hello World Workflow_ for the name.
4. **Click** Submit.

**Add the Starting \_Noop**\_\*\* Action to the Canvas\*\*

1. **Open** the _Core_ section in the left Actions menu.
2. **Drag and Drop** the _noop_ action to the Workflow Canvas.
3. **Replace** the default _core\_noop_ name with _send\_message_.
4. **Type** "This action starts the workflow" for the _Description_.

**Add a \_sendmail**\_\*\* Action to Send the Message\*\*

1. **Open** the _Core_ section in the left Actions menu if it's not already open.
2. **Drag and Drop** the _sendmail_ action to the Workflow Canvas.
3. **Replace** the default _core\_sendmail_ name with _to\_email_.
4. **Type** "This action sends the email" for the _Description_.
5. **Type** the following for the next several fields:
   * Sender: Choose a Sender
     * This demo uses noreply@rewst.io, but you will need to choose a Sender from the list shown for you.
   * Recipient: Your own email
   * Subject: Hello World
   * title: This is a Test

**Add Basic Jinja to Reference the Form Input.**

1. **Click** on the Jinja editor button next to the _message_ field.
2. **Type** the following to reference what we type in the form:

```django
{{ CTX.send_message }}
```

3. **Close** the editor.

**Create a Transition**

1. **Click and Drag** the transition from the _noop_ action to the _sendmail_ action.
   * To do this, you will need to hover over the gray circle under the _On Success_ section of the _noop_ action.

**Publish to Save the Workflow**

1. **Click** _Publish_ to save the Workflow.
2. **Click** _Submit_ on the pop-up to confirm.

</details>

<details>

<summary>Step 3: Connect the Form to the Workflow with a Trigger</summary>

**Add a Form Trigger**

1. **Click** the _Add Trigger_ button at the top menu.
2. **Type** "Hello World Trigger" in the _Name_ field.
3. **Click** the _Enabled_ slider.
4. **Choose** _Core - Form Submission_ for the _Trigger Type_.
   * You can type _form_ to see the option.
5. **Choose** the _Hello World Form_ form under _Trigger Parameters_ → _Form_.
6. **Click** Submit at the bottom.

**Save the Workflow**

1. **Click** _Publish_ to save the Workflow with the new Trigger and Configuration.
2. **Click** _Submit_ on the pop-up to confirm.

</details>

<details>

<summary>Step 4: Send a Message!</summary>

**View the Form URL**

1. **Click** the _View Direct URLs_ button next to _Dynamic Form URL_.
   * If the Trigger isn't still open then click _Edit Trigger_ at the top menu next to our Form Trigger
2. **Click** on the link.

**Send Hello World!**

1. **Type** "Hello World!" in the form field.
2. **Click** _Submit_.

</details>

***

### Conclusion

Congratulations! You've just built your first automation—an email notification triggered by form submission. While this example is simple, it showcases the essence of automation and sets the stage for more complex workflows.

Feel free to explore other available actions and continue building your automation skills. Your journey into automation has just begun, and we're excited to see what incredible automation you'll create in the future.
