---
description: >-
  The Network Security Manager pack allows you to interface with your SonicWall
  firewalls and more!
---

# SonicWall Integration Setup

{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

## Setup

To allow access to the SonicWall NSM Integration, you will need to contact the SonicWall Integration Support Team for an API token: [Pre-written Request Template](mailto:thirdpartyintegrations@sonicwall.com?subject=API%20Token%20for%20Rewst%20API%20Request%20-%20%5BYOUR\_TENANT\_NAME%5D\&body=Hello!%0D%0A%0D%0AI%20would%20like%20to%20enable%20the%20Rewst%20Integration%20for%20SonicWall%20NSM.%20To%20do%20so%2C%20I%20would%20like%20to%20request%20an%20API%20Token%20for%20the%20following%20Tenant%20and%20User.%0D%0A%0D%0AMySonicWall%20Username%3A%0D%0AMySonicWall%20Tenant\(s\)%3A%0D%0A%0D%0APlease%20let%20me%20know%20if%20any%20additional%20information%20is%20required.%0D%0A%0D%0AThank%20you%2C%0D%0A%0D%0A%5BYOUR%20NAME%5D)

To: `thirdpartyintegrations@sonicwall.com`

```
Hello!

I would like to enable the Rewst Integration for SonicWall NSM. To do so, I would like to request an API Token for the following Tenant and User.

MySonicWall Username:
MySonicWall Tenant(s):

Please let me know if any additional information is required.

Thank you,

[YOUR NAME]
```

Once the token is received:

1. **Go to** the SonicWall NSM integration page in [Rewst](https://app.rewst.io/).
2. **Enter** the API key.
3. **Enter** your NSM Region (the domain for the SonicWall NSM portal you log into).
4. **Save** the configuration.

Example of NSM regions:

* [https://nsm-uswest.sonicwall.com](https://nsm-uswest.sonicwall.com)
* [https://nsm-eucentral.sonicwall.com](https://nsm-eucentral.sonicwall.com)

### Actions

| Action                     | Description                                                                |
| -------------------------- | -------------------------------------------------------------------------- |
| Get Pod Connections        | Gets connections that a pod is using                                       |
| List Device Groups         | Lists the device groups associated with your tenant                        |
| List Firewalls             | Lists all the firewalls associated with your NSM account                   |
| Get Firewall Info          | Gets a firewall associated with your NSM account                           |
| Get License for Device     | Gets a firewall's license                                                  |
| Get Firewall's Connections | Gets connections that a device is using                                    |
| SonicWall NSM API Request  | Generic action for making authenticated requests against the SonicWall API |
