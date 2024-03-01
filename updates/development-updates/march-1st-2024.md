# March 1st 2024

Explore what new changes the Dev team has deployed in the last week!

This can be anything from new features, bug fixes, or QoL changes!

<details>

<summary><strong>New features and items</strong></summary>

* Added a `compress_string` and Jinja filter which compresses string value and returns a byte string.&#x20;
* Added a `msgpack` Jinja filter which serializes/deserializes json and returns a byte string.&#x20;
* Updated action parameter labels for CW PSA - Create Forecast for Sales Opportunity.
* Added `warranty_start` , `warranty_end`, and `warranty_note` fields to the Halo PSA add or update asset action.
* Added actions for ConnectWise PSA List Service Board Types, Subtypes and Items.
* Added a Rewst - Update Trigger action.

</details>

<details>

<summary><strong>Bug fixes and chores</strong></summary>

* Fixed `payload string too long` exception with on cloned workflow triggers large numbers of managed organizations are being saved.
* Removed unnecessary data from Redis streams to improve platform performance and efficiency.
* Fixed Microsoft Exchange Online actions looking for a response.status\_code when response is None.
* Fixed error in Microsoft Azure where `tenant_id` was being checked before it existed.
* Fixed issues with the Kaseya BMS Get Account By ID and Get Contact By ID action.
* Fixed ProofPoint - Domain Verification Code action parameters.
* Updated Duo - Send Activation By SMS action that was expecting an `int` but receiving a `num` (float).
* Fixed Datto Autotask webhook actions by changing `isSubscribedToPatchEvents` should be `isSubscriptedToUpdateEvents`

</details>

<details>

<summary><strong>In review, testing and development</strong></summary>

* Custom integrations v2 (In Review)
* Workflow version control (In Review)
* Microsoft refactor to allow for better permission system (In Development)
* Prevent duplicate action name errors (in Development)

</details>
