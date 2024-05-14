# Crate State and Maturity

Due to the nature of the Crate Marketplace, and all the various integrations that we support, we often have various stages of crate deployment. This is to ensure that crates are thoroughly tested not only internally, but also by our willing clients. In order to make this process as transparent as possible, we have created a state system for crates.

<details>

<summary>Egg - Pre-alpha Release</summary>

This is the initial state of a crate. It is the equivalent of a pre-alpha release. It is generally not recommended to use these crates in production.

We will often create crates in this state to show what is actively being worked on, and to get feedback from our clients to ensure we are working on the right things.

</details>

<details>

<summary>Hatchling - Alpha Release</summary>

This is the first stage of a crate that is ready for testing, but still considered alpha. It is not recommended to use these crates in production.

This state will often be used when we are doing internal testing, or the crate was made for a very specific purpose/requirement and is being tested directly with the requesting client.

</details>

<details>

<summary>Fledgling - Beta Release</summary>

This is the second stage of a crate that is ready for testing, and is the equivalent of a beta release.

At this stage, it is recommended to use client discretion when using these crates in production.

This state will often be used when we have moved on from internal testing and believe that the crate is ready for wider testing, but still needs to be tested in a production environment rather than our sandbox environments.

The ROC team will support this crate in this state.

</details>

<details>

<summary>Nestling - Release Candidate</summary>

This is the third stage of a crate that is ready for production, and is the equivalent of a release candidate.

At this stage, it is still recommended to use discretion when using these crates in production, however they have gone through vigorous testing in various environments and are considered stable.

This state will often be used when we have moved on from a smaller range of clients testing the crate, and are now ready to release it to a wider audience with potentially more complex environments.

The ROC team will support this crate in this state.

</details>

<details>

<summary>Soaring - Full Release</summary>

This is the final stage of a crate that is ready for production, and is the equivalent of a full release.

At this stage, the crate is considered stable and ready for production use.

The ROC team will support this crate in this state.

</details>

<details>

<summary>Migrating - Updating to a New Version</summary>

This is the state where a crate has been updated to a new version, but the older version is still available for clients to use.

This state will often be used when we have made a breaking change to a crate, and we want to ensure that clients have time to migrate to the new version before we remove the old version.

The ROC team will support this crate in this state.

</details>

{% hint style="info" %}
Setup Times Note that each crate may differ in terms of requirements, setup time, and complexity. This is why we have a range of states for each crate, to ensure that we can support the client in the best way possible.

We will also try to provide an estimate of the setup time for each crate, however, this is not always possible due to the nature of the crate.
{% endhint %}
