# February 2nd 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Deployed a new integration for Nerdio
* Added an Override Option flag to the option generator field on forms
* Added a combine filter to Jinja to allow merging of dictionaries
* Removed the Microsoft Tennant ID restriction from user invites. You can now invite any business email address to your organization.
* Added default fallback page for App Platform on routing failures
* Added new Jinja filters for various types of hashing
* Expose post trigger save mutation errors in the UI
* Added new IT Glue actions for Related Items
* Added a new Auvik region: US 5
* Added categorization tags to the Auvik integration
* Added support for `application/json` in `oauth_token_request_content_type` for Custom Integrations
* Added Get Metrics V2 action to Liongard
* Added workflow diff view to the publish modal on the workflow builder
* Workflow normalization part 1
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed User Defined Fields for Datto PSA webhooks
* Fixed a bug with updating the default home page in app platform
* Fixed a number of page navigation issues with links and the sidebar in app platform
* Fixed the `quantity` parameter for subscriptions action in the Synnex integration
* Fixed a bug where the `SUCCEEDED` and `FAILED` keywords were not being properly evaluated in jinja
* Fixed a bug where searching in an autocomplete field was not returning correct results
* Fixed a problem where ConnectWise Automate New Computer trigger wasn't updating the last search date in the database causing it to miss new computers
* Fixed the results key for SentinelOne Sites actions
* Fixed a bug where Re-run Workflow was not including trigger data
* Fixed incorrect icon display on the nav bar
* Prevent components getting caught in a render loop on App Platform
* Fixed a bug in App Platform where multiple WorkflowInput values were not being passed to triggered workflows
* Fixed Datto PSA Contact v2 action to have the correct data type for the `isActive` field
* Renamed the Nable integration
* Fixed pagination for the Hubspot generic api action
* Fixed a bug with the Pax8 Cancel Subscription action where the wrong data type was being used for a path parameter
* Fixed a bug with Crate unpacking by preventing null triggers from being passed in overrides
* Fixed a bug where redis connections were being disconnected prior to being removed from the connection pool
* Fixed IT Glue actions for Flexible Asset Fields
* Hide the workflow input section on forms when there are no inputs
* Added Remove-MailboxFolderPermission to the Microsoft Exchange integration
* Added error boundaries to datatable so the page doesn't crash when a datatable has an error in App Platform
* Prevent clone syncing error due to null clone_overrides
* Fixed a number of problems with data tables and column generation in App Platform
* Added custom integrations to the `reauth-integrations` cron job so credentials are kept active
* Fixed inconsistent trigger output rendering in App Platform
* Fixed a bug with saving workflows to commponents in App Platform
* Refactored Jinja rendering in App Platform

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Custom integrations v2
* Microsoft refactor to allow for better permission system
* Workflow version control
* Jinja live editor immprovements

</details>
