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
Context Variables are specific to the currently executing workflow. They include variables like [inputs ](../workflows/data-input-and-output.md#workflow-input)from the [workflow's trigger](../triggers/intro-to-triggers.md), any defined [Data Aliases](../workflows/configuring-your-workflow-tasks/navigating-between-tasks-with-transitions.md#diving-into-data-aliases), and results from tasks that have been executed.

* **Usage**: `{{ CTX.variable_name }}`
* **Additional Note**: Task results can be accessed once the task is complete. If attempted earlier, the variable will be `undefined`.
{% endtab %}

{% tab title="ORG" %}
Variables prefixed with `ORG` are related to data and functions specific to the Organization the workflow is running for. Below are the options you can call with the ORG prefix&#x20;

* **ORG.HAS\_TAG**
  * **Description**: Checks if the Organization associated with the running workflow has a specific tag.
  * **Usage**: `{{ ORG.HAS_TAG.Advanced_Security }}`
  * **Note**: Replace spaces in tag names with underscores (`_`).
* **ORG.VARIABLES**
  * **Description**: Custom variables associated with the Organization.
  * **Usage**: `{{ ORG.VARIABLES.variable_name }}`
* **ORG.MAPPING**
  * **Description**: A mapping table that correlates Organization identifiers in the current system with those in external systems.
  * **Usage**: `{{ ORG.MAPPING.ms_tenant_id }}`
* **ORG.INTEGRATIONS**
  * **Description**: Access integration-specific data and functionality.
  * **Usage**: `{{ ORG.INTEGRATIONS.microsoft_graph }}`
* **ORG.ATTRIBUTES**
  * **Description**: Houses attributes like `id` and `managing_org_id` of the organization.
  * **Usage**: `{{ ORG.ATTRIBUTES.id }}`
{% endtab %}

{% tab title="TASKS" %}
`TASKS` variables reference previous tasks by name.&#x20;

* **Usage Example**: `{{ TASKS.list_tickets.result.result[0].id }}`
  * **Note**: Replace spaces in task names with underscores (`_`).
* **TASKS\_RESULT\_DATA**
  * **Description**: Shortcut to reference task result data, equivalent to `{{ TASKS.task_name.result.result }}`.
  * **Usage**: `{{ TASKS_RESULT_DATA.Send_Message }}`
  * **Special Cases**: For 'with items' tasks, use `.collected_results` instead of `.result.result`.
{% endtab %}

{% tab title="UTILS" %}
* **UTILS.NOW**
  * **Description**: Returns the current time based on specified timezone and format. By default, returns the current UTC time as an integer.
  * **Usage**: `{{ UTILS.now() }}` or `{{ UTILS.now('EST', '%d-%m-%Y %H:%M:%S') }}`
  * **Format String**: Consult [Python's strftime format codes](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes) for custom date-time formatting.
* **UTILS.uuid4**
  * **Description**: Generates a new UUID (Universally Unique Identifier).
  * **Usage**: `{{ UTILS.uuid4 }}`
{% endtab %}
{% endtabs %}

#### Things to Keep in Mind

* Variable and function names are case-sensitive.
* Autocompletion is generally available after typing the dot (`.`) following a variable root like `CTX`, `ORG`, etc.

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

***

### Examples

{% tabs %}
{% tab title="Convert Epoch Time to Datetime" %}
You can convert epoch time to a datetime object using `convert_from_epoch`, then format it using `format_datetime`.

**Input:**

```json
{ 
  "epoch_time": 1694473606
}
```

**Jinja:**

```django
{{ CTX.epoch_time|convert_from_epoch|format_datetime('%Y-%m-%d %H:%M:%S') }}
```

**Output:**

```
2023-09-11 12:34:56
```
{% endtab %}

{% tab title="Get Weekday Name" %}
Convert the date to a weekday number (`%w`), which can then be used to fetch the corresponding day name from an array.

**Input:**

```json
{ 
  "date_variable": "2023-09-11"
}
```

**Jinja:**

```django
{{ ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"]
[CTX.date_variable | format_datetime('%w') | int] }}
```

**Output:**

```
Monday
```
{% endtab %}

{% tab title="Add Minutes to Time" %}
The `time delta` filter allows you to add or subtract time from a datetime variable. Here, `minutes=15` adds 15 minutes, and format `'%H:%M:%S'` displays only the time as output.

**Input:**

```json
{ 
  "time_variable": "2023-09-11T12:34:56Z"
}
```

**Jinja:**

```django
{{ CTX.time_variable | time_delta(minutes=15) | format_datetime('%H:%M %p') }}
```

**Output:**

```
12:49 PM
```
{% endtab %}
{% endtabs %}

### **Additional Resources**

The `format_datetime` filter leverages format codes to specify the output string's structure. Here is a breakdown of commonly used format codes:

* `%Y`: 4-digit year (e.g., 2023)
* `%y`: 2-digit year (e.g., 23)
* `%m`: Month as a zero-padded decimal (e.g., 09 for September)
* `%B`: Full month name (e.g., September)
* `%d`: Day of the month as a zero-padded decimal (e.g., 11)
* `%A`: Full weekday name (e.g., Monday)
* `%w`: Weekday as a decimal number, where Sunday is 0 and Saturday is 6
* `%H`: Hour (24-hour clock) as a zero-padded decimal (e.g., 14)
* `%I`: Hour (12-hour clock) as a zero-padded decimal (e.g., 02)
* `%M`: Minute as a zero-padded decimal (e.g., 34)
* `%S`: Second as a zero-padded decimal (e.g., 56)
* `%p`: AM or PM

For more context and assistance with date-time formats, consult [this Python strftime cheatsheet](https://strftime.org/).

***
