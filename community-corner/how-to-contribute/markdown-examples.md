---
description: This page showcases the various Markdown options Gitbook has to offer
---

# Markdown Examples

Click `Edit on GitHub` on this page to see the below examples in their Markdown context for using in your own updates. Use the visuals below to see how each of these elements looks when being used.

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



<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td><em>use</em> markdown <strong>within</strong></td><td>Add Cards</td><td></td><td></td></tr><tr><td></td><td>With target links</td><td></td><td><a href="../../cluck-university/getting-started/">getting-started</a></td><td></td></tr><tr><td>And header images</td><td></td><td></td><td></td><td><a href="../../.gitbook/assets/task_transition.png">task_transition.png</a></td></tr></tbody></table>

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

{% content-ref url="../../" %}
[..](../../)
{% endcontent-ref %}

## **More to Come**

Stay tuned for further details on more ways to contribute. Thank you for your interest in enhancing our community knowledge base!
