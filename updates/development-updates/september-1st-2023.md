# September 1st 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* No new features this week. Stay tuned for upcoming releases!

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Optimize query for a user organization that gets run on every request to improve application performance
* Removed an unnecessary serialization call when processing finished workflow tasks to improve application performance
* Improved the performance of our CI/CD pipeline reducing the amount of time to test and build the project from 20+ minutes to 2 minutes
* Fixed SentinelOne Create Site action where parameters were not being passed correctly
* Fixed ConnectSecure Get Agent Secrets action where the company\_id was not being passed to the JSON body
* Fixed NinjaRMM to properly handle plain text error responses
* Updated the redis connection pool to prevent errors due to connections disconnecting on idle timeout
* Added an option to ConnectWise Automate Schedule Script action to allow skipping of offline agents

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Refactor ConnectWise Manage integration
* Fix the Jinja editor value not updating when the underlying field is edited directly
* Add tagging for forms
* Add a filter to Acronis to allow users to restrict the number of orgs that get returned for org mapping
* Liongard integration
* GoDaddy integration
* Improvements to workflow builder UI when viewing workflows that are synced clones or installed via a crate

</details>
