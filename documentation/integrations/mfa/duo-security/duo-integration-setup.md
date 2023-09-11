# Duo Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

### Overview

There are three different APIs provided by Duo and a key to initiate an individual user directory sync.

1. **Duo Admin API**: This API allows administrators to manage their Duo accounts programmatically. With the Duo Admin API, administrators can create, update, and delete user accounts, manage two-factor authentication settings, and generate reports on user activity, among other tasks.
2. **Duo Accounts API**: The Accounts API lets customers programmatically create, delete, and manage individual Duo customer accounts. New Duo accounts created using the Accounts API are subaccounts of the account where the Accounts API application exists, creating a "parent" and "child" account relationship. A Duo account can have multiple child accounts, but a child account may only have one parent and no child accounts of its own.
3. **Duo Auth API**: This API allows developers to add two-factor authentication to their applications using Duo's authentication service. With the Duo Auth API, developers can authenticate users using Duo's two-factor authentication, retrieve information about users and their devices, and perform administrative tasks related to authentication, among other tasks.
4. **Individual Account Directory Sync**: Initiate a sync to create, update, or mark for deletion the user specified by username against the directory specified by the `directory_key`.

### Setting up the API accounts

1. **Create** an Admin API by following the instructions [here](https://duo.com/docs/adminapi#first-steps).
   * We will need the **integration key**, **secret key**, and **API hostname**.
2. **Create** an Accounts API by following the instructions [here](https://duo.com/docs/accountsapi#first-steps).
   * We will need the **integration key**, **secret key**, and **API hostname**.
3. **Create** an Auth API by following the instructions [here](https://duo.com/docs/authapi).
   * We will need the **integration key**, **secret key**, and **API hostname**.

The `directory_key` for a directory can be found by navigating to Users → Directory Sync in the Duo Admin Panel, and then clicking on the configured directory.

### Configuring the Integration

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Go to** the _Configuration_ → _Integrations_ in the left sidebar.
3. **Complete** the form by filling in the **integration key**, **secret key**, and **API hostname** from steps 1-3 under `Setting up the API accounts`.
4. **Map** clients by doing one of the following:
   1. **Click** the Suggest Values.
   2. **Select** the company in the dropdown for **duo\_account\_id** property.
5. **Apply** the `directory_key` from step 4 under 'Setting up the API accounts' for each organization in the `duo_admin_api_directory_key` field.
