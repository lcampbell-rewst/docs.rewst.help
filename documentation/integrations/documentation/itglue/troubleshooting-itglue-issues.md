# Troubleshooting IT Glue Issues

***

## Forbidden Errors

If you've selected `Allow specific IP addresses` in IT Glue rather than `Allow access from all IP addresses`, you will need to add the [#rewst-outgoing-ip-address](../../../../security/security-policy.md#rewst-outgoing-ip-address "mention") into the `IP Access Control` within IT Glue.

Here's how you can do it:

1. Navigate to the IP Access Control settings within IT Glue.
2. Add [Rewst's IP address](../../../../security/security-policy.md#rewst-outgoing-ip-address) to the list of allowed IP addresses.

<figure><img src="../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

After adding Rewst's IP address, the forbidden error should be resolved and you should be able to successfully set up the IT Glue integration.

***

## Password Access

Rewst requires the "Password Access" checkbox to be enabled on the API Keys screen in ITGlue Account Settings.

<figure><img src="../../../../.gitbook/assets/it-glue-least-privledged-access.png" alt=""><figcaption></figcaption></figure>

For more information, check out the [IT Glue documentation](https://api.itglue.com/developer/).
