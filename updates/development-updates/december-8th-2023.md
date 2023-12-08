# December 8th 2023

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added the ability to send additional headers to Microsoft Graph List Users action
* Updated the default page users are presented when a new page is created in App Platform
 
</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Added internal DNS routing for the engine and graph-api to kubernetes so requests between those systems never leave the cluster
* Replaced a slow redis KEYs command by using SETs instead resolving connection timeouts to that system when underload and improving performance
* Fixed an issue with saving workflows to components in App Platform
* Migrate redis clients from an outdated implementation to the officially supported python client
* Updated max pages being returned for ITGlue

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Continue work on App Platform to get ready for users
* Continue work on platform performance and stability

</details>
