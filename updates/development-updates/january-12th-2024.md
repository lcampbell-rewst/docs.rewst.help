# January 12th 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* SentinelOne integration refactor
* New actions for ConnectWise Automate for various endpoints, including: Computers, Contacts, Extrafields, Groups, NetworkDevices, RemoteAgent, Searches, and System
* Added high level components to App Platform
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Added Microsoft Graph permission for Teamwork Tags
* Fix intermittent page crashes on App Platform page list screen
* Fixed a bug in App Platform where it wasn't possible to make an image a link
* Fixed a bug in the Users list where duplicates were being shown due to case sensitivity
* Removed the "home" and "login" check boxes from pages in App Platform in favor of them being default pages
* Refactored the html container for App Platform to use an iframe and allow for javascript to be run
* Fixed a bug with Immybot configuration that was throwing a 500 error during configuration
* Fixed a documentation link for Immybot
* Fixed a bug with the Exports action in IT Glue
* Added Remove-DistributionGroup cmdlet to Microsoft Exchange integration

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Fix a bug with refreshing OAuth2 tokens for custom integration
* Workflow normalization v1
* Support for custom error pages in App Platform, like 404
* Refactor Microsoft integration configuration setup to improve UX and offer a better permission system
* Improved Time Saved functionality with Task level Time Saved and persistence beyond workflow execution retention. (Pull request open for the backend)
* Bug fixes for App Platform

</details>
