# Troubleshoot API Issues from ConnectWise Logs

## Overview

This guide outlines the steps for Rewst users to pull API logs from ConnectWise Manage. These logs are crucial for troubleshooting and optimizing the Rewst integration with ConnectWise.

## Prerequisites

* Access to ConnectWise Manage with appropriate permissions.
* Familiarity with navigating the ConnectWise Manage system.
* Confirm that your Rewst account is [correctly integrated with ConnectWise](connectwise-integration-setup.md).

***

## Step by Step Walkthrough

### Step 1: Log into ConnectWise Manage & Navigate to System Settings

* **Login** to ConnectWise
* **Navigate** to `System` > `Members`
* **Click** `API Members`

Here, you'll find settings specific to API interactions and configurations.

<figure><img src="../../../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

***

### Step 2: Select the Rewst user

Under the API Members tab, locate and select the user associated with Rewst's integration.

<figure><img src="../../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

***

### **Step 3: Open the API Logs Tab**

After selecting the Rewst user:

* **Navigate** to the `API Logs` tab.
  * This tab contains logs of all API interactions made by the user.
* **Click** on the `Start Debug Mode` hyperlink.
  * This action opens the `Start Debug Mode` pop-up

<figure><img src="../../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

***

### Step 4: Set Debug Duration

In the Debug Mode pop-up:

* **Enter** length of time (e.g. `5`) in the `Minutes` textbox. This will capture logs for the specified duration.
* **Click** the `Ok` button to start the debug mode.

<figure><img src="../../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

***

### Step 5: Replicate the Issue & Troubleshoot

* **Replicate** the issue or process you are troubleshooting
* **Return** to the API Logs tab.
* **Click** on the `Download Logs` hyperlink.&#x20;

Once downloaded, you can review these logs, and provide to the ROC for troubleshooting assistance.

***

## Conclusion

By following these steps, Rewst users can efficiently pull API logs from ConnectWise Manage, aiding in effective troubleshooting and optimization of the Rewst-ConnectWise integration.
