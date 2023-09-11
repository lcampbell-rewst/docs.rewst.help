---
description: >-
  This page is dedicated to assistance with the product itself and how you can
  utilize it with the Rewst platform
---

# Webhook Configuration

### Webhook Setup

By default, the Datto PSA "API User (system)" security level does not have permission to create company webhooks. This means that when you configure a trigger in the Rewst platform, you will receive an error message stating that the webhook could not be created. To resolve this, you will need to create a new security level

1. **Navigate** to the Datto PSA UI
2. **Go to** Admin → Account Settings & Users
3. **Click** "Security Levels" on the "Resources / Users (HR)" tab.
4. **Find** the "API User (system) (API-only)" security level on the context menu
5. **Select** Copy.
6. **Scroll down** to the "Other" tab and check the checkbox for "Create Company Webhooks".
7. **Enter** a number (each trigger will require at least one webhook).
8. **Save**, then edit the user you are using to authorize Rewst and set it to this new security level

You should now be able to create webhooks via the Rewst platform, which will happen automatically when you create a trigger such as "Datto - Ticket Record Saved"
