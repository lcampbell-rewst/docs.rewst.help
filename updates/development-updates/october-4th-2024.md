# October 4th, 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added the ability to use Org variables in Trigger Criteria
* Added a List Forms action with granular permissions

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Prevent copy/pasting of subworkflows between orgs that contain actions that don't exist in the target org
* Fixed column pinning for DataTables in App Platform
* Fixed a problem with List Workflow Executions With Time Savings action to require the updated_at field to bound the time savings portion of the query.
* Auto-focus the search bar for New Org Picker
* Fixed routing for custom page names that start with reserved routes in App Platform
* Automatically set the value on forms dropdown when users type to search preventing the need to click the item
* Fixed the App Platform `View` permission to include site themes
* Fixed frontend crashing on certain Github integration actions
* Added feature flag checks for multiplayer workflows
* Fixed falsey boolean handling and make it more consistent with user expectations
* Surface errors in webhook trigger tester that would cause a workflow to not start unrelated to the filters such as invalid request origin
* Prevent workflow canvas from freezing when searching for Actions
* Fix Core Send Mail action to allow input in full email addresses
* Updated pagination for DNSFilter to fetch up to 20k results
* Added missing enum import for forms to validate server side checks that were causing errors when loading embedded forms
* Fixed a bug with Rewst Get Template action failing when a template was selected from the dropdown instead of using the template id
* Fixed handling of required fields in Custom Integrations V2
* Added View permission on forms to allow showing form links to those users
* Removed `span` tag from jinja rendering in App Platform html components
* Updated DNS Filter logo and setup instructions
* Fixed a bug with generic HTTP requests to account for null header parameter
* Fixed permission settings page to show the display name of custom roles instead of the ID
* Fixed enum entry for Custom Integrations V2
* Prefill crate description using a template to avoid empty crate descriptions
* Made `Domain` a required field for SynnexAU
* Improved OpenAI parsing for Custom Integrations V2
* Made Trigger Type immutable
* Fixed a bug where form submissions were not checking if the underlying trigger was disabled
* Fixed a bug where soft-deleted orgs were still being included in workflow triggers
* Fixed padding for dynamic dropdowns on Forms to be consistent with static dropdowns
* Improved validation error messages on permission configurations where at least one role and one org are required
* Fixed a broken setup link for KaseyaBMS
* Set the default managing org_id to the current org_id when creating a new org
* Fixed a bug with MS CSP client mapping in the re-auth logic to refresh Azure tokens
* Fixed a bug where default integrations were not being automatically added to new orgs
* Fixed bugs with new OpenAPI parser in Custom Integrations V2
* Added authorization token refresh functionality to Custom Integrations V2
* Fixed a bug where the List Organizations action was timing out for orgs that manage a large number of orgs

</details>

<details>

<summary><strong>Deployed behind feature flags awaiting QA review and feedback</strong></summary>

* New Org Picker (Launching soon)
* Bitdefender integration (QA review)
* Granular forms permissions (QA review)
* IT Portal integration (QA review)
* Synnex Australia integration (QA review)
* Cove integration (QA review)
* Github integration (QA Review)
* Multi-player workflows V1 (Enabled for staff review)

</details>

<details>

<summary><strong>In code review and development</strong></summary>

* Crushbank integration (Code review)
* Nodeware integration (Code review)
* SQL Database integration refactor (Code review)
* JSON RPC Base Client (Code review)
* Webroot Triggers (Code review)

</details>
