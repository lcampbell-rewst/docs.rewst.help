---
description: >-
  Practice writing list comprehension, using Jinja, to create a new list from
  existing list data
---

# Jinja List Comprehension

## Module Overview

:bulb: List comprehension (a special enhancement to "Rewst-flavored Jinja"!) allows you to create a new list from an existing one in a simplified way, without needing to end the code with `{% endfor %}`. It consists of three parts:

1. Output – What do you want in your new list?
2. For Loop – How do you loop through data in the original list?
3. Condition (Optional) – Do you need to filter items to include in your new list?

Here's the basic structure:&#x20;

`{{` \
`[ output for output`\
`in CTX.list`\
`if condition ]}}`

### Video (_3:16 Minutes)_

{% embed url="https://youtu.be/bvCXCyCl5rE?si=X0djxKF7Jduux1nL" %}

<details>

<summary>Additional Tips</summary>

* Use dot notation in the output to specify parts of each item.
* The condition (typically, an "if" statement) is optional and filters based on criteria like "if the color is not red."
* If you want to turn the list into a string, apply the "join" filter. You'll find an example of this in the "Lunch Menu" exercises for this lesson.

For a few examples, refer to the Jinja List Comprehension Examples module.

</details>

### Action Items

Practice the list comprehension exercises included in the "Lunch Menu" data set: [#lesson-resources](./#lesson-resources "mention")



## Navigation

<table data-card-size="large" data-column-title-hidden data-view="cards" data-full-width="false"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center">Go to the previous module: </td><td align="center"><a data-mention href="basic-jinja-syntax-and-filters.md">basic-jinja-syntax-and-filters.md</a></td><td></td></tr><tr><td align="center">Go to the next module:</td><td align="center"><a data-mention href="jinja-list-comprehension-examples-them-apples.md">jinja-list-comprehension-examples-them-apples.md</a></td><td></td></tr></tbody></table>
