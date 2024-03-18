# Managing Groups: Microsoft Graph vs. Exchange Online

## Introduction

Let's talk about how to manage groups efficiently using Microsoft Graph and Microsoft Exchange Online. Understanding the type of group is crucial, as it dictates the API we should use.&#x20;

{% hint style="info" %}
Our documentation comes directly from Microsoft. If you need more info, we recommend visiting [this Microsoft reference page](https://learn.microsoft.com/en-us/graph/api/resources/groups-overview).
{% endhint %}

## Group Types

Here's a breakdown of the group types and their corresponding management methods:

1. #### Dynamic Membership Groups:
   * Dynamic membership groups are identified by the presence of "Dynamic membership" in the group type property. These groups cannot be directly modified through APIs.
2. #### Unified Groups:
   * Unified groups are managed using Microsoft Graph API. They are groups where "unified" is present in the group types property or when mail-enabled is set to false.
3. #### Security Groups:
   * Security groups can be managed using Exchange Online if mail-enabled is set to true. If mail-enabled is false, they are managed by Microsoft Graph API.
4. #### Distribution Groups:
   * Distribution groups are also managed using Exchange Online.

### Conclusion

By understanding the nuances of different group types and mapping them appropriately, you can efficiently handle group operations within your applications.&#x20;

***

## Additional Resources

<table data-card-size="large" data-view="cards"><thead><tr><th align="center"></th><th align="center"></th><th data-hidden data-type="content-ref"></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td align="center"><mark style="color:blue;"><strong>LIVE: Rewst 105</strong></mark></td><td align="center">Improve Group Management to Support Exchange</td><td><a href="https://calendly.com/cluck-u/rewst-105">https://calendly.com/cluck-u/rewst-105</a></td><td><a href="https://calendly.com/cluck-u/rewst-105">https://calendly.com/cluck-u/rewst-105</a></td></tr><tr><td align="center"><a href="../../../cluck-university/rewst-foundations-10x/105-improve-group-management-to-support-exchange.md"><strong>Rewst 105</strong></a></td><td align="center">Recording + Documentation</td><td></td><td></td></tr></tbody></table>
