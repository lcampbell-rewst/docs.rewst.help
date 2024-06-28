# Custom Integrations

## Introduction&#x20;

Custom Integrations allow Rewst users to build their own integrations tailored specifically to their organization's needs. By using Custom Integrations, users can integrate their workflows with any service that exposes an API, enhancing automation and efficiency within their operations.&#x20;

## Why Use Custom Integrations?&#x20;

* **Flexibility:** Build integrations that are perfectly tailored to your unique automations requirements.&#x20;
* **Compatibility:** Supports both modern and legacy APIs by accepting Swagger, [OpenAPI specifications](https://www.openapis.org/), or building your own integration from scratch.&#x20;
* **Ease of Use:** Automatically generate actions from API definitions, which can be used in workflows without manual coding.&#x20;
* **Visibility Control:** Manage who in your organization or in sub-organizations can see and use the integrations.&#x20;
* **Lifecycle Management:** Easily manage the lifecycle of your integrations with statuses like draft, published, deprecated, and hidden.&#x20;

## How to Use Custom Integrations&#x20;

To understand how to create a Custom Integration in Rewst, check out the walkthrough on the page for more information.

{% tabs %}
{% tab title="Supported Authorization Schemas" %}
* None&#x20;
* API key&#x20;
* Basic authorization&#x20;
* OAuth 2.0 with the following grant types&#x20;
* Client Credentials&#x20;
* Authorization code&#x20;
* No grant type&#x20;
{% endtab %}

{% tab title="Supported pagination schemas" %}
* None&#x20;
* Index&#x20;
* Page&#x20;
* Link&#x20;
* Pointer &#x20;
{% endtab %}
{% endtabs %}

## Editing and Managing Integrations&#x20;

Once an integration is created, you can edit it by navigating to the integration's detail page. Here, you can:&#x20;

* Change the visibility status of the integration (Hidden or Published).&#x20;
* Modify existing actions or add new actions or mark them as deprecated.&#x20;
* Delete the integration (Note: The integration must be uninstalled from all sub-organizations first).&#x20;

## Using Custom Integrations in Workflows&#x20;

After creating and configuring your integration, you can use it in workflows by adding actions from your custom integration to the workflow. &#x20;
