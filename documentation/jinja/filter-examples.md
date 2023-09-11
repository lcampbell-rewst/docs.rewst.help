# Filter Examples

### General Filters

`{{ CTX.firstname | capitalize }}`

Result: Capitalises the first character of the input variable. If firstname is "john", it'll become "John"

`{{ CTX.firstname | lower }}`

Result: Lowers the entire variable. If firstname is "jEnnIfer", it'll become "jennifer"

`{{ CTX.firstname | upper }}`

Result: Capitalises the entire variable. If firstname is "jeremy", it'll become "JEREMY"

### Iterating through a list

`{{ [users.userPrincipalName for users in TASKS.task_name.result.result ]}}`

Result: This will return all the users property "userPrincipalName"

#### Iterating through a list and finding a specific value

{% code overflow="wrap" %}
```django
{{ [users.userPrincipalName for users in TASKS.task_name.result.result if users.displayName == "Test Name"]}}
```
{% endcode %}

Result: This will return the userPrincipalName of the user(s) that has a display name of "Test Name"

{% code overflow="wrap" %}
```django
{{ [{"group_name": groups.displayName, "group_id": groups.id} for groups in TASKS.task_name.result.result if (not groups.dynamicMembership)"]}}
```
{% endcode %}

Result: This will return an object with the specified keys (group\_name and group\_id) and the specified property. It will only show groups that do not have a "dynamicMembership" property. This means that it will remove all dynamic groups from the list.

{% code overflow="wrap" %}
```django
{{ [{"group_name": groups.displayName, "group_id": groups.id} for groups in TASKS.task_name.result.result if (not groups.dynamicMembership) and (groups.displayName == "Testing Group Name"]}}
```
{% endcode %}

Result: This done the same as the above, except it has two conditions - adding that it'll only return groups with a display name of "Testing Group Name"
