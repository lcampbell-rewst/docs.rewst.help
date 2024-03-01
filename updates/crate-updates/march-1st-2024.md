# March 1st, 2024

<details>

<summary><strong>Crate Change Release Notes</strong></summary>

**What's New with our Crates?**

* **User Offboarding Crate Update**: Added more integration overrides to the User Offboarding Crate, including N-Central.
* **Datto PSA Ticket Fix**: Fixed a Jinja template issue in the Datto PSA ticket creation task that caused errors due to extra spaces.
* **Workflow Sensitivity and Jinja Update**: Adjusted task transition sensitivity from 10 to 9 and tweaked Jinja syntax to avoid errors when lists are empty.
* **Offboarding Crate Halo Update**: Updated the Offboarding Crate to include Halo integration.
* **Usage Location Update**: Added a new data alias for usage locations to prevent incorrect default settings.
* **Workflow Transition Logic**: Improved logic for workflow transitions to prevent incorrect path selection based on org variable settings.
* **Jinja Examples Crate Enhancements**: Added new examples to the Common Jinja Examples crate, including datetime checks and a macro for the last day of the month.
* **Database Check Update**: Updated the condition for checking database installation in workflows to avoid unnecessary steps.
* **Script Enhancement**: Added $env:ComputerName variable to a script to help identify the domain controller with outdated PowerShell.
* **Database Integration Note**: Clarified the use of specific database names for certain integrations and outlined how to disable them if not needed.

</details>
