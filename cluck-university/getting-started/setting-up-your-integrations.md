# Setting Up Your Integrations

{% embed url="https://youtu.be/9PFwvfPARbU" %}

## Integrating and Automating with Rewst

### Key Integrations to Prioritize

To get started, we recommend prioritizing a few critical MSP integrations:

1. **Microsoft Bundle**: This includes essential integrations like CSP, Graph, and Exchange Online.
2. **PSA (Also known as a Ticketing System)**: Essential for managing your service delivery.
3. **RMM (Remote Monitoring and Management)**: Monitors and manages your IT infrastructure.
4. **Documentation Platform**: Centralizes your documentation for easy access and management.

## Setting Up Integrations

Follow these steps to set up your integrations:&#x20;

1. **Access Configurations**:
   * **Navigate** to _Configurations_ → _Integrations_.
   * You'll find a list of core system integrations already set up by default.
2. **Install New Integrations**:
   * **Search** for the integration by name and click on it.
   * This will take you to the configuration page. Always refer to the corresponding help documents to ensure the correct setup.
3. **Configure Permissions**:
   * For integrations like RMM, you might need to install a component or script.
   * For the Microsoft cloud integration bundle, select the desired integrations and configure the authentication settings. You can use the Rewst Microsoft cloud connector for dynamic permission management or set up custom permissions as needed.
4. **Authorize Integrations**:
   * **Set** the required permissions and authorize all integrations with a single click.
   * You’ll be prompted to log in, and once authorized, you'll see a summary of your integrations, including the user who authorized them and the associated tenant ID.

{% hint style="success" %}
Check out our [microsoft-cloud-integration-bundle](../../documentation/integrations/cloud/microsoft-cloud-integration-bundle/ "mention")and [integrations](../../documentation/integrations/ "mention") pages for more information on each integration.&#x20;
{% endhint %}

## Custom Integrations

If you need to integrate software that isn't pre-configured in Rewst:

1. **Enable Custom Integrations**:
   * Go to **Settings** and select **Feature Preview**.
   * Enable **Custom Integrations**. If already enabled, it will be marked as such.
2. **Set Up Custom Integrations**:
   * Use the API to connect any product not already integrated with Rewst.
   * Install and configure as many custom integrations as needed.

#### Conclusion

Configuring your Rewst integrations is straightforward and paves the way for powerful automation capabilities. Watch the video below for a step-by-step visual guide to setting up and managing your integrations.
