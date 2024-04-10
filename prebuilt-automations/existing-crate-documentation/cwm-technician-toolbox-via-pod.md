# CWM: Technician Toolbox Via Pod

## Introduction

The Technical Toolbox crate gives your technicians access to Rewst automation within a Connect Wise Manage ticket. This document will walk you through the crate's various functions.&#x20;

## Prerequisites&#x20;

Before unpacking this crate, you must configure the pod to work with Rewst. Follow our guide: [Pod Configuration](../../documentation/integrations/psa/connectwise-manage/pod-configuration.md)

## Unpacking the Crate

**Log in** to app.rewst.io

**Navigate** to _Crates_ -> _Crate Marketplace_

**Search** for "_CWM: Technician Toolbox Via Pod"_

**Follow** the unpacking steps

{% hint style="info" %}
the crate will unpack with its triggers enabled. The trigger is set to work on any new tickets automatically. You will need to manually load the toolbox, as shown further in this document
{% endhint %}

## Using the Tool Box

On tickets with the pod running, you will see Five Main Categories; clicking the categories will open menu options for further tasks, as outlined below.&#x20;

<figure><img src="../../.gitbook/assets/Default View.png" alt=""><figcaption></figcaption></figure>

<details>

<summary>General</summary>

* Run AD Sync

</details>

<details>

<summary>User</summary>

* Reset Contact Password
* Send 2FA Request
* View User Information

</details>

<details>

<summary>Device</summary>

* View Uptime
* View Device Information
* Reboot Device
* Restart Print Spooler

</details>

<details>

<summary>Customer Portals</summary>

* M365
* Exchange
* Azure
* Azure AD
* Teams
* MEM (Intune)

</details>

<details>

<summary>Rewst Workflows</summary>

* Onboarding Form
* Offboarding Form
* Manage Group Membership
* Add User to Mailbox
* Manage MFA

</details>

## Re-running a Pod From a Ticket <a href="#re-running-a-pod-from-a-ticket" id="re-running-a-pod-from-a-ticket"></a>

Let's imagine you have a ticket that has had its associated pod workflow execution expire (or fail for one reason or another). If you attempt to view the pod in the ticket, you will see something along the lines of:

![](https://docs.rewst.help/\~gitbook/image?url=https:%2F%2Fgithub.com%2FRewstApp%2Fdocs.rewst.help%2Fassets%2F121902974%2F7ce5ce24-e338-41a2-99d2-9db4effd218a\&width=768\&dpr=4\&quality=100\&sign=4485813d2fca59f87d7ebaf75fbb0eb0e66b852ed70779a0fbe9c09235bd1edd)

To execute a new instance of the pod click on the 'Links' dropdown in the ticket and choose 'Rewst - Start Pod on this Ticket'

![](https://docs.rewst.help/\~gitbook/image?url=https:%2F%2Fgithub.com%2FRewstApp%2Fdocs.rewst.help%2Fassets%2F121902974%2F058d6794-48ba-4f7d-b5ba-d15b2f295b87\&width=768\&dpr=4\&quality=100\&sign=fdbd48a9a76af19e3a927358ed585e741ad293c8c3d07638f5d8a5f7864b51dc)

After using this button, a web page will open and close. This will send a request to the Live Link trigger and start a new execution for that ticket. Allow some time to pass before the ticket updates. You should see the pod populate once the execution has gone through.
