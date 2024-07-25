# Kaseya VSA Integration Setup



{% hint style="success" %}
**This Integration supports multiple instances**

[Check out the instructions to set up multiple instances here](../../general/multi-instance-integration/multi-instance-integration-setup.md).
{% endhint %}

{% hint style="warning" %}
If you are planning to upgrade from Kaseya VSA to Kaseya VSA X, for Rewst functionality purposes we recommend waiting until Kaseya VSA X is available in the following crates:

* Rewst: User Onboarding
* Rewst: User Offboarding v2
* Configure Organizational Variables
* Organizational Setup Report
* Add Client to Rewst (form)

This functionality should be available in August 2024.
{% endhint %}

## OAuth Account Setup

1. **Log in** to Rewst and go to Integrations select Kaseya.
2. **Copy** the Call back URL to the clipboard.
3. **Log in** to Kaseya.
4. **Click** on System → Server Management → OAuth Clients.
5. **Select** Register Client and supply the following:
   * Client Name (RewstAPI)
   * Redirect URL (From Rewst Kaseya integration page)
   * Email (`email@address.com`)
6. **Click** Save.
7. **Copy** the information from the pop-up to your clipboard.
8. **Return** to the Kaseya integration page and enter the values:
   * Hostname: (ie rmm.company.com)
   * Client ID: (From Kaseya OAuth page)
   * Client Secret: (From Kaseya OAuth page)
9. **Click** Save.

If your setup was successful you should see a confirmation.

If your VSA is behind a firewall, WAF has IIS Re-write rules, or has the Kaseya edge firewall configuration in place you will need to add `3.139.170.31` to the allowed list (tcp/443).

## Rewst Agent Procedure Import

To perform actions on agent end points in Rewst you will need to import the file Procedure RewstPoshCommand.xml into the VSA.

{% hint style="warning" %}
**It is important that you do not change or modify this file in any way**.
{% endhint %}

Please do not rename the procedure once imported.

1. **Download** the file Procedure Rewst (Powershell).xml.

{% file src="../../../../.gitbook/assets/Procedure Rewst (Powershell).xml" %}

2. **Log in** to your VSA.
3. **Go to** System → Server Management → Import Center.
4. **Select** New Import.
5. **Name** it _Rewst (Powershell)_, and point it to the _Procedure Rewst (Powershell).xml_ file.
6. **Click** Process.
7. **Click** Save.
