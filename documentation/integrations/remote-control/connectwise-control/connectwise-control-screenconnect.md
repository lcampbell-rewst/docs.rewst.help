# Connectwise Control (ScreenConnect)

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

## ConnectWise Control

Run commands on your ConnectWise Control agents and get logs from your sessions.

{% hint style="danger" %}
Heads up!

ConnectWise Control utilizes the `CustomProperty1` property - typically referenced as `Company` within the UI - to store the organization name.

If you are using this property for another purpose, you will need to update the `CustomProperty1` property to store the organization name.
{% endhint %}

## Setup

To allow Rewst access to your ConnectWise Control, you'll need to create a new user and allow it access to your sessions. To add a new user:

1. **Click** the "Admin" button on the left-hand side of the screen on your ConnectWise Control Instance.
2. **Click** "Security" in the sidebar.
3. **Click** "Show User Table".
4. **Click** "Add User".
5. **Fill out** the required data.
6. **Ensure** you select at minimum the _Control Host_ permission.
7. **Make a note** of the **username**, **password**, and **TOTP** secret you provide and input them below.
8. **Click** Save Configuration.

## Actions

### Get Session

Used to help you debug issues with your PowerShell scripts by providing logs associated with a specific connection ID.

**Parameters**[**​**](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#parameters)

| Name            | Type                                                                                                        | Description                                                              |
| --------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| `Session`       | [Session](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#session)             | **Required**. The session ID.                                            |
| `Connection ID` | `String`                                                                                                    | **Required**. The Connection ID provided by the "Invoke Command" Action. |
| `Session Group` | [Session Group](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#session-group) | **Required**. The session group.                                         |
| `Event Types`   | `Array[[Event Type](#event-types]`                                                                          | **Required**. The event types to filter the logs.                        |

### Invoke Command

Action to run a command template on an agent.

#### Invoke Command Parameters[​](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#invoke-command-parameters) <a href="#invoke-command-parameters" id="invoke-command-parameters"></a>

| Name            | Type                                                                                                        | Description                                                                                    |
| --------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `session_id`    | [Session](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#session)             | **Required**. The session ID.                                                                  |
| `session_group` | [Session Group](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#session-group) | **Required**. The session group.                                                               |
| `script`        | `Template`                                                                                                  | **Required**. The Powershell script template. You can create this under Automations → Scripts. |

## Reference Types

#### Session[​](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#session) <a href="#session" id="session"></a>

A reference to a "Session" within ConnectWise Control.

#### Session Group[​](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#session-group) <a href="#session-group" id="session-group"></a>

A reference to a session group within ConnectWise Control.

#### Event Types[​](http://localhost:3000/docs/integrations/Remote%20Control/connectwise-control#event-types) <a href="#event-types" id="event-types"></a>

| Event                      | Value |
| -------------------------- | ----- |
| Connected                  | 10    |
| Disconnected               | 11    |
| CreatedSession             | 20    |
| EndedSession               | 21    |
| InitiatedJoin              | 30    |
| InvitedGuest               | 31    |
| AddedNote                  | 32    |
| QueuedReinstall            | 40    |
| QueuedUninstall            | 41    |
| QueuedInvalidateLicense    | 42    |
| QueuedWake                 | 43    |
| QueuedCommand              | 44    |
| QueuedMessage              | 45    |
| QueuedGuestInfoUpdate      | 46    |
| QueuedTool                 | 47    |
| QueuedForceDisconnect      | 48    |
| ProcessedReinstall         | 50    |
| ProcessedUninstall         | 51    |
| ProcessedInvalidateLicense | 52    |
| ProcessedWake              | 53    |
| ProcessedCommand           | 54    |
| ProcessedMessage           | 55    |
| ProcessedGuestInfoUpdate   | 56    |
| ProcessedTool              | 57    |
| ProcessedForceDisconnect   | 58    |
| ModifiedName               | 60    |
| ModifiedIsPublic           | 61    |
| ModifiedCode               | 62    |
| ModifiedHost               | 63    |
| ModifiedCustomProperty     | 64    |
| RanCommand                 | 70    |
| SentMessage                | 71    |
| SentPrintJob               | 80    |
| ReceivedPrintJob           | 81    |
| CopiedText                 | 82    |
| CopiedFiles                | 83    |
| DraggedFiles               | 84    |
| RanFiles                   | 85    |
| SentFiles                  | 86    |
