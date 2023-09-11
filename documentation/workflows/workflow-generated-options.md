# Workflow Generated Options

### What are Workflow-Generated Options?

WF-Generated options allow forms to be highly dynamic. When a form field uses a WFGO, it runs a workflow within the trigger context of the form to provide a list of values to that field.

### Using WF-Generated Options

Option Generating workflows are built with the workflow editor but are configured to output data in a specific way to a form.

They show up in the workflows list with the tag `Options Gen`

### Creating an "Option Generator" Workflow

Create a workflow:

* In the **Variables** configuration section of the workflow, Set the **Workflow Type** to `Option Generator`
* Create an **Output** variable with the name of `options`
  * When the workflow runs, it should result in a context variable `{{ CTX.options }}` that contains a list of items with key/value pairs that will be referenced in the Form editor
  * The values here will be used in the **Label Field** an **Value Field** for a form _Field_
    * The **Label** is what gets shown to the user who fills out the form as an available choice.
    * The **Value** field will be set to the value of the **Field Name** when that form is submitted. Workflows will reference this as `{{ CTX.<field_name> }}`
    * :new: Using the **Default Selected Field** will evaluate an attribute of the `options` list for _truthiness_. Items which evaluate `true` will be selected by default when this field populates.
* Workflow-generated Forms can utilize **Input** Variables as well. If these are specified in the Workflow editor, then the Form Editor will allow you to choose what values to use for these. These can be manually set, or they can be the result of previous Form value entries.

**Want more practice?**

{% hint style="success" %}
[Check out our Rewst Foundations Courses](../../cluck-university/rewst-foundations-10x/).
{% endhint %}
