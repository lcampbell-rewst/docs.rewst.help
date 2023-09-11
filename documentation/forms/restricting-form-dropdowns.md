---
description: Restricting Form Dropdown Options with Organization Variables
---

# Restricting Form Dropdowns

The Onboarding form includes a number of fields to be filled out when onboarding new users. The default behavior of all the dropdown fields is to pull the list of options from the API. This is because the dropdown fields have _Dyanmic Options_ set.

<figure><img src="../../.gitbook/assets/dynamic-options (1).png" alt=""><figcaption></figcaption></figure>

While this may work in many cases, there are scenarios where it makes sense to limit the number of options based on the customer segment you're working with. An example of this might be that you need to limit which email domains each customer sees. You may also want to limit which locations customers can choose from. In any case, you can set specific values for the _default\_form_ Organization Variables to use in your forms.

{% hint style="info" %}
Using the User Onboarding Form and Workflow The example we'll be looking at is specifically for the User Onboarding Form and Workflow as it is currently the most likely use-case.
{% endhint %}

### Adding an Organization Variable to a Form

You can add default values for any of the Form Organization variables below:

{% hint style="info" %}
To view the form org variables table, [click here](form-organizational-variables.md).
{% endhint %}

### How to Limit the Email Domains in the Onboarding Form

As noted above, a good use case for this is to limit the email domains that customers can choose from to simplify their experience and potentially make the form more secure. To do this, you can do the following:

#### Add the Org Variable to an Organization

1. **Go to** Configuration → Organization Variables.
2. **Click** _Add_ at the top right.
3. **Type** in the following for the new Organization Variable:
   * Name: form\_default\_email\_domain
   * Value: `["email domain"]`
   * Category: General
   * Organization: Choose Your Organization

<figure><img src="../../.gitbook/assets/org-variable-settings.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Variable values must exist Any value you add to a variable must exist in the list that the form value is pulling from. An example of this would be that any email domain added as a default must exist in the list that is pulled from the Microsoft API.
{% endhint %}

Next, the variable can be added to the form field.

#### Add the Org Variable to the Form Field

1. **Go to** Automations → Forms.
2. **Open** the User Onboarding Form.
3. **Click** to open the settings for the _Email Domain Name_ field.
4. **Type** _true_ in the `schema.enumSourceWorkflow.input.force_default` setting.
5. **Type** _email\_domain_ in the `schema.enumSourceWorkflow.input.choose_variable` setting.

{% hint style="info" %}
You only need to add the latter half of the `form_default` variable when adding it to the `schema.enumSourceWorkflow.input.choose_variable` setting.
{% endhint %}

6. **Save** the Form.

{% hint style="danger" %}
Make sure to set the Org variable values for any Company Organization using the form For example, maybe there are three Company Organizations that need to use the same form with a list of 3 domains to choose from. Each Organization needs to have the variable added with the domain values set. If you only set the variable and values in Company 1, the other two Companies won't see any options to choose from.
{% endhint %}
