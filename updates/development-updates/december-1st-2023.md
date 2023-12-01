# December 1st 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Allow duplicate org names
* Added a trigger for new tickets in Kaseya BMS
* Added headers to Datto PSA requests to allow impersonation on Rewst actions
* App platform workflow builder UX enhancements
* App platform charts and graphs
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed a problem where errors during a clone sync could cause a cascading failure scenario
* Fixed a bug with Datto PSA actions using billCodeID and changeInfoField2 fields
* Strip Content-Type header for Sophos generic action requets that don't contain a body to prevent error
* Added null checks to the Monaco editor to prevent intermittent page crashes when editing markdown fields on forms
* Normalized the database schema for App Platform
* Fixed a problem where the org picker wasn't loading immediately
* Fixed a bug with PUT requests for Ninja RMM
* Switched org hierarchy SQL functions to use a materialized view to improve performance for auth checks
* Fixed bugs with jinja parsing in html on App Platform pages
* Fixed a bug where Get Audit Trail action for Connectwise PSA wasn't paginating
* Fixed a bug where hubspot triggers were not respecting the trigger criteria
* Fixed a bug causing the frontend to crash on the forms builder when setting a condition on options generated dropdown


</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Continue work on App Platform to get ready for users
* Continue work on platform performance and stability

</details>
