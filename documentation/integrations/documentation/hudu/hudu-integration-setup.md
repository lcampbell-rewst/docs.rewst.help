# Hudu Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

### Overview

This document outlines the requirements and setup for the Hudu integration.

### Setting up the API account

Before configuring the Rewst integration you must generate an API user.

1. **Log in** to your Hudu instance.
2. **Copy** your instance hostname (ex: yourinstance.huducloud.com) and enter it below.
3. **Click** the Gear icon labeled Admin In the upper-left corner.
4. **Select** API at the bottom of the page.
5. **Create** a new key In the left-hand sidebar by entering the following:
   * Name: Rewst
   * Allowed IP Addresses: 3.139.170.31
   * Password Access: Checked
   * Can Perform Destructive Actions?: Checked
6. **Click** "Create New Key".
7. **Log in** to the [Rewst platform](https://app.rewst.io).
8. **Click** on the _"Integrations"_ menu on the left sidebar.
9. **Click** **on** or search for _"Hudu Documentation"_.
10. **Copy** the API Key from the top of the page and enter it below.
11. **Click** Save.

Rewst will perform a quick validation of the information.

Beneath that integration authentication section you will see the following options:

1. **Suggest Values:** This option will attempt to generate mappings between Rewst organizations and child organization in this integration.
2. **Refresh Options:** This will re-read the potential mapping options - both organizations and companies in IT Glue.
3. **Save Mappings:** This will apply mapping configuration changes.
