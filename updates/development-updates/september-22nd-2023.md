# September 22nd 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added shallow cloning to templates and scripts
* Added org mapping for Crowdstrike accounts for MSSPs
* Added support for non-standard oAuth implementations to the custom integration
* Added a checkbox on forms for dynamic options to allow setting fields to always skip caching

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Lazy load org\_variables in the engine to resolve issues with workflows that have large or a large number of org\_vars
* Added Microsoft Graph permissions to be able to access retention events and sharepoint
* Fixed some problems with the OpenAI integration when using Azure hosting for the chate completions endpoint
* Updated the core Mock action to always be shown as "mocked" in the workflow builder
* Adjusted timeout for ConnectWise Control Invoke Command action to use the max task timeout instead of 60 seconds
* Replaced out dated verbage from User Invites to Authorized Users
* Prevent sending batch requests to kafka that are larger than the kafka max\_request setting
* Enabled multi-tenancy for Auvik, Sonicwall, and Sophos
* Increased max workflow timeout from 7 days to 30 days

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Highlight connected tasks when hovering on arrow connectors
* Updates to the Jinja live editor tool to allow for multiple tabs and a better UX
* Implement Istio in Kubernetes cluster to allow for better observability and control of network traffic
* Improvements to workflow builder UI when viewing workflows that are synced clones or installed via a crate
* Liongard integration
* Godaddy integration

</details>
