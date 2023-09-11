# Microsoft Graph Integration Setup

## Overview

The Microsoft Graph integration allows MSPs to interact with Microsoft Graph API through Rewst. Microsoft Graph serves as a unified endpoint for interacting with various Microsoft products, such as Office 365, Azure Active Directory, SharePoint, OneDrive, Outlook, Teams, and more.

By leveraging this integration, MSPs can build workflows that integrate and interact with Microsoft services, retrieve and manipulate data, and perform various tasks on behalf of users or organizations. It provides a consistent and secure way to access resources and data across different services, eliminating the need for developers to make multiple API calls to different endpoints.

Microsoft Graph supports a wide range of operations, including reading and writing data, managing users, accessing calendars and contacts, retrieving files, sending emails, and performing analytics on user activities. It also allows developers to create custom applications and workflows that leverage the capabilities of Microsoft services.

## Integration Setup

Rewst recommends installing Microsoft integrations in the following order:

1. Microsoft CSP
2. Microsoft Graph
3. Microsoft Exchange Online

Use the same account for authorization when installing these integrations:

1. **Navigate** to the integrations page in [Rewst](https://app.rewst.io/).
2. **Click** on the Microsoft Graph integration.
3. (Optional) **Enable** the Use CSP Delegated Admin Permissions toggle.
4. **Click** the Microsoft Graph OAuth Configuration Authorize/Re-Authorize button (using the same account as used for the Microsoft CSP integration).
5. **Follow** the authorization steps prompted by Microsoft.
