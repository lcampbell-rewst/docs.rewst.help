---
description: >-
  Microsoft Exchange Online provides access to Microsoft Exchange Online
  resources (i.e. Mailboxes, Distribution Groups, etc.).
---

# Microsoft Exchange Online

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

| Name           | Type                             | Description                                                                                                                                      |
| -------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Cmdlet Name    | `String`                         | **Required**. The name of the cmdlet to run.                                                                                                     |
| Parameters     | `Array[[Parameter](#parameter)]` | **Required**. The parameters to pass to the cmdlet.                                                                                              |
| Remove Empty   | `boolean`                        | If `true`, any null value will be stripped before sending the request. Default: `true`.                                                          |
| Anchor Mailbox | `string`                         | Optional. Some cmdlets require an anchor mailbox header to be specified. This can be overridden here if desired or for troubleshooting purposes. |
