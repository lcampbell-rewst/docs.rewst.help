---
description: 'Harness the Power of Nerdio: Key Features at Your Fingertips'
---

# Actions & Endpoints

## Introduction

The Nerdio Integration with Rewst delivers a robust set of actions and endpoints for interacting with various features within their platform:

* **Account Provisioning & Management**: Automate the creation and maintenance of accounts, ensuring efficient service delivery.
* **Resource Optimization**: Utilize tools like Cost Estimator and Reservations to manage and optimize cloud expenses.
* **Desktop & App Management**: Configure and manage desktop images and app role assignments with ease.
* **Data Protection**: Leverage backup and recovery vault features to ensure your clients' data is secure and recoverable.
* **Network Configuration**: Manage complex network setups and host pools, ensuring reliable and secure connectivity.
* **Custom Solutions**: Utilize generic requests and scripted actions to tailor solutions to specific client needs.

***

## Available Actions

Each feature is designed with MSPs in mind, ensuring you have the tools necessary to deliver exceptional cloud management services. Below is a summary of each section, highlighting the diverse capabilities and opportunities provided through the Nerdio Integration:

* [**Account Provisioning**](actions-and-endpoints.md#account-provisioning)
* [**Accounts**](actions-and-endpoints.md#accounts)
* [**App Role Assignments**](actions-and-endpoints.md#app-role-assignments)
* [**Backup**](actions-and-endpoints.md#backup)
* [**Cost Estimator**](actions-and-endpoints.md#cost-estimator)
* [**Desktop Image**](actions-and-endpoints.md#desktop-image)
* [**Directories**](actions-and-endpoints.md#directories)
* [**Fs Logix Configs**](actions-and-endpoints.md#fs-logix-configs)
* [**Generic Request**](actions-and-endpoints.md#generic-request)
* [**Host**](actions-and-endpoints.md#host)
* [**Host Pool**](actions-and-endpoints.md#host-pool)
* [**Invoices**](actions-and-endpoints.md#invoices)
* [**Job**](actions-and-endpoints.md#job)
* [**Networks**](actions-and-endpoints.md#networks)
* [**Recovery Vault**](actions-and-endpoints.md#recovery-vault)
* [**Reservations**](actions-and-endpoints.md#reservations)
* [**Resource Group**](actions-and-endpoints.md#resource-group)
* [**Scripted Actions**](actions-and-endpoints.md#scripted-actions)
* [**Secure Variables**](actions-and-endpoints.md#secure-variables)
* [**Storage Azure Files**](actions-and-endpoints.md#storage-azure-files)
* [**Test**](actions-and-endpoints.md#test)
* [**Timezones**](actions-and-endpoints.md#timezones)
* [**Usages**](actions-and-endpoints.md#usages)
* [**User Sessions**](actions-and-endpoints.md#user-sessions)
* [**Workspace**](actions-and-endpoints.md#workspace)

***

## Endpoint Details

### Account Provisioning

{% swagger baseUrl="<example-domain>.com" path="/accountprovisioning/linkTenant" method="post" summary="Link Tenant 1" %}
{% swagger-description %}
Step 1. Execute LinkTenant provision step, sync job
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accountprovisioning/linkNetwork" method="post" summary="Link Tenant 2" %}
{% swagger-description %}
Step 2. Start Azure configuration step
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accountprovisioning/connectToExistingAd" method="post" summary="Link Tenant 3" %}
{% swagger-description %}
Step 3. Start Connect to existing AD step (add job).
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accountprovisioning/createNewAzureAdds" method="post" summary="Link Tenant 4" %}
{% swagger-description %}
Step 4. Start Create new Azure DS step (add job)
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accountprovisioning/configureFileStorage" method="post" summary="Link Tenant 5" %}
{% swagger-description %}
Step 5. Start Configure file storage step (add job)
{% endswagger-description %}
{% endswagger %}

### Accounts

{% swagger baseUrl="<example-domain>.com" path="/accounts" method="get" summary="List Accounts" %}
{% swagger-description %}
Get list of accounts.
{% endswagger-description %}
{% endswagger %}

### App Role Assignments

{% swagger baseUrl="<example-domain>.com" path="/app-role-assignments" method="delete" summary="Unassign App Role" %}
{% swagger-description %}
Unassign App Role from Principals
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/app-role-assignments" method="get" summary="List Assigned Principals" %}
{% swagger-description %}
List all Assigned Principals
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/app-role-assignments" method="post" summary="Assign App Role" %}
{% swagger-description %}
Assign App Role to Principals
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/app-role-assignments" method="put" summary="Update App Role" %}
{% swagger-description %}
Update App Role for Principal
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/app-role-assignments/roles" method="get" summary="List App Roles" %}
{% swagger-description %}
List all app roles
{% endswagger-description %}
{% endswagger %}

### Backup

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup/protectedItems" method="get" summary="List all protected items" %}
{% swagger-description %}
Get all protected Items
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup/recoveryPoints" method="get" summary="Get Recovery points of protected item" %}
{% swagger-description %}
Get the recovery points of protected items
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup/enable" method="post" summary="Enable Backup" %}
{% swagger-description %}
Enable Backup
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup/restore" method="post" summary="Restore Resource" %}
{% swagger-description %}
Restore Resource to chosen recovery point
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup/disable" method="post" summary="Disable Resource" %}
{% swagger-description %}
Disable Resource. The resource will be removed from the backup policy and will no longer be backed up. You will be able to restore from any recovery points available so far.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup/deleteBackupData" method="post" summary="Disable Backup Date" %}
{% swagger-description %}
Delete Backup Date. The resource will be removed from the backup vault. You will not be able to restore this resource.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/backup" method="post" summary="Backup Resource" %}
{% swagger-description %}
Backup Resource. Execute backup of current resource
{% endswagger-description %}
{% endswagger %}

### Cost Estimator

{% swagger baseUrl="<example-domain>.com" path="/costestimator/{id}" method="get" summary="Get Estimate by Id" %}
{% swagger-description %}
Get the saved estimate by ID
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/costestimator/list" method="get" summary="List Saved Estimates" %}
{% swagger-description %}
List all Saved Estimates
{% endswagger-description %}
{% endswagger %}

### Desktop Image

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}" method="delete" summary="Delete Desktop Image" %}
{% swagger-description %}
Delete desktop image
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}" method="get" summary="Get Desktop Image" %}
{% swagger-description %}
Get desktop image in detail
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}/power-off-and-set-as-image-configuration" method="delete" summary="Remove " %}
{% swagger-description %}
Remove 'set as image schedule configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image" method="get" summary="List Desktop Images" %}
{% swagger-description %}
List all desktop images in detail
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}/change-log" method="get" summary="List Changes to Image" %}
{% swagger-description %}
List all changed made to the desktop image
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}/open-rdp" method="post" summary="Open RDP Access" %}
{% swagger-description %}
Open RDP Access
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/create-from-library" method="post" summary="Create Desktop Image From Azure Library" %}
{% swagger-description %}
Create desktop image from azure library
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/create-from-vm" method="post" summary="Create Desktop Image From Azure VM" %}
{% swagger-description %}
Create desktop image from azure VM
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}/clone" method="post" summary="Clone Desktop Image" %}
{% swagger-description %}
Clone desktop image
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}/run-script" method="put" summary="Run Scripted Actions on Desktop Image" %}
{% swagger-description %}
Run scripted actions on desktop image
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/desktop-image/{subscriptionId}/{resourceGroup}/{name}/stop" method="put" summary="Power Off Desktop Image" %}
{% swagger-description %}
Power off current desktop image
{% endswagger-description %}
{% endswagger %}

### Directories

{% swagger baseUrl="<example-domain>.com" path="/directories" method="get" summary="List all directories" %}
{% swagger-description %}
List all directories
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/directories" method="get" summary="List directories by Account" %}
{% swagger-description %}
List directories by Account
{% endswagger-description %}
{% endswagger %}

### Fs Logix Configs

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/fslogix" method="get" summary="List FSLogix configs" %}
{% swagger-description %}
List all existing FSLogix configs
{% endswagger-description %}
{% endswagger %}

### Generic Request

{% swagger baseUrl="<example-domain>.com" path="/<url_path>" method="get" summary="Nerdio API Request" %}
{% swagger-description %}
Generic action for making authenticated requests against the Nerdio API
{% endswagger-description %}
{% endswagger %}

### Host

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}" method="delete" summary="Remove Host" %}
{% swagger-description %}
Remove chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts" method="get" summary="List All Hosts" %}
{% swagger-description %}
List all hosts of the host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts" method="post" summary="Create Host" %}
{% swagger-description %}
Create host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/start" method="post" summary="Start Host" %}
{% swagger-description %}
Power on chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/start" method="post" summary="Stop Host" %}
{% swagger-description %}
Power off chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/restart" method="post" summary="Restart Host" %}
{% swagger-description %}
Restart chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/allowsessions" method="post" summary="Allow Host" %}
{% swagger-description %}
Activate / Deactivate chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/reimage" method="post" summary="Reimage Host" %}
{% swagger-description %}
Reimage chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/assignUser" method="post" summary="Assign User to Host" %}
{% swagger-description %}
Assign, Unassign, or Reassign user chosen host
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/run-script" method="put" summary="Run Scripted Action on Host" %}
{% swagger-description %}
Run Scripted Action on Host
{% endswagger-description %}
{% endswagger %}

### Host Pool

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}" method="delete" summary="Remove Host Pool" %}
{% swagger-description %}
Remove chosen host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/auto-scale-pause" method="delete" summary="Remove Autoscale Pause" %}
{% swagger-description %}
Remove autoscale pause for host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/auto-scale-pause" method="put" summary="Pause Autoscale" %}
{% swagger-description %}
Pause autoscale for host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/delete-bulk" method="delete" summary="Delete All Hosts" %}
{% swagger-description %}
Delete all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/schedule-configuration/{jobType}" method="delete" summary="Remove Job Schedule Configuration" %}
{% swagger-description %}
Remove Job Schedule Configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool" method="get" summary="List Host Pools" %}
{% swagger-description %}
List all host pools in the account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool" method="post" summary="Create Host Pool" %}
{% swagger-description %}
Create Host Pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/autoscale-configuration" method="get" summary="Get Host Pool Autoscale Config" %}
{% swagger-description %}
Get the host pool current autoscale configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/autoscale-configuration" method="put" summary="Update Host Pool Autoscale Config" %}
{% swagger-description %}
Update the host pool current autoscale configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/autoscale-settings" method="get" summary="Get Host Pool Autoscale Settings" %}
{% swagger-description %}
Get the host pool current autoscale settings
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/autoscale-settings" method="put" summary="Update Host Pool Autoscale Settings" %}
{% swagger-description %}
Update the host pool current autoscale settings
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/active-directory" method="get" summary="Get Host Pool AD" %}
{% swagger-description %}
Get the host pool current AD
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/active-directory" method="put" summary="Update Host Pool AD" %}
{% swagger-description %}
Update the host pool current AD
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/avd" method="get" summary="Get Host Pool Properties" %}
{% swagger-description %}
Get the host pool current properties
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/avd" method="put" summary="Update Host Pool Properties" %}
{% swagger-description %}
Update the host pool current properties
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/vm-deployment" method="get" summary="Get Host Pool VM Deployment Settings" %}
{% swagger-description %}
Get the host pool current VM deployment settings
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/vm-deployment" method="put" summary="Update Host Pool VM Deployment Settings" %}
{% swagger-description %}
Update the host pool current VM deployment Settings
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/fslogix" method="get" summary="Get Host Pool FSLogix Config" %}
{% swagger-description %}
Get the host pool current FSLogix Config
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/fslogix" method="put" summary="Update Host Pool FXLogix Config" %}
{% swagger-description %}
Update the host pool current FXLogix Config
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/session-timeouts" method="get" summary="Get Host Pool Session Timeouts" %}
{% swagger-description %}
Get the host pool current Session Timeouts
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/session-timeouts" method="put" summary="Update Host Pool Session Timeouts" %}
{% swagger-description %}
Update the host pool current Session Timeouts
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/tags" method="get" summary="List Host Pool Tags" %}
{% swagger-description %}
List the host pool current tags
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/tags" method="put" summary="Update Host Pool Tags" %}
{% swagger-description %}
Update the host pool current tags
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/assigned-users" method="get" summary="List Users Assigned to Host Pool" %}
{% swagger-description %}
List the users assigned to the current host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/assign" method="post" summary="Assign User to Host Pool" %}
{% swagger-description %}
Assign user to host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/unassign" method="post" summary="Unassign User to Host Pool" %}
{% swagger-description %}
Unassign user to host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/clone" method="post" summary="Clone Host Pool" %}
{% swagger-description %}
Clone the chosen host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/stop-bulk" method="post" summary="Power Off Host Pools" %}
{% swagger-description %}
Power off all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/start-bulk" method="post" summary="Power On Host Pools" %}
{% swagger-description %}
Power on all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/restart-bulk" method="post" summary="Restart Host Pools" %}
{% swagger-description %}
Restart all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/reimage" method="post" summary="Reimage Host Pools" %}
{% swagger-description %}
Resize or reimage all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/allowsessions" method="post" summary="Toggle Host Pools" %}
{% swagger-description %}
Activeate / Deactivate all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/run-script-bulk" method="post" summary="Run Script on Host Pools" %}
{% swagger-description %}
Run script on all hosts in the pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/auto-scale-enable" method="put" summary="Toggle Autoscale for Host Pool" %}
{% swagger-description %}
Toggle Autoscale for host pool with current configuratoins
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/capacity-extender-properties" method="put" summary="Set Host Pool Capacity Extender Properties" %}
{% swagger-description %}
Set host pool capacity extender properties
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/logoff" method="put" summary="Log Off All Users" %}
{% swagger-description %}
Log off all users from host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/disconnect" method="put" summary="Disconnect All Users" %}
{% swagger-description %}
Disonnect all users from host pool
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/send-message" method="put" summary="Send Message" %}
{% swagger-description %}
Send message to all sessions for host pool
{% endswagger-description %}
{% endswagger %}

### Invoices

{% swagger baseUrl="<example-domain>.com" path="/invoices" method="get" summary="List Invoices" %}
{% swagger-description %}
List all invoices
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/invoices/{id}" method="get" summary="Get Invoice" %}
{% swagger-description %}
Get invoice details
{% endswagger-description %}
{% endswagger %}

### Job

{% swagger baseUrl="<example-domain>.com" path="/job/{jobId}" method="get" summary="Get Job" %}
{% swagger-description %}
Get job information by Id
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/job/{jobId}/tasks" method="get" summary="List Tasks" %}
{% swagger-description %}
List all tasks of job by job id
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/job/restart/{jobId}" method="post" summary="Restart Job" %}
{% swagger-description %}
Restart job
{% endswagger-description %}
{% endswagger %}

### Networks

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/networks" method="get" summary="List Managed Networks" %}
{% swagger-description %}
List managed networks by account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/networks/all" method="get" summary="List All Available Networks" %}
{% swagger-description %}
List all available networks by account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/networks/link" method="get" summary="Link Existing Network" %}
{% swagger-description %}
Link existing network
{% endswagger-description %}
{% endswagger %}

### Recovery Vault

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/policy" method="delete" summary="Delete Policy from Vault" %}
{% swagger-description %}
Delete policy from vault
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/policy" method="get" summary="Get Policy Data" %}
{% swagger-description %}
Get policy data
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault" method="get" summary="List Managed Vaults" %}
{% swagger-description %}
List all managed Vaults
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault" method="post" summary="Create New Vaults" %}
{% swagger-description %}
Create new vault
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/allvaults" method="get" summary="List All Vaults" %}
{% swagger-description %}
Get all managed Vaults
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/policies" method="get" summary="List All Policies in Vault" %}
{% swagger-description %}
Get all policies in the Vault
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/regionpolicyinfo/{subscriptionId}/{region}" method="get" summary="Get Region Information" %}
{% swagger-description %}
Get information about region protection by policies
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/link/vault" method="post" summary="Link to Vault" %}
{% swagger-description %}
Link to existing vault
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/unlink/vault" method="post" summary="Unlink Vault" %}
{% swagger-description %}
Unink vault
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/createorupdate/policy" method="post" summary="Create Policy" %}
{% swagger-description %}
Create New Policy
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/recovery-vault/assignpoliciestoresources" method="post" summary="Assign Policy to Resource" %}
{% swagger-description %}
Assign policy o resources
{% endswagger-description %}
{% endswagger %}

### Reservations

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/reservations/{reservationId}" method="delete" summary="Delete Reservation" %}
{% swagger-description %}
Delete reservation by Id
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/reservations/{reservationId}" method="get" summary="Get Reservation" %}
{% swagger-description %}
Get reservation by Id
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/reservations/{reservationId}" method="put" summary="Update Reservation" %}
{% swagger-description %}
Update existing reservation by Id
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/reservations" method="get" summary="List Reservations" %}
{% swagger-description %}
List all reservation
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/reservations" method="post" summary="Add Reservations" %}
{% swagger-description %}
Add new reservation
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/reservations/{reservationId}/resources" method="get" summary="List Resource Names" %}
{% swagger-description %}
List all resource names associated to reservation
{% endswagger-description %}
{% endswagger %}

### Resource Group

{% swagger baseUrl="<example-domain>.com" path="/resource-group/linked" method="delete" summary="Unlink Resource Group" %}
{% swagger-description %}
Unlink Azure resource group
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/resource-group/linked" method="post" summary="Link Resource Group" %}
{% swagger-description %}
Link Azure resource group
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/resource-group/linked" method="delete" summary="Unlink Resource Group by Account" %}
{% swagger-description %}
Unlink Azure resource group
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/resource-group/linked" method="post" summary="Link Resource Group by Id" %}
{% swagger-description %}
Link Azure resource group by id
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/resource-group" method="get" summary="List Managed Resource Groups" %}
{% swagger-description %}
List all managed resource groups
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/resource-group" method="get" summary="List Managed Resource Groups by Account" %}
{% swagger-description %}
List all managed resource groups by account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/resource-group/setDefault" method="put" summary="Set Resource Group as Default" %}
{% swagger-description %}
Set Azure resource group as default
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/resource-group/setDefault" method="put" summary="Set Resource Group as Default by Account" %}
{% swagger-description %}
Set Azure resource group as default by account
{% endswagger-description %}
{% endswagger %}

### Scripted Actions

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions/{id}" method="delete" summary="Delete MSP Scripted Action" %}
{% swagger-description %}
Delete MSP scripted Action
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions/{id}" method="put" summary="Update MSP Scripted Action" %}
{% swagger-description %}
Update MSP scripted Action
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions/{id}/schedule" method="delete" summary="Delete Azure MSP Scripted Action Schedule Configuration" %}
{% swagger-description %}
Delete Azure MSP Scripted Action Schedule Configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions/{id}/schedule" method="get" summary="Get Azure MSP Scripted Action Schedule Configuration" %}
{% swagger-description %}
Get azure runbook msp scripted action schedule configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions/{id}/schedule" method="put" summary="Schedule Azure MSP Scripted Action" %}
{% swagger-description %}
Schedule Azure runbook msp scripted action execution in Automation account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions/{id}" method="delete" summary="Delete Account Scripted Action" %}
{% swagger-description %}
Delete Account Scripted Action
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions/{id}" method="put" summary="Update Account scripted Action" %}
{% swagger-description %}
Update account scripted action
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions/{id}/schedule" method="delete" summary="Delete Azure runbook Account Scripted Action Schedule Configuration" %}
{% swagger-description %}
Delete Azure runbook account scripted action schedule confirmation
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions/{id}/schedule" method="get" summary="Get Azure runbook Account Scripted Action Schedule Configuration" %}
{% swagger-description %}
Get Azure runbook Account Scripted Action Schedule Configuration
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions/{id}/schedule" method="post" summary="Schedule Azure runbook Account Scripted Action Execution in Automation Account" %}
{% swagger-description %}
Schedule Azure runbook Account Scripted Action in Automation Account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions" method="get" summary="List MSP Scripted Actions" %}
{% swagger-description %}
List all msp scripted actions
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions" method="post" summary="Create MSP Scripted Action" %}
{% swagger-description %}
Create MSP Scripted Action
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions" method="get" summary="List MSP Scripted Actions by Account" %}
{% swagger-description %}
List all msp scripted actions by account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions" method="post" summary="Create Account Scripted Action" %}
{% swagger-description %}
Create account Scripted Action
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/scripted-actions/{id}/execution" method="post" summary="Run Azure runbook MSP Scripted Action in Automation Account" %}
{% swagger-description %}
Run Azure runbook MSP Scripted Action in Automation Account
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/scripted-actions/{id}/execution" method="post" summary="Run Azure runbook MSP Scripted Action in Automation Account by Account" %}
{% swagger-description %}
Run Azure runbook MSP Scripted Action in Automation Account by account
{% endswagger-description %}
{% endswagger %}

### Secure Variables

{% swagger baseUrl="<example-domain>.com" path="/secure-variables" method="delete" summary="Delete MSP Secure Variable" %}
{% swagger-description %}
Delete msp secure variable
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/secure-variables" method="get" summary="List MSP Secure Variables" %}
{% swagger-description %}
List all MSP secure variables
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/secure-variables" method="post" summary="Create MSP Secure Variable" %}
{% swagger-description %}
Create MSP secure variable
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/secure-variables" method="put" summary="Update MSP Secure Variable" %}
{% swagger-description %}
Update MSP secure variable
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/secure-variables" method="delete" summary="Delete Account Secure Variable" %}
{% swagger-description %}
Delete account secure variable
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/secure-variables" method="get" summary="List Account Secure Variables" %}
{% swagger-description %}
List all account secure variables
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/secure-variables" method="post" summary="Create Account Secure Variable" %}
{% swagger-description %}
Create Account secure variable
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/secure-variables" method="put" summary="Update Account Secure Variable" %}
{% swagger-description %}
Update account secure variable
{% endswagger-description %}
{% endswagger %}

### Storage Azure Files

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/storage/azure-files/{subscriptionId}/{resourceGroup}/{storageAccountName}/{shareName}/auto-scale" method="get" summary="Get Azure Files Autoscale" %}
{% swagger-description %}
Get Azure Files Autoscale
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/storage/azure-files/{subscriptionId}/{resourceGroup}/{storageAccountName}/{shareName}/auto-scale" method="put" summary="Update Azure Files Autoscale" %}
{% swagger-description %}
Update Azure Files Autoscale
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/storage/azure-files/{subscriptionId}/{resourceGroup}/{storageAccountName}/{shareName}/auto-scale/enabled/{isEnabled}" method="post" summary="Toggle Azure Files Autoscale" %}
{% swagger-description %}
Enable/Disable Azure Files Autoscale
{% endswagger-description %}
{% endswagger %}

### Test

{% swagger baseUrl="<example-domain>.com" path="/test" method="get" summary="Test" %}
{% swagger-description %}
Test
{% endswagger-description %}
{% endswagger %}

### Timezones

{% swagger baseUrl="<example-domain>.com" path="/timezones" method="get" summary="List Timezones ids" %}
{% swagger-description %}
List out the timezones
{% endswagger-description %}
{% endswagger %}

### Usages

{% swagger baseUrl="<example-domain>.com" path="/usages" method="get" summary="List Usages" %}
{% swagger-description %}
List Usages
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/usages" method="get" summary="List Usages by Account" %}
{% swagger-description %}
List Usages by Account
{% endswagger-description %}
{% endswagger %}

### User Sessions

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/sessions" method="get" summary="List Host Pool User Sessions" %}
{% swagger-description %}
List all host pool user sessions
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/workspace/{subscriptionId}/{resourceGroup}/{workspaceName}/sessions" method="get" summary="List workspace user sessions" %}
{% swagger-description %}
List all host pool user sessions
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/session/{sessionId}/action/logoff" method="post" summary="Perform Logoff Action for Host Pool User Session" %}
{% swagger-description %}
Perform logoff actoin for host pool user session
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/session/{sessionId}/action/disconnect" method="post" summary="Perform Disconnect Action for Host Pool User Session" %}
{% swagger-description %}
Perform disconnect action for host pool user session
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/host-pool/{subscriptionId}/{resourceGroup}/{poolName}/hosts/{hostName}/session/{sessionId}/action/send-message" method="post" summary="Send Message for Host Pool User Session" %}
{% swagger-description %}
Send Message action for host pool user session
{% endswagger-description %}
{% endswagger %}

### Workspace

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/workspace" method="get" summary="List Workspaces" %}
{% swagger-description %}
List available workspaces
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="<example-domain>.com" path="/accounts/{accountId}/workspace" method="post" summary="Create Workspace" %}
{% swagger-description %}
Create workspace for provided account
{% endswagger-description %}
{% endswagger %}
