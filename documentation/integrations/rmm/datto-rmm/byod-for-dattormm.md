---
description: Using BYOD to Address DattoRMM's Data Retrieval Slowness
---

# BYOD For DattoRMM

{% hint style="warning" %}
For the BYOD integration to function correctly with DattoRMM, it is essential that the **`Database Config Name`** is set exactly as **`Rewst Cache - Database`**. Failure to do so will result in caching issues, affecting data retrieval performance.
{% endhint %}

### Overview

DattoRMM customers occasionally face challenges with the speed at which data is returned from DattoRMM's APIs. One efficient workaround is to leverage the Bring Your Own Database (BYOD) integration. This document provides specialized steps for integrating BYOD with DattoRMM to address these speed issues.

{% hint style="info" %}
To setup your BYOD Integration, refer to the [Database Integration Setup](../../database/database-integration-setup.md) page.
{% endhint %}

### Purpose of Using BYOD with DattoRMM

The aim of integrating BYOD with DattoRMM is to streamline data retrieval and bypass potential lags or slow responses. With the BYOD in place, DattoRMM's options generation workflows are optimized, leading to improved performance and reduced wait times.

#### Post-Integration Steps Specific to DattoRMM

Follow these detailed steps to ensure a seamless integration with DattoRMM

1. **Workflow for Group Options Generation**:
   * Navigate to the **\[Rewst Master v2] On-Prem: Get All Groups** workflow that's set up for options generation.
   * Integrate the **\[Rewst Master v2] BYOD: Insert Data Into Database** as a completion listener for this workflow.
   * Ensure the listener is set to the `Success` status and its integration override is assigned to `SQL Database`.
2. **Workflow for Organizational Units (OUs) Options Generation**:
   * Follow the same process for the **\[Rewst Master v2] On-Prem: Get All OUs** workflow used for options generation.
3. **Refreshing Values**: After implementing the above steps, if any form seems to display outdated data, manually force a refresh to ensure it pulls the latest values.

{% hint style="warning" %}
Certain workflows, like the `Insert Into Database`, might not be automatically available to you. It's often necessary to consult with The ROC for specific sync operations. When in doubt, [reach out](../../../../support/contact-resources.md)!
{% endhint %}
