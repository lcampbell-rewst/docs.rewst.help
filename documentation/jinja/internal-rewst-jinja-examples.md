# Internal Rewst Jinja Examples

<details>

<summary>Shortcuts</summary>

• Press "F1" within the editor to see menu and shortcut options

• Press "Ctrl + Space" to get the initial root options

</details>

<details>

<summary>General Help</summary>

• Add "|" to access Jinja filters. Reference: [https://jinja.palletsprojects.com/en/3.0.x/templates/#list-of-builtin-filters](https://jinja.palletsprojects.com/en/3.0.x/templates/#list-of-builtin-filters) usage: "\{{ ORG.ATTRIBUTES.id|default('test default string') \}}"

</details>

<details>

<summary>Context Variables</summary>

Description: Contains workflow context variables, i.e. inputs provided by the Trigger, "Workflow Variables" configured during Crate installation, etc.

</details>

<details>

<summary>ORG Variables</summary>

Description: Data and functions specific to the Organization the workflow is running for

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

</details>

<details>

<summary>Tasks</summary>

**TASKS:**

Description: Reference previous tasks by name. Note: spaces must be replaced by underscores (\_), i.e. the "Send Message" task is reference with TASKS.Send\_Message

Usage: `{{ TASKS.list_tickets.result.result[0].id }}`

**TASKS\_RESULT\_DATA:**

Description: Reference previous tasks by name. Shortcut for \{{ TASKS.task\_name.result.result \}}

Note: spaces must be replaced by underscores (\_), i.e. the "Send Message" task is reference with TASK\_RESULT\_DATA.Send\_Message

**Things to keep in mind:**

As a general rule of thumb you will always need to use `.result.result` when referencing a task - with the exception of if that task is a "with items" and it becomes `.collected_results`

These should, for the most part, all autocomplete when you do the dot.

</details>

<details>

<summary>Utils</summary>

**UTILS.NOW:**

Description: now(timezone="UTC", dt\_format="timestamp") Default behavior returns the current UTC timestamp as an integer. The optional dt\_format argument accepts a format string, see [https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes)

Usage: `["{{ UTILS.now() }}", "{{ UTILS.now('EST', '%d-%m-%Y %H:%M:%S') }}"]`

**UTILS.uuid4:**

Description: Default behavior returns a new UUID

Usage: `["{{ UTILS.uuid4 }}"]`

</details>

<details>

<summary>Date Time</summary>

Current Time Formatted

data-tag="now" data-0='utc' data-1='%Y-%m-%dT%H:%M:%SZ'

Two Days Ago

data-0='utc' data-1='days=2' data-2='2' data-3=', '| format_datetime` from a datetime object to a specified string format

Code: `It was a {{ ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday"]["2022-07-04T11:38:00" | format_datetime("%w") | int] }}`

`| load_datetime` from a datetime object to a specified string format

Code: `{{ "06-09-2022" | load_datetime("%m-%d-%Y") }}`

`| time_delta` to add/subtract units from a datetime object

`{{ "06-09-2022" | load_datetime("%m-%d-%Y") | time_delta(days=-30) | format_datetime("%B %d, %Y") }}`

[Help with Date Formats](https://strftime.org/)

</details>
