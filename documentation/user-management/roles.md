# Roles

There are three different roles available when adding a user:

1. Admin
2. Member
3. Forms

Let's take a look at how these are defined.

{% hint style="warning" %}
_Disclaimer: This article will be updated as Role functionality will be added over time_
{% endhint %}

### Admin

The Admin role is for the super user that will have access to everything in their organization. They can do things like:

* Add and remove Users
* Add user Roles
* View, edit, and build workflows
* Check Results
* Add, edit, and configure forms
* Manage integrations and organization variables
* Etc

At the top level organization, an Admin will be able to see all of the customer organizations and manage information there. At the customer level, An Admin will be able to access the same information for the customer organization.

### Member

The only way the Member role differs from the Admin role at this time is in that a Member cannot change user roles while an Admin can. Further changes will be made soon so that the Member Role will not be able to do things such as adding or editing users and organizations.

### Forms

The primary use case for this permission level is to provide customers or internal employees with a way to fill out forms. A user with the Forms Role will only have access to form URLs that are provided to them by an Admin or Member. This means they will not have access to the platform itself and only have the ability to view and fill out different forms for the organization or customer they're added to. This means anyone added at a customer level will only have access to forms for that customer, while a user added at the top-level organization would have access to forms from any customer organization and the top-level organization itself.
