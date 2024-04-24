# NinjaOne Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

## Overview

Integrating Rewst with NinjaRMM provides users with a powerful combination of documentation and remote monitoring and management capabilities. By bringing these two platforms together, Rewst users can streamline their operations and enhance efficiency. With the integration, users can seamlessly access and manage NinjaRMM within Rewst, enabling them to monitor and troubleshoot devices, deploy software, and perform remote tasks more effectively. This integration empowers users to centralize their IT documentation and RMM workflows, ensuring a comprehensive and streamlined approach to IT management within the Rewst platform.

## Setup

### Complete Setup in Ninja

First, go to Ninja and complete the following:

1. **Go to** Administration -> Library -> Automation.
2. **Click** + Add -> New Script on the right.
3. **Add** the following script:
   * Name: Rewst (Windows) &#x20;
   * Language: Powershell
   * OS: Windows
   * Architecture: All

```powershell
Param(
    [Parameter(Mandatory=$true)]
    [string]$script_content_path,
    [Parameter(Mandatory=$true)]
    [string]$results_postdata_path
)

$rewst_base_url = "https://engine.rewst.io/webhooks/custom/action"
$script_content_url = "$rewst_base_url/$script_content_path"
$post_url = "$rewst_base_url/$results_postdata_path"



# Download Script Content from Rewst

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$wc = New-Object System.Net.WebClient
$wc.Encoding = [System.Text.Encoding]::UTF8
$commands = ($wc.DownloadString($script_content_url))

# Execute Script Content

iex $commands
```

### Complete Setup in Rewst

Follow the below steps to configure a new integration in Rewst:

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Go to** _Configuration_ → _Integrations_ menu on the left sidebar.
3. **Click** or search for "Ninja".
4. **Select** your Region.
5. **Authorize** OAuth into Ninja via Microsoft.
   * You should see your customer show up at the bottom.
6. **Click** Save.

## Actions

### Devices

#### List Custom Fields for Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-custom-fields-for-device) <a href="#list-custom-fields-for-device" id="list-custom-fields-for-device"></a>

Returns a list of applicable management options[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-applicable-management-options)

GET `/device/{id}/custom-fields`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### Update Field Values[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-field-values) <a href="#update-field-values" id="update-field-values"></a>

Update the device's custom field values[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-devices-custom-field-values)

PATCH `/device/{id}/custom-fields`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### Get Last Logged On User For Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-last-logged-on-user-for-device) <a href="#get-last-logged-on-user-for-device" id="get-last-logged-on-user-for-device"></a>

Returns username that was last to login to the device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-username-that-was-last-to-login-to-device)

GET `/device/{id}/last-logged-on-user`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### List OS Patches by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-os-patches-by-device) <a href="#list-os-patches-by-device" id="list-os-patches-by-device"></a>

Returns list of pending`/rejected/approved` OS patches for device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-pendingrejectedapproved-os-patches-for-device)

GET `/device/{id}/os-patches`

| Parameter | Type   | Required | Description                       |
| --------- | ------ | -------- | --------------------------------- |
| Device    | string | Yes      |                                   |
| Status    | string | No       | Return Activities With Status(es) |
| Type      | string | No       | Update Type Filter                |
| Severity  | string | No       |                                   |

#### Get OS Update Installation Report By Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-os-update-installation-report-by-device) <a href="#get-os-update-installation-report-by-device" id="get-os-update-installation-report-by-device"></a>

Returns patch installation history records (successful and failed) for the device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-patch-installation-history-records-successful-and-failed-for-device)

GET `/device/{id}/os-patch-installs`

| Parameter        | Type   | Required | Description                                     |
| ---------------- | ------ | -------- | ----------------------------------------------- |
| Device           | string | Yes      |                                                 |
| Status           | string | No       | Return Activities With Status(es)               |
| Installed Before | string | No       | Include Patches Installed Before Specified Date |
| Installed After  | string | No       | Include Patches Installed After Specified Date  |

#### Get Software Update History by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-software-update-history-by-device) <a href="#get-software-update-history-by-device" id="get-software-update-history-by-device"></a>

Returns 3rd party software patch installation history records for a device (successful and failed)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-3rd-party-software-patch-installation-history-records-for-device-successful-and-failed)

GET `/device/{id}/software-patch-installs`

| Parameter        | Type   | Required | Description                                     |
| ---------------- | ------ | -------- | ----------------------------------------------- |
| Device           | string | Yes      |                                                 |
| Type             | string | No       | Update Type Filter                              |
| Impact           | string | No       | Update Impact Filter                            |
| Status           | string | No       | Return Activities With Status(es)               |
| Product          | string | No       |                                                 |
| Installed Before | string | No       | Include Patches Installed Before Specified Date |
| Installed After  | string | No       | Include Patches Installed After Specified Date  |

#### List Disk Drives by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-disk-drives-by-device) <a href="#list-disk-drives-by-device" id="list-disk-drives-by-device"></a>

Returns device disks' details[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-device-disks-details)

GET `/device/{id}/disks`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### List Storage Volumes by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-storage-volumes-by-device) <a href="#list-storage-volumes-by-device" id="list-storage-volumes-by-device"></a>

Returns device volumes' details[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-device-volumes-details)

GET `/device/{id}/volumes`

| Parameter | Type   | Required | Description                                                |
| --------- | ------ | -------- | ---------------------------------------------------------- |
| Device    | string | Yes      |                                                            |
| Include   | string | No       | Additional Information To Include (Bl - Bit Locker Status) |

#### List Processors by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-processors-by-device) <a href="#list-processors-by-device" id="list-processors-by-device"></a>

Returns list of device Processor details[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-device-processor-details)

GET `/device/{id}/processors`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### List Installed Software by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-installed-software-by-device) <a href="#list-installed-software-by-device" id="list-installed-software-by-device"></a>

Returns list of software installed on a device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-software-installed-on-device)

GET `/device/{id}/software`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### Device Alerts (Triggered Conditions) by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#device-alerts-triggered-conditions-by-device) <a href="#device-alerts-triggered-conditions-by-device" id="device-alerts-triggered-conditions-by-device"></a>

Returns list of active alerts (triggered conditions) for device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-active-alerts-triggered-conditions-for-device)

GET `/device/{id}/alerts`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |
| Lang      | string | No       | Language    |

#### Device Currently Running (Active) Jobs by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#device-currently-running-active-jobs-by-device) <a href="#device-currently-running-active-jobs-by-device" id="device-currently-running-active-jobs-by-device"></a>

Returns currently running jobs for device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-currently-running-jobs-for-device)

GET `/device/{id}/jobs`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |
| Lang      | string | No       | Language    |

#### List Windows Services by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-windows-services-by-device) <a href="#list-windows-services-by-device" id="list-windows-services-by-device"></a>

Returns list of Windows Services for a device and their statuses[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-windows-services-for-a-device-and-their-statuses)

GET `/device/{id}/windows-services`

| Parameter    | Type   | Required | Description   |
| ------------ | ------ | -------- | ------------- |
| Device       | string | Yes      |               |
| Service Name | string | No       |               |
| State        | string | No       | Service State |

#### Get Device Details[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-device-details) <a href="#get-device-details" id="get-device-details"></a>

Returns device details[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-device-details)

GET `/device/{id}`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### Get Device Activities[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-device-activities) <a href="#get-device-activities" id="get-device-activities"></a>

Returns activity log for device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-activity-log-for-device)

GET `/device/{id}/activities`

| Parameter     | Type   | Required | Description                                                          |
| ------------- | ------ | -------- | -------------------------------------------------------------------- |
| Device        | string | Yes      |                                                                      |
| Older Than    | string | No       | Return Activities Recorded That Are Newer Than Specified Activity ID |
| Newer Than    | string | No       | Return Activities Recorded That Are Older Than Specified Activity ID |
| Activity Type | string | No       | Return Activities Of Type                                            |
| Status        | string | No       | Return Activities With Status(es)                                    |
| Series Uid    | string | No       | Return Activities Related To Alert (Series)                          |
| Lang          | string | No       | Language                                                             |

#### Pending, Failed And Rejected Software Patches For Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#pending-failed-and-rejected-software-patches-for-device) <a href="#pending-failed-and-rejected-software-patches-for-device" id="pending-failed-and-rejected-software-patches-for-device"></a>

Returns list of 3rd party Software patches for a device (for which there were no installation attempts)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-3rd-party-software-patches-for-a-device-for-which-there-were-no-installation-attempts)

GET `/device/{id}/software-patches`

| Parameter | Type   | Required | Description                       |
| --------- | ------ | -------- | --------------------------------- |
| Device    | string | Yes      |                                   |
| Status    | string | No       | Return Activities With Status(es) |
| Product   | string | No       |                                   |
| Type      | string | No       | Update Type Filter                |
| Impact    | string | No       | Update Impact Filter              |

### Groups

#### List Group Members' Devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-group-members-devices) <a href="#list-group-members-devices" id="list-group-members-devices"></a>

Returns list of device identifiers that match group criteria[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-device-identifiers-that-match-group-criteria)

GET `/group/{id}/device-ids`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Group     | string | Yes      |             |
| Refresh   | string | No       |             |

### Management

#### Reset Alert`/Condition` And Provide Custom Data For Activity[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#reset-alertcondition-and-provide-custom-data-for-activity) <a href="#reset-alertcondition-and-provide-custom-data-for-activity" id="reset-alertcondition-and-provide-custom-data-for-activity"></a>

`/alert/{uid}/reset`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Alert     | string | Yes      |             |

#### Update API Webhook Configuration[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-api-webhook-configuration) <a href="#update-api-webhook-configuration" id="update-api-webhook-configuration"></a>

Creates or updates Webhook configuration for the current application`/client`[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#creates-or-updates-webhook-configuration-for-current-applicationclient)

PUT `/webhook`

| Parameter  | Type   | Required | Description                                        |
| ---------- | ------ | -------- | -------------------------------------------------- |
| URL        | string | No       | Callback (Web Hook) URL For Activity Notifications |
| Activities | object | No       | Activity Filter                                    |
| Expand     | string | No       | Which References To Expand In Payloads             |
| Headers    | array  | No       |                                                    |

#### Remove Webhook API Channel[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#remove-webhook-api-channel) <a href="#remove-webhook-api-channel" id="remove-webhook-api-channel"></a>

Creates or updates PSA configuration based on client[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#creates-or-updates-psa-configuration-based-on-client)

DELETE `/webhook`

#### Approve`/Reject` Devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#approvereject-devices) <a href="#approvereject-devices" id="approvereject-devices"></a>

Approve or reject devices that are waiting for approval[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#approve-or-reject-devices-that-are-waiting-for-approval)

`/devices/approval/{mode}`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Mode      | string | Yes      |             |
| Devices   | array  | No       |             |

#### Reset Alert`/Condition`[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#reset-alertcondition) <a href="#reset-alertcondition" id="reset-alertcondition"></a>

DELETE `/alert/{uid}`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Alert     | string | Yes      |             |

#### Modify Windows Service Configuration[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#modify-windows-service-configuration) <a href="#modify-windows-service-configuration" id="modify-windows-service-configuration"></a>

Configures Windows Service startup settings[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#configures-windows-service-startup-settings)

`/device/{id}/windows-service/{serviceId}/configure`

| Parameter  | Type   | Required | Description        |
| ---------- | ------ | -------- | ------------------ |
| Device     | string | Yes      |                    |
| Service ID | string | Yes      | Service Identifier |
| Start Type | string | No       | Start Type         |
| Username   | string | No       |                    |

#### Reboot Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#reboot-device) <a href="#reboot-device" id="reboot-device"></a>

Sends a command to restart the computer[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#sends-a-command-to-restart-the-computer)

`/device/{id}/reboot/{mode}`

| Parameter | Type   | Required | Description          |
| --------- | ------ | -------- | -------------------- |
| Device    | string | Yes      |                      |
| Mode      | string | Yes      | Reboot Mode          |
| Reason    | string | No       | Stated Reboot Reason |

#### List Scripting Options by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-scripting-options-by-device) <a href="#list-scripting-options-by-device" id="list-scripting-options-by-device"></a>

Returns scripting options (built-in actions, custom scripts) available for device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-scripting-options-built-in-actions-custom-scripts-available-for-device)

GET `/device/{id}/scripting/options`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |
| Lang      | string | No       | Language    |

#### Update Device Information[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-device-information) <a href="#update-device-information" id="update-device-information"></a>

Change device-friendly name, user data, etc[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#change-device-friendly-name-user-data-etc)

PATCH `/device/{id}`

| Parameter         | Type   | Required | Description                  |
| ----------------- | ------ | -------- | ---------------------------- |
| Device            | string | Yes      |                              |
| Display Name      | string | No       | Display Name (User Assigned) |
| Custom Attributes | string | No       | User Specified               |
| nodeRoleId        | string | No       |                              |
| Policy            | string | No       |                              |

#### Get Device Link[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-device-link) <a href="#get-device-link" id="get-device-link"></a>

Returns link to the device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-link-to-device)

GET `/device/{id}/dashboard-url`

| Parameter | Type    | Required | Description              |
| --------- | ------- | -------- | ------------------------ |
| Device    | string  | Yes      |                          |
| Redirect  | boolean | No       | Return Redirect Response |

#### Control Windows Service[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#control-windows-service) <a href="#control-windows-service" id="control-windows-service"></a>

Start`/Stop/Restart` Windows Service on a device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#startstoprestart-windows-service-on-a-device)

`/device/{id}/windows-service/{serviceId}/control`

| Parameter  | Type   | Required | Description        |
| ---------- | ------ | -------- | ------------------ |
| Device     | string | Yes      |                    |
| Service ID | string | Yes      | Service Identifier |
| Action     | string | No       | Action             |

#### Schedule Maintenance[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#schedule-maintenance) <a href="#schedule-maintenance" id="schedule-maintenance"></a>

Schedule maintenance window for device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#schedule-maintenance-window-for-device)

PUT `/device/{id}/maintenance`

| Parameter                | Type   | Required | Description                                                                                  |
| ------------------------ | ------ | -------- | -------------------------------------------------------------------------------------------- |
| Device                   | string | Yes      |                                                                                              |
| Disabled Features        | array  | No       | List Of Features That Will Be Disabled During Maintenance                                    |
| Maintenance Window Start | number | No       | Unix Timestamp, with milliseconds (i.e. 1666373777.891) - Defaults to now.                   |
| Maintenance Window End   | number | No       | Unix Timestamp, with milliseconds (i.e. 1666373777.891), at least 5 minutes after the start. |

#### Cancel Maintenance[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#cancel-maintenance) <a href="#cancel-maintenance" id="cancel-maintenance"></a>

Cancel pending or active maintenance for the device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#cancel-pending-or-active-maintenance-for-device)

DELETE `/device/{id}/maintenance`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Device    | string | Yes      |             |

#### Run Script Or Built In Action[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#run-script-or-built-in-action) <a href="#run-script-or-built-in-action" id="run-script-or-built-in-action"></a>

Run script or built-in action on a device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#run-script-or-built-in-action-on-a-device)

`/device/{id}/script/run`

| Parameter  | Type    | Required | Description                  |
| ---------- | ------- | -------- | ---------------------------- |
| ID         | integer | No       | Script Identifier            |
| Type       | string  | No       | Type                         |
| Uid        | string  | No       | Built In Action Identifier   |
| Parameters | string  | No       | Action`/Script` Parameters   |
| Run As     | string  | No       | Credential Role`/Identifier` |

#### Create Location For Organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#create-location-for-organization) <a href="#create-location-for-organization" id="create-location-for-organization"></a>

Creates new location for the organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#creates-new-location-for-organization)

`/organization/{id}/locations`

| Parameter         | Type   | Required | Description    |
| ----------------- | ------ | -------- | -------------- |
| Organization      | string | Yes      |                |
| Name              | string | No       | Location Name  |
| Address           | string | No       | Address        |
| Description       | string | No       | Description    |
| Custom Attributes | string | No       | User Specified |
| Tags              | string | No       | Tags           |
| Fields            | string | No       | Custom Fields  |

#### Update Organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-organization) <a href="#update-organization" id="update-organization"></a>

Change organization name, description and policy mappings[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#change-organization-name-description-and-policy-mappings)

PATCH `/organization/{id}`

| Parameter          | Type   | Required | Description              |
| ------------------ | ------ | -------- | ------------------------ |
| Organization       | string | Yes      |                          |
| Name               | string | No       | Organization Full Name   |
| Description        | string | No       | Organization Description |
| Custom Attributes  | string | No       | User Specified           |
| Node Approval Mode | string | No       | Device Approval Mode     |
| Tags               | string | No       | Tags                     |
| Fields             | string | No       | Custom Fields            |

#### Generate Installer[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#generate-installer) <a href="#generate-installer" id="generate-installer"></a>

Generates and returns URL for an installer for a specified organization`/location`[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#generates-and-returns-url-for-installer-for-specified-organizationlocation)

GET `/organization/{id}/location/{location_id}/installer/{installer_type}`

| Parameter      | Type    | Required | Description |
| -------------- | ------- | -------- | ----------- |
| Organization   | string  | Yes      |             |
| Location       | integer | Yes      |             |
| Installer Type | string  | Yes      |             |

#### Update Location[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-location) <a href="#update-location" id="update-location"></a>

Change location name, address, description, custom data[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#change-location-name-address-description-custom-data)

PATCH `/organization/{id}/locations/{locationId}`

| Parameter         | Type    | Required | Description    |
| ----------------- | ------- | -------- | -------------- |
| Organization      | string  | Yes      |                |
| Location ID       | integer | Yes      |                |
| Name              | string  | No       | Location Name  |
| Address           | string  | No       | Address        |
| Description       | string  | No       | Description    |
| Custom Attributes | string  | No       | User Specified |
| Tags              | string  | No       | Tags           |
| Fields            | string  | No       | Custom Fields  |

#### Change Organization Policy Mappings[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#change-organization-policy-mappings) <a href="#change-organization-policy-mappings" id="change-organization-policy-mappings"></a>

Update policy assignment for node role(s). Returns list of affected device IDs[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#update-policy-assignment-for-node-roles-returns-list-of-affected-device-ids)

PUT `/organization/{id}/policies`

| Parameter    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| Organization | string | Yes      |             |

### Organization

#### Create New Organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#create-new-organization) <a href="#create-new-organization" id="create-new-organization"></a>

Creates a new organization with an optional list of locations and policy mappings. Template organization ID can be specified to copy various settings[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#creates-new-organization-with-optional-list-of-locations-and-policy-mappings-template-organization-id-can-be-specified-to-copy-various-settings)

`/organizations`

| Parameter          | Type   | Required | Description                  |
| ------------------ | ------ | -------- | ---------------------------- |
| Organization       | string | No       |                              |
| Name               | string | No       | Organization Full Name       |
| Description        | string | No       | Organization Description     |
| Custom Attributes  | string | No       | User Specified               |
| Node Approval Mode | string | No       | Device Approval Mode         |
| Tags               | string | No       | Tags                         |
| Fields             | string | No       | Custom Fields                |
| Locations          | array  | No       | List Of Locations            |
| Policies           | array  | No       | Node Role Policy Assignments |

#### List Organization Locations[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-organization-locations) <a href="#list-organization-locations" id="list-organization-locations"></a>

Returns list of locations for organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-locations-for-organization)

GET `/organization/{id}/locations`

| Parameter    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| Organization | string | Yes      |             |

#### Get Organization Information[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-organization-information) <a href="#get-organization-information" id="get-organization-information"></a>

Returns organization details (policy mappings, locations)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-organization-details-policy-mappings-locations)

GET `/organization/{id}`

| Parameter    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| Organization | string | Yes      |             |

#### List Users for Organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-users-for-organization) <a href="#list-users-for-organization" id="list-users-for-organization"></a>

Returns list of end-users for organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-end-users-for-organization)

GET `/organization/{id}/end-users`

| Parameter    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| Organization | string | Yes      |             |

#### List Organization Documents[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-organization-documents) <a href="#list-organization-documents" id="list-organization-documents"></a>

Returns organization documents[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-organization-documents)

GET `/organization/{id}/documents`

| Parameter    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| Organization | string | Yes      |             |

#### List Organization Devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-organization-devices) <a href="#list-organization-devices" id="list-organization-devices"></a>

Returns list of devices for organization[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-devices-for-organization)

GET `/organization/{id}/devices`

| Parameter    | Type   | Required | Description |
| ------------ | ------ | -------- | ----------- |
| Organization | string | Yes      |             |

### Queries

#### List Uninstalled OS Patches[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-uninstalled-os-patches) <a href="#list-uninstalled-os-patches" id="list-uninstalled-os-patches"></a>

Returns list of OS patches for which there were no installation attempts[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-os-patches-for-which-there-were-no-installation-attempts)

GET `/queries/os-patches`

| Parameter        | Type   | Required | Description                       |
| ---------------- | ------ | -------- | --------------------------------- |
| Device Filter    | string | No       | Device Filter                     |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter       |
| Status           | string | No       | Return Activities With Status(es) |
| Type             | string | No       | Update Type Filter                |
| Severity         | string | No       | Update Severity Filter            |

#### List Pending, Failed And Rejected 3rd Party Software Patches[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-pending-failed-and-rejected-3rd-party-software-patches) <a href="#list-pending-failed-and-rejected-3rd-party-software-patches" id="list-pending-failed-and-rejected-3rd-party-software-patches"></a>

Returns list of 3rd party Software patches for which there were no installation attempts[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-3rd-party-software-patches-for-which-there-were-no-installation-attempts)

GET `/queries/software-patches`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |
| Status           | string | No       | Update Status Filter        |
| Product          | string | No       |                             |
| Type             | string | No       | Update Type Filter          |
| Impact           | string | No       | Update Impact Filter        |

#### List Software Update History[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-software-update-history) <a href="#list-software-update-history" id="list-software-update-history"></a>

Returns 3rd party software patch installation history records (successful and failed)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-3rd-party-software-patch-installation-history-records-successful-and-failed)

GET `/queries/software-patch-installs`

| Parameter        | Type   | Required | Description                                     |
| ---------------- | ------ | -------- | ----------------------------------------------- |
| Device Filter    | string | No       | Device Filter                                   |
| Type             | string | No       | Update Type Filter                              |
| Impact           | string | No       | Update Impact Filter                            |
| Status           | string | No       | Update Status Filter                            |
| Product          | string | No       |                                                 |
| Installed Before | string | No       | Include Patches Installed Before Specified Date |
| Installed After  | string | No       | Include Patches Installed After Specified Date  |

#### Last Logged On User Report[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#last-logged-on-user-report) <a href="#last-logged-on-user-report" id="last-logged-on-user-report"></a>

Returns usernames and logon times[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-usernames-and-logon-times)

GET `/queries/logged-on-users`

| Parameter     | Type   | Required | Description   |
| ------------- | ------ | -------- | ------------- |
| Device Filter | string | No       | Device Filter |

#### List Custom Fields with Details[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-custom-fields-with-details) <a href="#list-custom-fields-with-details" id="list-custom-fields-with-details"></a>

Returns Custom Fields report with additional information about each field[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-custom-fields-report-with-additional-information-about-each-field)

GET `/queries/custom-fields-detailed`

| Parameter     | Type   | Required | Description                                |
| ------------- | ------ | -------- | ------------------------------------------ |
| Device Filter | string | No       | Device Filter                              |
| Updated After | string | No       | Custom Fields Updated After Specified Date |
| Fields        | string | No       | Custom Fields                              |

#### List Health Status by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-health-status-by-device) <a href="#list-health-status-by-device" id="list-health-status-by-device"></a>

Returns list of device health summary records[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-device-health-summary-records)

GET `/queries/device-health`

| Parameter     | Type   | Required | Description          |
| ------------- | ------ | -------- | -------------------- |
| Device Filter | string | No       | Device Filter        |
| Health        | string | No       | Health Status Filter |

#### List Software Inventory[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-software-inventory) <a href="#list-software-inventory" id="list-software-inventory"></a>

Returns list software installed on devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-software-installed-on-devices)

GET `/queries/software`

| Parameter        | Type   | Required | Description                                     |
| ---------------- | ------ | -------- | ----------------------------------------------- |
| Device Filter    | string | No       | Device Filter                                   |
| Installed Before | string | No       | Include Patches Installed Before Specified Date |
| Installed After  | string | No       | Include Patches Installed After Specified Date  |

#### List OS Update Installations[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-os-update-installations) <a href="#list-os-update-installations" id="list-os-update-installations"></a>

Returns patch installation history records (successful and failed)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-patch-installation-history-records-successful-and-failed)

GET `/queries/os-patch-installs`

| Parameter        | Type   | Required | Description                                     |
| ---------------- | ------ | -------- | ----------------------------------------------- |
| Device Filter    | string | No       | Device Filter                                   |
| Status           | string | No       | Return Activities With Status(es)               |
| Installed Before | string | No       | Include Patches Installed Before Specified Date |
| Installed After  | string | No       | Include Patches Installed After Specified Date  |

#### List Antivirus Status by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-antivirus-status-by-device) <a href="#list-antivirus-status-by-device" id="list-antivirus-status-by-device"></a>

Returns list of statues of antivirus software installed on devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-statues-of-antivirus-software-installed-on-devices)

GET `/queries/antivirus-status`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |
| Product State    | string | No       | Product State Filter        |
| Product Name     | string | No       | Product Name Filter         |

#### List Raid Controllers[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-raid-controllers) <a href="#list-raid-controllers" id="list-raid-controllers"></a>

Returns list of RAID controllers[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-raid-controllers)

GET `/queries/raid-controllers`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Raid Drives[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-raid-drives) <a href="#list-raid-drives" id="list-raid-drives"></a>

Returns list of drives connected to RAID controllers[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-drives-connected-to-raid-controllers)

GET `/queries/raid-drives`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Windows Services[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-windows-services) <a href="#list-windows-services" id="list-windows-services"></a>

Returns list of Windows Services and their statuses[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-windows-services-and-their-statuses)

GET `/queries/windows-services`

| Parameter     | Type   | Required | Description   |
| ------------- | ------ | -------- | ------------- |
| Device Filter | string | No       | Device Filter |
| Name          | string | No       | Service Name  |
| State         | string | No       | Service State |

#### List Custom Fields[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-custom-fields) <a href="#list-custom-fields" id="list-custom-fields"></a>

Returns Custom Fields report[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-custom-fields-report)

GET `/queries/custom-fields`

| Parameter     | Type   | Required | Description                                |
| ------------- | ------ | -------- | ------------------------------------------ |
| Device Filter | string | No       | Device Filter                              |
| Updated After | string | No       | Custom Fields Updated After Specified Date |
| Fields        | string | No       | Custom Fields                              |

#### List Computer Systems[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-computer-systems) <a href="#list-computer-systems" id="list-computer-systems"></a>

Returns computer systems information for devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-computer-systems-information-for-devices)

GET `/queries/computer-systems`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Disk Drives[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-disk-drives) <a href="#list-disk-drives" id="list-disk-drives"></a>

Returns list of physical disks[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-physical-disks)

GET `/queries/disks`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Antivirus Threats[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-antivirus-threats) <a href="#list-antivirus-threats" id="list-antivirus-threats"></a>

Returns list of antivirus threats[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-antivirus-threats)

GET `/queries/antivirus-threats`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Operating Systems by Device[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-operating-systems-by-device) <a href="#list-operating-systems-by-device" id="list-operating-systems-by-device"></a>

Returns operating systems for devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-operating-systems-for-devices)

GET `/queries/operating-systems`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Processors[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-processors) <a href="#list-processors" id="list-processors"></a>

Returns list of processors[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-processors)

GET `/queries/processors`

| Parameter        | Type   | Required | Description                 |
| ---------------- | ------ | -------- | --------------------------- |
| Device Filter    | string | No       | Device Filter               |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter |

#### List Disk Volumes[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-disk-volumes) <a href="#list-disk-volumes" id="list-disk-volumes"></a>

Returns list of disk volumes[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-disk-volumes)

GET `/queries/volumes`

| Parameter        | Type   | Required | Description                                              |
| ---------------- | ------ | -------- | -------------------------------------------------------- |
| Device Filter    | string | No       | Device Filter                                            |
| Timestamp Filter | string | No       | Monitoring Timestamp Filter                              |
| Include          | string | No       | Additional Information To Include (Bl Bit Locker Status) |

### System

#### List Organizations[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-organizations) <a href="#list-organizations" id="list-organizations"></a>

Returns list of organizations (Brief mode)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-organizations-brief-mode)

GET `/organizations`

#### Get Attachment by ID[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-attachment-by-id) <a href="#get-attachment-by-id" id="get-attachment-by-id"></a>

Returns attachment (image, document)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-attachment-image-document)

GET `/attachment/{id}`

| Parameter | Type   | Required | Description           |
| --------- | ------ | -------- | --------------------- |
| ID        | string | Yes      | Attachment Identifier |

#### List All Device Custom Fields[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-all-device-custom-fields) <a href="#list-all-device-custom-fields" id="list-all-device-custom-fields"></a>

Returns list of all custom fields[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-all-custom-fields)

GET `/device-custom-fields`

#### List Active Alerts (Triggered Conditions)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-active-alerts-triggered-conditions) <a href="#list-active-alerts-triggered-conditions" id="list-active-alerts-triggered-conditions"></a>

Returns list of active alerts`/triggered` conditions[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-active-alertstriggered-conditions)

GET `/alerts`

| Parameter     | Type   | Required | Description   |
| ------------- | ------ | -------- | ------------- |
| Source Type   | string | No       |               |
| Device Filter | string | No       | Device Filter |
| Lang          | string | No       | Language      |

#### List Organizations with Locations and Policies[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-organizations-with-locations-and-policies) <a href="#list-organizations-with-locations-and-policies" id="list-organizations-with-locations-and-policies"></a>

Returns list of organizations with locations and policy mappings[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-organizations-with-locations-and-policy-mappings)

GET `/organizations-detailed`

#### List Device Roles[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-device-roles) <a href="#list-device-roles" id="list-device-roles"></a>

Returns list of device roles[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-device-roles)

GET `/roles`

#### List Supported 3rd Party Software[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-supported-3rd-party-software) <a href="#list-supported-3rd-party-software" id="list-supported-3rd-party-software"></a>

Returns available software products (3rd party patching)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-available-software-products-3rd-party-patching)

GET `/software-products`

#### List Devices (Detailed)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-devices-detailed) <a href="#list-devices-detailed" id="list-devices-detailed"></a>

Returns list of devices with additional information[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-devices-with-additional-information)

GET `/devices-detailed`

| Parameter     | Type   | Required | Description   |
| ------------- | ------ | -------- | ------------- |
| Device Filter | string | No       | Device Filter |

#### List Active Jobs[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-active-jobs) <a href="#list-active-jobs" id="list-active-jobs"></a>

Returns list of running jobs[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-running-jobs)

GET `/jobs`

| Parameter     | Type   | Required | Description     |
| ------------- | ------ | -------- | --------------- |
| Job Type      | string | No       | Job Type Filter |
| Device Filter | string | No       | Device Filter   |
| Lang          | string | No       | Language        |

#### List Locations[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-locations) <a href="#list-locations" id="list-locations"></a>

Returns flat list of all locations for all organizations[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-flat-list-of-all-locations-for-all-organizations)

GET `/locations`

#### List Scheduled Tasks[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-scheduled-tasks) <a href="#list-scheduled-tasks" id="list-scheduled-tasks"></a>

Returns list of registered scheduled tasks[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-registered-scheduled-tasks)

GET `/tasks`

#### List Groups (Saved Searches)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-groups-saved-searches) <a href="#list-groups-saved-searches" id="list-groups-saved-searches"></a>

Returns list of groups[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-groups)

GET `/groups`

| Parameter | Type   | Required | Description |
| --------- | ------ | -------- | ----------- |
| Lang      | string | No       | Language    |

#### List Activities[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-activities) <a href="#list-activities" id="list-activities"></a>

Returns activity log in reverse chronological order[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-activity-log-in-reverse-chronological-order)

GET `/activities`

| Parameter                                 | Type   | Required | Description                                                          |
| ----------------------------------------- | ------ | -------- | -------------------------------------------------------------------- |
| Class                                     | string | No       | Activity Class (System`/Device)` Filter                              |
| Activities Recorded Before Specified Date | string | No       |                                                                      |
| Activities Recorded After Specified Date  | string | No       |                                                                      |
| Older Than                                | string | No       | Return Activities Recorded That Are Newer Than Specified Activity ID |
| Newer Than                                | string | No       | Return Activities Recorded That Are Older Than Specified Activity ID |
| Activity Type                             | string | No       | Return Activities Of Type                                            |
| Status                                    | string | No       | Return Activities With Status(es)                                    |
| User                                      | string | No       | Return Activities For User(s)                                        |
| Series Uid                                | string | No       | Return Activities Related To Alert (Series)                          |
| Device Filter                             | string | No       | Device Filter                                                        |
| Lang                                      | string | No       | Language                                                             |

#### List Devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-devices) <a href="#list-devices" id="list-devices"></a>

Returns list of devices (basic node information)[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-devices-basic-node-information)

GET `/devices`

| Parameter     | Type   | Required | Description   |
| ------------- | ------ | -------- | ------------- |
| Device Filter | string | No       | Device Filter |

#### List Policies[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-policies) <a href="#list-policies" id="list-policies"></a>

Returns list of policies[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-policies)

GET `/policies`

#### List Users[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-users) <a href="#list-users" id="list-users"></a>

Returns list of users[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-users)

GET `/users`

| Parameter | Type   | Required | Description      |
| --------- | ------ | -------- | ---------------- |
| User Type | string | No       | User Type Filter |

#### Search for Devices[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#search-for-devices) <a href="#search-for-devices" id="search-for-devices"></a>

Returns list of entities matching the search term[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#returns-list-of-entities-matching-search-term)

GET `/devices/search`

| Parameter    | Type    | Required | Description                                                |
| ------------ | ------- | -------- | ---------------------------------------------------------- |
| Search Query | string  | No       | Search Query (Name, Logged On User Name, IP Address, Etc.) |
| Limit        | integer | No       | Limit Number Of Devices To Return                          |

### Ticketing

#### List Ticket Log Entries[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-ticket-log-entries) <a href="#list-ticket-log-entries" id="list-ticket-log-entries"></a>

Get a list of ticket log entries[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-list-of-ticket-log-entries)

GET `/ticketing/ticket/{ticketId}/log-entry`

| Parameter | Type    | Required | Description |
| --------- | ------- | -------- | ----------- |
| Ticket ID | integer | Yes      |             |
| Type      | string  | No       |             |

#### List Tickets For Board[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-tickets-for-board) <a href="#list-tickets-for-board" id="list-tickets-for-board"></a>

Get list of tickets by Board identifier[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-list-of-tickets-by-board-identifier)

`/ticketing/trigger/board/{boardId}/run`

| Parameter       | Type   | Required | Description |
| --------------- | ------ | -------- | ----------- |
| Board           | string | Yes      |             |
| Sort By         | array  | No       |             |
| Filters         | array  | No       |             |
| Search Criteria | string | No       |             |

#### List Boards[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-boards) <a href="#list-boards" id="list-boards"></a>

Get list of boards[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-list-of-boards)

GET `/ticketing/trigger/boards`

#### List Contacts[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-contacts) <a href="#list-contacts" id="list-contacts"></a>

Get list of contacts[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-list-of-contacts)

GET `/ticketing/contact/contacts`

#### List Ticket Forms[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#list-ticket-forms) <a href="#list-ticket-forms" id="list-ticket-forms"></a>

Get list of ticket forms[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#get-list-of-ticket-forms)

GET `/ticketing/ticket-form`

#### Modify Ticket[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#modify-ticket) <a href="#modify-ticket" id="modify-ticket"></a>

Modify a ticket on a board[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#modify-a-ticket-on-a-board)

PUT `/ticketing/ticket/{ticketId}`

| Parameter | Type    | Required | Description |
| --------- | ------- | -------- | ----------- |
| Ticket ID | integer | Yes      |             |
| Ticket    | object  | No       |             |
| Comment   | object  | No       |             |

#### Create Ticket[​](http://localhost:3000/docs/integrations/RMM/Ninja/ninja-rmm-integration#create-ticket) <a href="#create-ticket" id="create-ticket"></a>

`/ticketing/ticket`

| Parameter        | Type    | Required | Description |
| ---------------- | ------- | -------- | ----------- |
| requestUid       | string  | No       |             |
| clientId         | string  | No       |             |
| Ticket Form      | string  | No       |             |
| Location         | string  | No       |             |
| Node ID          | integer | No       |             |
| Summary          | string  | No       |             |
| Description      | object  | No       |             |
| Status           | string  | No       |             |
| Type             | string  | No       |             |
| User             | string  | No       |             |
| requesterUid     | string  | No       |             |
| CC List          | object  | No       |             |
| Attribute Values | array   | No       |             |
| Severity         | string  | No       |             |
| Priority         | string  | No       |             |
| Tags             | string  | No       | Tags        |
| Parent Ticket ID | integer | No       |             |
