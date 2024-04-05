---
description: >-
  Microsoft Exchange Online provides access to Microsoft Exchange Online
  resources (i.e. Mailboxes, Distribution Groups, etc.).
---

# Microsoft Exchange Online

{% hint style="warning" %}
**New: Microsoft Cloud Integration Bundle!** 🌟 We've combined our Microsoft integrations into a single, streamlined package for easier management and enhanced security. While individual integration guides are still here, we recommend checking out the new bundle for a simplified setup. Learn more on the [Microsoft Cloud Integration Bundle](../../cloud/microsoft-cloud-integration-bundle-documentation/) page.
{% endhint %}

## Setup

Rewst recommends installing Microsoft integrations in the following order:

1. Microsoft CSP
2. Microsoft Graph
3. Microsoft Exchange Online

Use the same account for authorization when installing these integrations:

1. **Navigate** to the integrations page in Rewst.
2. **Click** on the Microsoft Exchange Online integration.
   1. (Optional) **Enable** the Use CSP Delegated Admin Permissions toggle.
3. **Click** the Exchange Online OAuth Configuration Authorize/Re-Authorize button (using the same account as used for the Microsoft CSP integration).
4. **Follow** the authorization steps prompted by Microsoft.

## Actions

### Invoke Command

Invoke a command in Microsoft Exchange Online (EXO).

**Parameters**[**​**](http://localhost:3000/docs/integrations/Mail/ms-exchange-online#parameters)

<table><thead><tr><th>Name</th><th width="780.3333333333333">Type</th><th>Description</th></tr></thead><tbody><tr><td>Cmdlet Name</td><td><code>String</code></td><td><strong>Required</strong>. The name of the cmdlet to run.</td></tr><tr><td>Parameters</td><td><code>Array[[Parameter](#parameter)]</code></td><td><strong>Required</strong>. The parameters to pass to the cmdlet.</td></tr><tr><td>Remove Empty</td><td><code>boolean</code></td><td>If <code>true</code>, any null value will be stripped before sending the request. Default: <code>true</code>.</td></tr><tr><td>Anchor Mailbox</td><td><code>string</code></td><td>Optional. Some cmdlets require an anchor mailbox header to be specified. This can be overridden here if desired or for troubleshooting purposes.</td></tr></tbody></table>

