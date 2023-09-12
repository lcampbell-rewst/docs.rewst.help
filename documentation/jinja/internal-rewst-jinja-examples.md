# Internal Rewst Jinja Examples

## Shortcuts & General Help

* Access the Jinja Editor on any fields where you see the code editor icon <img src="../../.gitbook/assets/jinja-burger.png" alt="" data-size="line">(fondly called the Jinja Burger amongst other Kewp Members)&#x20;
* Press `F1` within the editor to see menu and shortcut options
* Press `Ctrl + Space` to get the initial root options
* Add `|` to the end of your variables to access [Jinja filters](list-of-jinja-filters.md). e.g.: `{{ ORG.ATTRIBUTES.id|default('test default string') }}`

***

## Variable Roots

{% tabs %}
{% tab title="CTX" %}
Context Variables are variables specific to the running workflow. They are referenced in a workflow with `CTX.variable_name`. These include [inputs ](../workflows/data-input-and-output.md#workflow-input)provided by the [workflow's trigger](../triggers/intro-to-triggers.md), any [Data Aliases](../workflows/configuring-your-workflow-tasks/navigating-between-tasks-with-transitions.md#diving-into-data-aliases) defined within the workflow, as well as any published results of tasks upon completion.&#x20;
{% endtab %}

{% tab title="ORG" %}
Variables prefixed with `ORG` are related to data and functions specific to the Organization the workflow is running for. Below are the options you can call with the ORG prefix&#x20;

**ORG.HAS\_TAG:**

Description: Returns True if the Organization the workflow is running for has the tag Note: spaces must be replaced by underscores (\_)

Usage: `{{ ORG.HAS_TAG.Advanced_Security }}`

**ORG.VARIABLES:**

Description:

Usage:

**ORG.MAPPING:**

Description: Contains values mapping Organizations in Rewst with those in external systems

Usage: `{{ ORG.MAPPING.ms_tenant_id }}`

**ORG.INTEGRATIONS:**

Usage: `{{ ORG.INTEGRATIONS.microsoft_graph }}`

**ORG.ATTRIBUTES:**

Description: Contains attributes of the organization record, such as the id and managing\_org\_id

Usage: `{{ ORG.ATTRIBUTES.id }}`
{% endtab %}

{% tab title="TASKS" %}
Description: Reference previous tasks by name. Note: spaces must be replaced by underscores (\_), i.e. the "Send Message" task is reference with TASKS.Send\_Message

Usage: `{{ TASKS.list_tickets.result.result[0].id }}`

**TASKS\_RESULT\_DATA:**

Description: Reference previous tasks by name. Shortcut for \{{ TASKS.task\_name.result.result \}}

Note: spaces must be replaced by underscores (\_), i.e. the "Send Message" task is reference with TASK\_RESULT\_DATA.Send\_Message

**Things to keep in mind:**

As a general rule of thumb you will always need to use `.result.result` when referencing a task - with the exception of if that task is a "with items" and it becomes `.collected_results`

These should, for the most part, all autocomplete when you do the dot.
{% endtab %}

{% tab title="UTILS" %}
**UTILS.NOW:**

Description: now(timezone="UTC", dt\_format="timestamp") Default behavior returns the current UTC timestamp as an integer. The optional dt\_format argument accepts a format string, see [https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes)

Usage: `["{{ UTILS.now() }}", "{{ UTILS.now('EST', '%d-%m-%Y %H:%M:%S') }}"]`

**UTILS.uuid4:**

Description: Default behavior returns a new UUID

Usage: `["{{ UTILS.uuid4 }}"]`
{% endtab %}
{% endtabs %}

***

## Rewst's List Comprehension Functionality in Jinja

List comprehensions in Rewst's implementation of Jinja provide a compact way to transform lists, filter them, or generate new lists.&#x20;

{% hint style="info" %}
To read more in depth about this topic, please review the [Jinja List ](use-cases-and-best-practices/jinja-lists.md)[Comprehension](use-cases-and-best-practices/jinja-lists.md) page.
{% endhint %}

***

### **Examples**

This section breaks down two practical examples of how to leverage list comprehensions in your Jinja templates: returning a new list of only a specified attribute, and filtering a list by the existence of a specific value within the specified attribute. Check out the details below.

{% tabs %}
{% tab title="Return a List of Strings from a Particular Attribute" %}
This example demonstrates how to extract the `first_name` attribute from each `user` object within the `CTX.users` list. The list comprehension iterates over `CTX.users` and retrieves the `first_name` for each entry.

**Jinja:**

```django
{{
  [
    user.first_name 
    for user in CTX.users
  ]
}}
```

**Explanation:**

1. `for user in CTX.users`: Iterates over each `user` object in the list `CTX.users`.
2. `user. First_name`: Retrieves the `first_name` attribute of the current `user` object.
{% endtab %}

{% tab title="Filter a List by the Value of a Specific Attribute" %}
In this example, the list comprehension filters `CTX.users` to return only the objects where the `first_name` attribute is "Luke."

**Jinja:**

```django
{{
  [
    user 
    for user in CTX.users
    if user.first_name == "Luke"
  ]
}}
```

**Explanation:**

1. `for user in CTX.users`: Iterates over each `user` object in the list `CTX.users`.
2. `if user.first_name == "Luke"`: Applies a filter to only include users with the first name "Luke."
{% endtab %}
{% endtabs %}

***

## Date-Time Operations

Date-Time manipulations in Jinja can be easily achieved using context variables and built-in filters. This section provides examples to perform various date-time operations with JSON objects. Here are various examples demonstrating how to manipulate date-time values using Jinja filters in Rewst.

### Sample Input Data

```json
{ 
  "date_variable": "2023-09-11",
  "epoch_time": 1694473606,
  "time_variable": "2023-09-11T12:34:56Z"
}
```

***

### Example One: Convert Epoch Time to Datetime

You can convert epoch time to a datetime object using `convert_from_epoch`, then format it using `format_datetime`.

**Jinja:**

```django
{{ CTX.epoch_time | convert_from_epoch | format_datetime('%Y-%m-%d %H:%M:%S') }}
```

**Expected Output:**

```
2023-09-11 12:34:56
```

***

### Example Two: Perform Time Delta Operations

The `time delta` filter allows you to add or subtract time from a datetime variable. Here, `days=-30` subtracts 30 days.

```django
{{ CTX.date_variable | time_delta(days=-30) | format_datetime('%B %d, %Y') }}
```

**Output:**

`August 12, 2023`

### Example Three: Get Weekday Name

Convert the date to a weekday number (`%w`), which can then be used to fetch the corresponding day name from an array.

`{{ ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"][CTX.date_variable | format_datetime('%w') | int] }}`

**Output:**

`Monday`

***

### Example Four: Convert Datetime to Friendly Time

```django
{{ CTX.time_variable | format_datetime('%I:%M %p') }}
```

**Output:**

```
12:34 PM
```

### Example Five: Add Minutes to Time

**Jinja:**

```django
{{ CTX.time_variable | time_delta(minutes=15) | format_datetime('%H:%M:%S') }}
```

**Output:**

```
12:49:56
```

***

### **Additional Resources**

The `format_datetime` filter leverages format codes to specify the output string's structure. Here is a breakdown of commonly used format codes:

* `%Y`: 4-digit year (e.g., 2023)
* `%y`: 2-digit year (e.g., 23)
* `%m`: Month as a zero-padded decimal (e.g., 09 for September)
* `%B`: Full month name (e.g., September)
* `%b`: Abbreviated month name (e.g., Sep)
* `%d`: Day of the month as a zero-padded decimal (e.g., 11)
* `%A`: Full weekday name (e.g., Monday)
* `%a`: Abbreviated weekday name (e.g., Mon)
* `%w`: Weekday as a decimal number, where Sunday is 0 and Saturday is 6
* `%H`: Hour (24-hour clock) as a zero-padded decimal (e.g., 14)
* `%I`: Hour (12-hour clock) as a zero-padded decimal (e.g., 02)
* `%M`: Minute as a zero-padded decimal (e.g., 34)
* `%S`: Second as a zero-padded decimal (e.g., 56)
* `%p`: AM or PM
* `%Z`: Time zone name (e.g., UTC)

For more context and assistance with date-time formats, consult [this Python strftime cheatsheet](https://strftime.org/).

***
