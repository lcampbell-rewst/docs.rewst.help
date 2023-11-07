---
description: >-
  Welcome to the Community Corner! This is designed to be a collaborative space
  where members can share insights, tips, and best practices.
---

# How to Contribute

## **Introduction**

Rewst's Community Corner aims to foster collaboration among users of our platform. Contributions help improve our documentation, sharing knowledge and best practices. This space will evolve, and eligibility criteria for broader contributions are under consideration.

## **Quick-Fix Contributions**

1. **Edit on GitHub**: Locate the "Edit on GitHub" button within the three dots at the top right of the documentation page you wish to edit.
2. **Find & Edit File**: Find the corresponding Markdown file and edit it, adhering to the pages formatting structure.
3. **Submit Pull Request**: After editing, submit a pull request with a detailed description of your changes.
4. **Review**: Our team will review the pull request. Upon approval, it will be merged into the live documentation.

***

## **Future Contributions: Eligibility & Criteria**

Eligibility criteria for more significant contributions that go beyond basic page edits and fixes are currently under consideration and will include requirements of completion of relevant Cluck University training modules.

Some of the things that should be considered with any updates include:

* **Relevance**: Contributions should focus on automation, good code hygiene, and effective use of the Rewst platform.
* **Clarity**: Aim for clear, concise writing. Avoid jargon and overly technical terms.
* **Respect**: Maintain a respectful and collaborative atmosphere.
* **Formatting**: Use Markdown for textual elements to ensure readability and consistency.
* **Objectivity**: Base contributions on verifiable information and maintain a neutral tone.

***

## **Markdown Examples**

***

## This is an H1 Heading

### This is an H2 Heading

#### This is an H3 Heading

This is a Paragraph Block

* This is
* an unordered list

1. This is
2. an ordered list

* [x] This is a task list
* [x] you can check items
* [ ] or leave them unchecked

Dividers can be placed like this:

***

Hint blocks can be setup with a few different options:

{% hint style="info" %}
This is a blue "Info" hint.
{% endhint %}

{% hint style="warning" %}
This is an orange "Warning" hint.
{% endhint %}

{% hint style="danger" %}
This is a red "Danger" hint.
{% endhint %}

{% hint style="success" %}
This is a green "Success" hint.
{% endhint %}

```django
you can insert a code block
with different formatting
```

> You can make quoted text like this

<figure><img src="https://images.unsplash.com/photo-1612170153139-6f881ff067e0?crop=entropy&#x26;cs=srgb&#x26;fm=jpg&#x26;ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwzfHxjaGlja2VufGVufDB8fHx8MTY5OTM3NDYyNnww&#x26;ixlib=rb-4.0.3&#x26;q=85" alt=""><figcaption><p>You can attach pictures and contextual tips like this</p></figcaption></figure>

{% embed url="https://docs.rewst.help" %}
Embed URLs
{% endembed %}

| Make Tables | With Columns |
| ----------- | ------------ |
| And         | Add          |
| Relevant    | Rows         |



<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td><em>use</em> markdown <strong>within</strong></td><td>Add Cards</td><td></td><td></td></tr><tr><td></td><td>With target links</td><td></td><td><a href="../cluck-university/getting-started/">getting-started</a></td><td></td></tr><tr><td>And header images</td><td></td><td></td><td></td><td><a href="../.gitbook/assets/task_transition.png">task_transition.png</a></td></tr></tbody></table>

{% tabs %}
{% tab title="First Tab" %}
Tabs are a good option
{% endtab %}

{% tab title="Second Tab" %}
For organizing content as well
{% endtab %}
{% endtabs %}

<details>

<summary>Expandable components</summary>

Allow you to collapse content within the component

You can add images, code block, and lists

</details>

Adding an API Method:

{% swagger method="get" path="" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

Linking to another page:

{% content-ref url="../" %}
[..](../)
{% endcontent-ref %}

## **More to Come**

Stay tuned for further details on more ways to contribute. Thank you for your interest in enhancing our community knowledge base!
