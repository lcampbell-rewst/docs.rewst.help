# Connectwise Control

### ConnectWise Control

Run commands on your ConnectWise Control agents and get logs from your sessions.

{% hint style="danger" %}
**Heads up!**

ConnectWise Control utilizes the `CustomProperty1` property - typically referenced as `Company` within the UI - to store the organization name.

If you are using this property for another purpose, you will need to update the `CustomProperty1` property to store the organization name.
{% endhint %}

### Setup

To allow Rewst access to your ConnectWise Control, you'll need to create a new user and allow it access to your sessions. To add a new user:

1. **Click** the "Admin" button on the left hand side of the screen on your ConnectWise Control Instance.
2. **Click** "Security" in the sidebar.
3. **Click** "Show User Table".
4. **Click** "Add User".
5. **Fill-out** the required data.
6. **Ensure** you select at minimum the _Control Host_ permission.
7. **Make a note** of the **username**, **password**, and **TOTP** secret you provide and input them below.
8. **Click** "Save Configuration".

### Actions

<details>

<summary>Get Session</summary>

Used to help you debug issues with your PowerShell scripts by providing logs associated with a specific connection ID.

**Parameters**

</details>

<details>

<summary>Invoke Command</summary>

Action to run a command template on an agent.

**Invoke Command Parameters**

**Reference Types**

**Session**

A reference to a "Session" within ConnectWise Control.

**Session Group**

A reference to a session group within ConnectWise Control.

**Event Types**

\\

</details>
