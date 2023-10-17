# Actions & Endpoints

## Actions & Endpoints

### Introduction

The Liongard Integration with Rewst delivers a robust set of actions and endpoints for interacting with Liongard. Below is a summary of each section, highlighting the diverse capabilities and opportunities provided through the Liongard Integration:

* **Generic Request**
* **V2 Environments**
* **V2 Metrics**

### Actions

#### Generic Request

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/<url_path>" method="get/put/post/delete" summary="Liongard API Request" %}
{% swagger-description %}
Generic action for making authenticated requests against the Liongard API
{% endswagger-description %}
{% endswagger %}

#### V2 Environments

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/" method="get" summary="List Environments (V2)" %}
{% swagger-description %}
Retrieve a list of environments. You can specify the page size, columns to include, and the order of the response
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/" method="post" summary="Add Environment (V2)" %}
{% swagger-description %}
API endpoint to add a new environment. The endpoint requires a JSON body containing the label for the environment
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/" method="put" summary="Update Environments in Bulk (V2)" %}
{% swagger-description %}
Update multiple environments using the Liongard API
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/bulk" method="post" summary="Add Environments in Bulk (V2)" %}
{% swagger-description %}
Add multiple environments by making a POST request to the /environments/bulk endpoint with a JSON body containing the necessary information
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/{environmentId}" method="delete" summary="Delete Environment (V2)" %}
{% swagger-description %}
Delete an environment by its ID
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/{environmentId}" method="get" summary="Get Environment (V2)" %}
{% swagger-description %}
Get a single environment by providing the environmentId as a path parameter
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/{environmentId}" method="put" summary="Update Environment (V2)" %}
{% swagger-description %}
Update a single environment by providing the environment ID and the updated JSON body
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/environments/{environmentId}/relatedEntities" method="get" summary="Get Related Entities Per Environment (V2)" %}
{% swagger-description %}
Returns all the Related Entities that are tied to a single Environment such as Agents, Launchpoints, and Integration mappings
{% endswagger-description %}
{% endswagger %}

#### V2 Metrics

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/metrics" method="get" summary="List Metrics (V2)" %}
{% swagger-description %}
Returns a list of metrics that have been created.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/metrics/evaluate" method="post" summary="Get Metric Values (V2)" %}
{% swagger-description %}
Get Metric values for systems using Metric ID/UUID(s). Max 100 requests/min per user. No need for filters/sorting, but include an empty array in the request.
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/metrics/evaluate/systems" method="post" summary="Get Metric Enabled Values (V2)" %}
{% swagger-description %}
Returns Metric values for all Enabled Metrics for a given System ID, Metrics must have "display" set to enabled to show in the response
{% endswagger-description %}
{% endswagger %}

{% swagger baseUrl="https://companyABC.app.liongard.com" path="/api/v2/metrics/{MetricID}/relatedEnvironments" method="get" summary="Get Related Environments (V2)" %}
{% swagger-description %}
Returns Environment IDs for all related Environments for a given Metric ID
{% endswagger-description %}
{% endswagger %}
