# Configure Organization Variables

### Introduction

An organization variable is a universal setting that applies across your MSP Rewst Organization and your Client's organizations. Organization variables are used to apply values at the organization and sub-org layers. They are referenced in workflows using the syntax `{{ ORG.VARIABLES. }}`.&#x20;

Sub-organizations can inherit organization variables unless a sub-org has the same variable defined, which will override the value.

The Configure Organizational Variables crate is used to help you set the essential variables that will allow Rewst prebuilt crates to work.

### Installation

1. **Go to** _Crates_ → _Crate Marketplace._
2. **Select** _Configure Organizational Variables_ and follow the unpacking steps.

{% hint style="success" %}
You will now have two forms:

* \[ROC] Rewst: Configure Organizational Variables
* \[ROC] Rewst: Simple Organizational Variable Form for Child Accounts
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2024-02-29 at 2.26.18 PM.png" alt=""><figcaption></figcaption></figure>

### Using the Forms

1. **Go to** Automations → Forms → \[ROC] Rewst: Configure Organizational Variables
2. **Click** the three dots to the right and select Usages → View Direct URLs
3. **Choose** your MSP URL
4. **Select** _Standard_ in the form options
5. **Fill out** the form&#x20;

{% hint style="info" %}
&#x20;Use the table at the bottom of this page for a definition of each field
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2024-02-29 at 2.28.19 PM.png" alt="" width="375"><figcaption></figcaption></figure>

### Setting Organization Variables for Sub-Organizations

To customize variables for client organizations:

1. **Navigate** to _Automations_ → _Forms_ → _\[ROC] Rewst: Simple Organizational Variable Form for Child Accounts._
2. **Click** the three dots to the right and select Usages → View Direct URLs
3. **Select** the URL of the client you would like to configure

<figure><img src="../../.gitbook/assets/Screenshot 2024-02-29 at 2.30.14 PM.png" alt=""><figcaption></figcaption></figure>

####

#### PSA Configuration

| Field Label                            | Description                                                                                                                                     |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Default PSA                            | Select your PSA                                                                                                                                 |
| Default Ticket Location                | The board you want Rewst generated tickets to go onto                                                                                           |
| Default Ticket Status                  | The status when Rewst is actively working on a ticket                                                                                           |
| Ticket Status while Waiting for Input  | The status when Rewst is waiting for a techs input on a ticket, such as when waiting on a license to be purchased                               |
| Ticket Status when Workflow Complete   | The status when Rewst has finished the workflow and is ready for a tech to review                                                               |
| No Time in Tickets                     | <p>Only Use Notes: Will not add time entries to the ticket<br>Add Time Entries: Will add time entries into the ticket</p>                       |
| Default Tech ID                        | Define the Tech ID of the member that Rewst will impersonate for Time Entries                                                                   |
| Default Work Role                      | Define the Work Role for the Tech that Rewst will impersonate for Time Entries                                                                  |
| Default Work Type                      | Define the Work Type for the Tech that Rewst will impersonate for Time Entries                                                                  |
| Default Priority                       | Priority for Rewst created tickets                                                                                                              |
| Send From Address                      | Define the reply to address when sending emails to ensure replies automatically get created in your PSA. This will likely be your support email |

#### **Identity & Access Management**

| Field Label                  | Description                                                                                                                                                          |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Default RMM                  | Select your RMM                                                                                                                                                      |
| Primary Identity Provider    | <p>Select what your organization uses for IDP.<br>Note if you use a hybrid setup with or with out ADsync you will want to select On-Prem</p>                         |
| Preferred Domain Controller  | <p>The host name for the domain controller you would like Rewst to run Powershell on<br>Note: This does not need to be the fully qualified name and can be DC-01</p> |
| Preferred ADConnect Server   | The name of the Server runing ADConnect                                                                                                                              |
| On-Prem Exchange Server      | Name of the On-Prem Exchange Server (if you are not running On-Prem Exchange, leave blank)                                                                           |

#### Licencing & Purchases

| Field Label                      | Description                  |
| -------------------------------- | ---------------------------- |
| Microsoft Licensing Distributor  | Select your license provider |

#### Password Management

| Field Label                          | Description                                                                                                                               |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| Store Password in Ticket             | Define whether to add the onboarding user one time password into the ticket internal notes. This is specific to the User Onboarding Crate |
| Onboarding - Password Save Location  | Select another location to create the user onboard password. Such as PSA, ItGlue, Hudu                                                    |
| PWPush URL                           | Add the URL for your PWPush if you have selected that option above                                                                        |

#### User Onboarding & Offboarding Defaults&#x20;

{% hint style="warning" %}
#### These settings are specific to the User Onboarding & Offboarding crates
{% endhint %}

| Field Label                             | Description                                                                                                                                                                                                                                                                                |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| User Onboarding & Offboarding Defaults  | These settings are specific to the user onboarding workflow                                                                                                                                                                                                                                |
| User Start-Date Behavior                | <p>Start Automation Immediately: WIll create the user immediately regardless of the account creation date specified in the user onboarding form<br>Pause Workflow until Start Date Specified: Pause the workflow until the account creation date specified in the user onboarding form</p> |
| Type for Created New User Ticket        | Select the ticket type for a user onboard creation                                                                                                                                                                                                                                         |
| Subtype for Created New User Ticket     | Select the subtype for a user onboard creation                                                                                                                                                                                                                                             |
| Item for Created New User Ticket        | Select the item for the user onboard creation                                                                                                                                                                                                                                              |
| User Name Format                        | Select the username format for new users for your organization. Note you can specify a different username for each of your organizations with the "\[ROC] Rewst: Simple Organizational Variable Form for Child Accounts form"                                                              |
| No AD Sync                              | Check if you have an OnPrem AD with no Ad Sync                                                                                                                                                                                                                                             |
| Miscellaneous Settings                  |                                                                                                                                                                                                                                                                                            |
| Preferred Phone Number Format           | Select a Prefered Phone number format                                                                                                                                                                                                                                                      |
| M365 Usage Location                     | Select a default M365 Usage Location                                                                                                                                                                                                                                                       |
| New User Approval Email                 | If set, Rewst will send an email to this address requesting approval before it continues the user onboarding workflow.                                                                                                                                                                     |
