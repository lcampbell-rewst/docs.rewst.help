---
description: >-
  Link an external reference to a workflow execution with an identifier and
  reference ID. Retrieve details later by specifying parameters. Choose user and
  set failure conditions for pre-existing links.
---

# Foreign Object References

## Overview

Effectively managing and keeping track of external resources for use within workflows can significantly improve automation efficiency. This page covers how to link external references to your workflow's executions using Rewst's `Associate External Object` and `Get External Reference` actions, and how to use them to simplify your processes, and ensure better visibility of your workflow executions.

### Why This Is Useful:

* **Improves Accessibility:** Makes it easy to find and use relevant information when needed.
* **Streamlines Processes:** Reduces complexity in linking external data to workflows.
* **Saves Time:** Eliminates the need to gather the same data repeatedly.
* **Tracks Progress:** Can provide a clear reference point for ongoing tasks and projects.

***

## Associate External Object

Linking external resources, like tickets from a PSA system, to your workflow executions can streamline management and enhance traceability. This section walks through the steps to associate an external object within your workflow executions.

### **Key Points:**

* **Association:** Connects an external system's resource to your workflow.
* **Conflict Handling:** Optionally fails if a pre-existing link is detected.
* **User Execution:** Runs under specified user or default user.

### **Parameters:**

* **identifier:** Unique identifier of the external resource you'd like to associate.
* **reference\_id:** Reference for the external resource that you will be able to call back on.
* **run\_as\_user (optional):** Defined user's ID or default user's ID (if blank) for running the task.
* **fail\_on\_conflict (optional):** Set this option to true if you don't want to overwrite any existing `reference_id`/`identifier` pair already exists.

### **Output**

The resulting task's output returns the verified information about the associated external object.

***

## Get External Reference

Facilitates the retrieval of details about the any external integration or manually set references. You can use it to fetch all external integration references associated with a specific organization in Rewst or to find the organization and workflow execution associated with a specific external reference ID.

### **Key Points:**

* **Retrieval:** Fetches external resource information.
* **User Execution:** Runs under specified user credentials or default user.
* **Organization Specific:** Requires organization ID for context.

### **Parameters**

* **org\_id:** ID of the organization in Rewst.
* **identifier:** Unique identifier of the external resource.
* **reference\_id:** Reference ID of the external resource.
* **run\_as\_user (optional):** Specify user credentials.

### **Output**

Returns detailed information about the external reference(s), such as the `org_id` in Rewst linked to it, the type of `identifier`, and the external `reference_id`. This information is helpful for cross-system data synchronization and management.

***

{% hint style="info" %}
Check out the documentation for the[view-rewst-integration-org-variables.md](../../../../prebuilt-automations/existing-crate-documentation/view-rewst-integration-org-variables.md "mention") crate, to see a practical example of how to leverage this action within your Rewst workflows.
{% endhint %}
