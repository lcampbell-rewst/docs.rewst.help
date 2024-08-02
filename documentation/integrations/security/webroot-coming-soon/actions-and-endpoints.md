# Actions & Endpoints

## Introduction

The Webroot Integration with Rewst delivers a robust set of actions and endpoints for interacting with Webroot. Below is a summary of each section, highlighting the diverse capabilities and opportunities provided through the Webroot Integration:

* [**Console Access**](actions-and-endpoints.md#console-access)
* [**Console GSM**](actions-and-endpoints.md#console-gsm)
* [**Ecom**](actions-and-endpoints.md#ecom)
* [**Generic Request**](actions-and-endpoints.md#generic-request)
* [**Healthcheck**](actions-and-endpoints.md#healthcheck)
* [**Notifications**](actions-and-endpoints.md#notifications)
* [**Skystatus**](actions-and-endpoints.md#skystatus)

## Actions

### Console Access

## Request Admin Access to GSM Console

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/access/gsm/{gsmKey}/addadminrequest`

Initiates the process for requesting admin access to a GSM console. Before initiating, it's the requester's responsibility to inform the owner of the target GSM console that a designated person will receive a confirmation message from Webroot.

## Get GSM Add Admin Access Request Status

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/access/gsm/{gsmKey}/addadminstatus`

Retrieves the status of a GSM add admin access request.

### Console Gsm

## Get GSM Console Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}`

Required Scope Console.GSM Gets information about a given GSM console.

## Get GSM Console Information by Site Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/lookupsite/{siteKeycode}`

Scope Console.GSM Looks up information about a specific GSM site which is associated with a given site keycode. You can use this method to query site details using a site keycode and to retrieve the site's identifier for follow-up calls.

## Get Web Console URL to Corresponding GSM Console

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/webconsoleurl`

Gets a URL to the Webroot web console that, when used in a browser, automatically logs the authenticated user in to the corresponding GSM Console.

## Get Web Console URL to Corresponding Endpoint Protection Console

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/webconsoleurl`

Gets a URL to the Webroot web console that, when used in a browser, automatically logs the authenticated user in to the corresponding Endpoint Protection Console.

## List Sites Associated With A Given Gsm Console.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites`

Gets the list of sites associated with a given GSM console.

## Get GSM Site Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}`

Gets information about a GSM site.

## Create New Site Under A Given Gsm Console.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites`

Creates a New Site Under A Given Gsm Console.

## Update Site Under A Given Gsm Console.

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}`

Description coming soon...

## Deactivate A Site Under A Given Gsm Console.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/deactivate`

Deactivates a site under a given GSM console.

## Suspends A Site Under A Given Gsm Console.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/suspend`

When a site is suspended the associated license key is forcibly expired.

## Resumes A Site Under A Given Gsm Console.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/resume`

When a site is resumed, the site's license key inherits the days remaining of the parent GSM console keycode.

## Converts A Trial Site Into A Full License.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/converttrial`

This operation will fail, if the parent GSM console license is not a full license.

## List Admins On A Given Gsm Console.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/admins`

Gets the list of admins on a given GSM console.

## Add New User as Admin to GSM Console

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/admins`

Adds a new user as an admin to a GSM console with the desired access level.

## Get GSM Admin Information.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/admins/{userId}`

Gets information about a GSM admin.

## Update User Account Attributes Of A GSM Admin.

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/admins/{userId}`

Description coming soon...

## Removes GSM Admin From A Gsm Console And All Its Sites.

<mark style="color:red;">`DELETE`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/admins/{userId}`

Description coming soon...

## List Admins On GSM Site.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/admins`

Description coming soon...

## Gets Site Admin Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/admins/{userId}`

Gets information about a site admin.

## Adds New User As A Site Admin To A Site With The Desired Access Level.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/admins`

Adds a new user as a site admin to a site with the desired access level.

## Adds Admins To A Site Or Modifies Access Permissions Of Site Admins.

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/admins`

Adds Admins to a site or modifies access permissions of site admins. Depending on the number of permission changes made, these modifications may take up to a few minutes to be processed and reflected by other API calls accordingly.

## Update Certain User Account Attributes Of A Site Admin

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/admins/{userId}`

Edits certain user account attributes of a site admin.

## Remove Admin From A Site

<mark style="color:red;">`DELETE`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/admins/{userId}`

Admin will be removed from the site. If the admin is an admin on the parent GSM console, the admins permissions on the GSM and its other sites remain unchanged - the user's access level will be set to 0 (no access) for the specified site only.

## List Global Policies On A Given Gsm Console

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/policies`

Description coming soon...

## Get Information About A Gsm Policy

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/policies/{policyId}`

Description coming soon...

## List Policies On A Given GSM Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/policies`

Description coming soon...

## Get Information About A Site Policy

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/policies/{policyId}`

Description coming soon...

## List Groups On A Given GSM Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups`

Description coming soon...

## Create Group Under GSM Site

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups`

Description coming soon...

## Get Group Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}`

Description coming soon...

## Update Group Under A Given GSM Site

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}`

Description coming soon...

## Deletes Group Under A Given GSM Site

<mark style="color:red;">`DELETE`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}`

Description coming soon...

## List Endpoints On A Given GSM Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints`

Description coming soon...

## Move Endpoints To A Different Group.

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints`

Description coming soon...

## Get Endpoint Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/{endpointId}`

Description coming soon...

## List Endpoints On A Given Group

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}/endpoints`

Description coming soon...

## Apply New Policy To Specified Endpoints

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/policy`

Description coming soon...

## Apply New Policy To Group Of Endpoints

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}/endpoints/policy`

Description coming soon...

## Reactivate List Of Endpoints Or All Endpoints On A Site.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/reactivate`

This command is only applied to deactivated endpoints.

## Deactivate List Of Endpoints, Or All Endpoints On A Site.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/deactivate`

Description coming soon...

## Deactivate All Endpoints In A Group

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}/endpoints/deactivate`

Description coming soon...

## List Executed Commands On A Given GSM Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/commands`

Description coming soon...

## List Executed Commands On A Given Group

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}/commands`

Only returns the executed commands from the past 6 months.

## List Executed Commands On A Given Endpoint

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/{endpointId}/commands`

Only returns the executed commands from the past 6 months.

## Issue An Agent Command To A List Of Endpoints, Or To All Endpoints On A Site.

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/commands`

Description coming soon...

## Issue An Agent Command To A Group Of Endpoints

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}/endpoints/commands`

Description coming soon...

## Get Threat History Information For Endpoints On A GSM Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/threathistory`

\*\*NOTE:\*\* The maximum allowed time difference between 'startDate' and 'endDate' is 3 calendar months.

## Get Threat History Information For Endpoints On A Group

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/groups/{groupId}/threathistory`

\*\*NOTE:\*\* The maximum allowed time difference between 'startDate' and 'endDate' is 3 calendar months.

## Get Threat History Information For A Given Endpoint

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/endpoints/{endpointId}/threathistory`

\*\*NOTE:\*\* The maximum allowed time difference between 'startDate' and 'endDate' is 3 calendar months.

## Get Per Day Summary Counts Of Number Of Recorded Url Actions On Endpoints In The Given Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/blockedurls/counts`

\*\*NOTE:\*\* Blocked URLs data is generally available for as far as 90 days in the past. However, the maximum allowed time range between 'startDate' and 'endDate' is 30 days.

## List Recorded Url Actions On Endpoints In The Given Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/blockedurls/data`

\*\*NOTE:\*\* Blocked URLs data is generally available for as far as 90 days in the past. However, the maximum allowed time range between 'startDate' and 'endDate' is 30 days.

## List Available DNS Protection Categories And Respective Identifiers

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/categories`

Description coming soon...

## List Available DNS Protection Policies And Respective Identifiers For GSM Parent Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/policies`

Description coming soon...

## Get Specified DNS Protection Policy Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/policies/{policyId}`

Description coming soon...

## Get Defined Mappings Of DNS Protection Policies For A GSM Parent Keycode, Filtered By The Given Site.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/mappings`

Description coming soon...

## Creates Mapping For DNS Protection Policy For GSM Site

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/mappings`

Description coming soon...

## Get Mapping Of DNS Protection Policy Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/mappings/{mappingId}`

Returns detailed information for a specified mapping of a DNS Protection policy.

## Update Specified Mapping Of A DNS Protection Policy

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/mappings/{mappingId}`

Description coming soon...

## Delete Specified Mapping Of DNS Protection Policy

<mark style="color:red;">`DELETE`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/mappings/{mappingId}`

Description coming soon...

## List Available DNS Protection Block Reasons And Respective Identifiers

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/blockreasons`

Description coming soon...

## Get Information About Dns Requests That Were Blocked By The Dns Protection Service.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/blockedtraffic`

The maximum allowed time difference between 'startDate' and 'endDate' is 30 days. WARNING The maximum number of returned traffic records is limited. For high-use sites, query more regularly for shorter periods rather than pulling data for 30 days at once

## Get DNS Request Information Seen by DNS Protection Services for One or More Specified Categories

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/trafficbycategory`

The maximum allowed time difference between 'startDate' and 'endDate' is 30 days. WARNING The maximum number of returned traffic records is limited. For high-use sites, query more regularly for shorter periods rather than pulling data for 30 days at once

## Get Traffic Summary for Each Site Under Given GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/trafficsummary`

\*\*NOTE:\*\* The maximum allowed time difference between 'startDate' and 'endDate' is 30 days.

## Get Traffic Summary For Specific Site Under Given GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/trafficsummary`

Returns a traffic summary (e.g. the number of total DNS requests, blocked DNS requests, and risky DNS requests) for a specific site under a given GSM. "\*\*NOTE:\*\* The maximum allowed time difference between 'startDate' and 'endDate' is 30 days."

## Get Traffic Summary Grouped By Categories For Given GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/trafficsummary/categoryreport`

Returns a traffic summary (e.g. the number of total DNS requests, blocked DNS requests, and allowed DNS requests) grouped by categories for a given GSM. "\*\*NOTE:\*\* The maximum allowed time difference between 'startDate' and 'endDate' is 30 days."

## Get Traffic Summary Grouped By Categories For Specific Site Under Given GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/trafficsummary/categoryreport`

Get traffic summary (e.g. the number of total DNS requests, blocked DNS requests, and allowed DNS requests) grouped by categories for a specific site under a given GSM. The maximum allowed time difference between 'startDate' and 'endDate' is 30 days."

## Get Traffic Summary Grouped By Categories And Users For Given Gsm.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/dnsp/trafficsummary/categoryuserreport`

Returns a traffic summary (e.g. the number of blocked DNS requests, allowed DNS requests, and user name) grouped by categories and users for a given GSM.The maximum allowed time difference between 'startDate' and 'endDate' is 30 days."

## Get Traffic Summary Grouped By Categories And Users For Specific Site Under Given GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/dnsp/trafficsummary/categoryuserreport`

Get traffic summary (e.g. the number of blocked DNS requests, allowed DNS requests, and user name) grouped by categories and users for a specific site under a given GSM. The maximum allowed time difference between 'startDate' and 'endDate' is 30 days."

## Get Activity Overview for Webroot Security Awareness Training (WSAT) Phishing Campaigns on a Specific Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/wsat/campaigns/phishing/activity`

Get information on activity seen for Webroot Security Awareness Training (WSAT) phishing campaigns associated to a given site. The \*startDate\* cannot be earlier than one year ago, and the timespan between \*startDate\* and \*endDate\* must not exceed 90 days.

## Get Activity Overview for Webroot Security Awareness Training (WSAT) Campaigns for a Specific Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/console/gsm/{gsmKey}/sites/{siteId}/wsat/campaigns/training/activity`

Get information on activity seen for Webroot Security Awareness Training (WSAT) training campaigns associated to a given site. The \*startDate\* cannot be earlier than one year ago, and the timespan between \*startDate\* and \*endDate\* must not exceed 90 days.

### Ecom

## Create New Shopping Cart

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/carts`

Creates a new shopping cart. Carts act as a container for pending orders.

## Get Cart by VendorOrderCode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/carts/{vendorOrderCode}`

Gets a cart by it's vendorOrderCode. The response will also include the cart's items and customers, if present.

## Create End/Reseller Customer

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/carts/{vendorOrderCode}/customers`

Creates end customer (shipping) and/or reseller customer records to associate to a given cart. Note that a billing customer is associated when the cart is created and cannot be modified.

## Get Customers

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/carts/{vendorOrderCode}/customers`

Gets the customers associated to a cart.

## Create Order by Processing Cart

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/carts/{vendorOrderCode}/customers`

Create Order by Processing Cart

## Get Order Status Info

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/products/{keycode}/orderstatus`

Gets information about the order status for a keycode

## Cancel Product

<mark style="color:red;">`DELETE`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/products/{keycode}/licensecategory/{licenseCategoryName}`

Creates a request to cancel a particular product.

## Get License by Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/products/{keycode}`

Get License by Keycode

## Get Child Licenses

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/products/{keycode}/childlicenses`

Gets all child licenses of a parent license, but without billing information which is maintained by the parent license.

## Create Trial License

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/trials`

Creates a trial license for a given product

## Create Trial Modules

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/ecom/shop/trials/{keycode}/modules`

Creates trial module for a given parent keycode

### Generic Request

## Webroot API Request

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/<url_path>`

Generic action for making authenticated requests against the Webroot API

### Healthcheck

## Get Health Ping

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/health/ping`

Empty action that can be used to ping for the availability of the service.

## Get Health Version

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/health/version`

Retrieves version information of the running service environment.

### Notifications

## List Available Event Types and Subscription Details with Required Permissions

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/eventtypes`

Gets a list of available event types that can be subscribed to, with information on required scope permissions and subscription domains for each event type.

## Get Active Subscriptions Information With The Authenticated Caller.

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions`

Subscriptions are maintained on the basis of username and client id. Only subscriptions that have been created and are active for the username and client id pair of the caller are returned.

## Create New Subscription

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions`

Please refer to https://unityapi.webrootcloudav.com/Docs/en/APIDoc/Api/POST-api-notifications-subscriptions

## Get Specific Subscription Information

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}`

Description coming soon...

## Update Specific Subscription Information

<mark style="color:orange;">`PUT`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}`

For webhook-based subscriptions When changing DeliveryContext or DeliveryUrl, a validation call will be made. The webhook must respond with the expected ValidationResponse matching the ValidationContext. RE - Notifications Guide

## Unsubscribe From A Specific Subscription

<mark style="color:red;">`DELETE`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}`

Unsubscribing from a subscription means that no more notifications will be made available under this specific subscription.

## Get Latest Notifications For A Specific Subscription

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}/fetch`

Returns notifications for a subscription in chronological order, up to 1000 per call. Use the NextPosition value from the previous response for subsequent calls. The response indicates if more notifications are available

## Create A Position Token To Start Fetching Notifications

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}/position`

Generates A Position Token To Start Fetching Notifications

## Suspends Calls To The Subscription

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}/suspendwebhook`

Suspends calls to the subscription's webhook DeliveryUrl for informing about new notifications.

## Resumes Calls To The Subscription

<mark style="color:green;">`POST`</mark> `unityapi.webrootcloudav.com/service/api/notifications/subscriptions/{subscriptionId}/resumewebhook`

Resumes calls to the subscription's webhook DeliveryUrl for informing about new notifications.

### Skystatus

## Get Agent Status for Endpoints - GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/gsm/{keyCode}`

Required Scope - SkyStatus.GSM. Returns agent status information for all endpoints matching the specified criteria.

## Get DNS Protection Status for Endpoints - GSM

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/gsm/dnsp/{keyCode}`

Required Scope - SkyStatus.GSM. Returns DNS protection (DNSP) status information for all endpoints matching the specified criteria.

## Get Agent Status for Endpoints - Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/gsm/{keyCode}`

Required Scope - SkyStatus.Site. Returns agent status information for all endpoints matching the specified criteria.

## Get DNS Protection Status for Endpoints - Site

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/gsm/dnsp/{keyCode}`

Required Scope - SkyStatus.Site. Returns DNS protection (DNSP) status information for all endpoints matching the specified criteria.

## Get Site-level Summary Report of Endpoint Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites`

Required Scope SkyStatus.Reporting - Returns a site-level summary report of endpoint usage for a GSM master keycode. For each site the report includes information like the site name and license type as well as the total number of endpoints.

## Get GSM-level summary Report of Endpoint Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}`

Required Scope SkyStatus.Reporting - Returns a GSM-level summary report of endpoint usage for a GSM master keycode. Besides general information like the console name and type of GSM license the report includes the total number of sites and endpoints.

## Get Site-level Summary Report of Endpoint Usage by Site Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites/{keyCode}`

Required Scope SkyStatus.Reporting - Returns a site-level summary report of endpoint usage for a GSM master keycode by a site keycode. The report includes information like the site name and license type as well as the total number of endpoints.

## Get Endpoint-level Summary Report of Endpoint Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/endpoints`

Required Scope SkyStatus.Reporting - Returns an endpoint-level summary report of endpoint usage for a GSM master keycode. For each endpoint the report includes information like the endpoint's hostname, machine identifier, and its activation state

## Get Endpoint-level Summary Report of Endpoint Usage by Site Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites/{keyCode}/endpoints`

Scope SkyStatus.Reporting- Returns an endpoint-level summary report of endpoint usage for a GSM master keycode by a site keycode. For each endpoint the report includes information like the endpoint's hostname, machine identifier, and its activation state.

## Get GSM-level Summary Report of DNSP Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/dnsp`

Required Scope SkyStatus.Reporting - Returns a GSM-level summary report of DNSP usage for a GSM master keycode. Besides general information like the console name and type of GSM license the report includes the total number of sites and devices.

## Get Site-level Summary Report of DNSP Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites/dnsp`

Required Scope SkyStatus.Reporting - Returns a site-level summary report of DNSP usage for a GSM master keycode. For each site the report includes information like the site name and license type as well as the total number of devices.

## Get Site-level Summary Report of DNSP Usage by Site Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites/{keyCode}/dnsp`

Required Scope SkyStatus.Reporting - Returns a site-level summary report of DNSP usage for a GSM master keycode by a site keycode. The report includes information like the site name and license type as well as the total number of devices.

## Get GSM-level Summary Report of WSAT Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/wsat`

Required Scope SkyStatus.Reporting - Returns a GSM-level summary report of WSAT usage for a GSM master keycode. Besides general information like the console name and type of GSM license the report includes the total number of sites and users.

## Get Site-level Summary Report of WSAT Usage

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites/wsat`

Required Scope SkyStatus.Reporting - Returns a site-level summary report of WSAT usage for a GSM master keycode. For each site the report includes information like the site name and license type as well as the total number of users.

## Get Site-level Summary Report of WSAT Usage by Site Keycode

<mark style="color:blue;">`GET`</mark> `unityapi.webrootcloudav.com/service/api/status/reporting/gsm/{gsmKey}/sites/{keyCode}/wsat`

Required Scope SkyStatus.Reporting - Returns a site-level summary report of WSAT usage for a GSM master keycode by a site keycode. The report includes information like the site name and license type as well as the total number of users.
