# Users & Invitation Actions

## **List Users by Organization**

**Description**: Get user list and optionally invited users by your organization in Rewst.

**Parameters**:

* **Include User Invites?:** Whether or not to include user invites in the results.
* **Which Invites:** Which invitees to include. Can be `all`, `accepted`, or `pending`.

**Output**: A list of users with details like ID, role, organization ID, assigned role IDs, username, and a boolean indicating superuser status.

***

## **Get User**

**Description:** Get user by email or ID in Rewst.

**Parameters:**

* **ID:** The ID of a user in Rewst.
* **Organization ID:** The ID of an organization in Rewst.
* **Email address:** The email of a user in Rewst.

**Output:** The returned object includes the user's details like ID, role, organization ID, assigned role IDs, username, and a boolean indicating superuser status.

***

## **List User Invites to Rewst**

**Description:** Get user invite list by your organization in Rewst.

**Parameters:** _No parameters needed for this action._

**Output:** The returned list includes a list of user invite objects. Each object contains the invite's ID, email, organization ID, assigned role IDs, a boolean indicating acceptance status, and the ID of the inviter.

***

## **Invite User to Rewst**

**Description:** Invite a user to your organization in Rewst.

**Parameters:**

* **Email:** Email address of the user to invite.
* **Roles:** Role IDs to assign to user.

**Output:** The returned object includes the invite details such as ID, email, organization ID, assigned role IDs, a boolean indicating acceptance status, and the ID of the inviter.

***

## **Delete User Invite**

**Description:** Delete a user invite from your organization in Rewst.

**Parameters:**

* **Email:** Email address of the user invite to delete.

**Output:** The returned object shows the number of invites deleted.
