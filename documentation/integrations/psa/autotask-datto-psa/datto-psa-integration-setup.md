---
description: This document outlines the requirements and setup for the Datto integration.
---

# Autotask Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

### Setting up the API account

Before configuring the Rewst integration you must generate an API user.

Please refer to [Datto's documentation](https://helpdesk.kaseya.com/hc/en-gb/articles/4407245633169-Create-an-API-User-in-Datto-PSA-Autotask) for generating API credentials for your organization if you have not already. Part of this process will include the generation/assignment of a tracking identifier. Information about tracking identifiers can be found [here](https://www.autotask.net/help/Content/4\_Admin/1CompanySettings\_Users/ResourcesUsersHR/Resources/API\_Tracking\_Identifier.htm).

### Configuring the Integration

Once you have created an API account, you will need to configure the integration within the Rewst platform. Follow the below steps to configure a new integration:

1. **Log in** to the [Rewst platform](https://app.rewst.io/).
2. **Go to** the _Configuration_ → _Integrations_ in the left sidebar.
3. **Click** on or search for _Datto PSA_.
4. **Complete** the form with the details you created:
   1. **Platform**: The zone associated with your Datto account
   2. **API User Password**: This is the API password created during the API user creation process.
   3. **API Username**: This is the API username created during the API user creation process.
   4. **API Tracking Identifier**: The generated tracking number for this application
5. **Save** the configuration. Rewst will do a quick validation of your input.

#### Company Filter

1. **Filter**: Select what you would like filtered from the dropdown.
2. **Operation**: Choose which Operation you would like to use.
3. **Value**: This must be an integer "Example for Company Below".

{% hint style="info" %}
**Accepted Company Type Values**

Ensure you enter the number for the company type you would like to filter on.

```
1 = Customer
2 = Lead
3 = Prospect
4 = Dead
5 = Cancelation
6 = Vendor
7 = Partner
```
{% endhint %}

Beneath that integration authentication section you will see the following options:

1. **Suggest Values**: This option will attempt to generate mappings between Rewst organizations and child organizations in this integration.
2. **Refresh Options**: This will re-read the potential mapping options - for both organizations and companies in Datto.
3. **Save Mappings**: This will apply mapping configuration changes.
