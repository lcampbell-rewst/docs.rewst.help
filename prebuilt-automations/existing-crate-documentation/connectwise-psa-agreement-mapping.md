---
description: >-
  Synchronizes Users into Connectwise Manage Agreement Additions by License,
  Department, or Group membership.
---

# Connectwise PSA Agreement Mapping

## Introduction

For MSPs doing user-based billing agreements, this crate allows a user to map user groupings to those agreements to facilitate automated billing reconciliation based on a selection of criteria.&#x20;

To make the automation mechanism flexible, users can be categorized according to either EntraAD (AzureAD) Group Membership, Assigned Licenses, or their Department fields.&#x20;

Based on the user categorization, these can be mapped to existing "Additions" in the Agreements to populate the Quantity field for those Additions.&#x20;

In addition to populating the Quantity, the sync process can also fill the user names into the description field for each addition for customer review.

## Configuration

After installing the crate, a form named **Map ConnectWise Manage Agreement Additions** will be installed.&#x20;

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

This form is used to maintain "mappings" between the environments and the PSA Agreements. These are stored in Organizational Variables in Rewst based on the form inputs.&#x20;

From the MSP organization, use this form to Add, Modify, or Remove a mapping configuration. When Adding or Modifying a Mapping, you will make the following choices:

* **Customer**: This will be from the list of PSA clients
* **Agreement**: PSA Agreement which we will be mapping users to
* **Line Item**: Also known as the Agreement Addition, this is the item which will have its quantity determined by the collection process
* **Mapping Type**:
  * **Group**: Choose this to map users according to membership within an EntraAD Group
  * **License**: Use this to map the users according to a Microsoft 365 License that is applied to them
  * **Department**: This will utilize the "Department" field as it is filled in users' EntraAD properties
* Depending on the mapping type, you will be presented with a field to choose between the options that are available in the specific customer's environment to map users by (Group, License, or Department)
* **Sync User Names into Description**: If you enable this, the actual names of the users will be put into the Description field of each Addition
* **Split User Names by**: This will allow you to choose between "Comma" and "New Line" to fine-tune how the list of users appears on the invoice. Commas will use fewer lines when you have many users, but New Line may be easier to read.

## Operation

A workflow with a Cron (time-based) trigger will run daily to sync users for each company that has been mapped.&#x20;

For each customer agreement that has a mapping set for it, it will query the users with the intended attributes using Microsoft Graph (Group, Licenses, or Department), collect quantities and details, and add those to the PSA Agreement Additions. If there are any errors, they will be sent via email to the individual who created the mapping so they can troubleshoot.&#x20;

## Caveats

* Department fields are free-form text. If you aren't automating the filling-in of these, there is always the chance that spellings or formatting may vary, resulting in incomplete data.
* The Description field in PSA Agreement Additions is limited to about 6000 characters. Large sets of users can easily exceed that maximum and usernames won't appear in the Addition. When this happens, an email will be sent to the person who created the mapping to let them know that this is the case.&#x20;
