# How to Use Powershell in Rewst

{% embed url="https://youtu.be/IhbSoK0AawU" %}

## Introduction

In this video, we'll explore the powerful capabilities of using Powershell in Rewst automation. This is particularly crucial for tasks such as collecting inventory, making changes in Active Directory environments, and performing RMM-style activities like software inventory, malware scans, and software installations. Let's dive into how Rewst communicates with endpoints using Powershell and the REST API.

## Communicating with Endpoints via Powershell

Rewst communicates with endpoints using Powershell through the REST API, treating Powershell commands as workflow actions. By instructing agents on the commands to execute, Rewst facilitates the execution of tasks on endpoints. However, the challenge arises in collecting responses from endpoints, given the limitations of RMMs in output collection. Powershell scripts in Rewst offer a solution by creating objects converted to Json, allowing seamless communication and result retrieval via web hooks.

## Example: Sending Results Back to Rewst

This practical example showcases the creation of a Powershell script. The script includes a PS results object for building Json-convertible objects. The bottom section demonstrates how to convert and send results back to Rewst, ensuring clean, consistent, and actionable information.

Remember, posting results back to Rewst is crucial for script execution, but it won't impact the rest of your automation. The data can then be utilized for further actions.

## Storing Powershell Scripts in Rewst

To store your scripts, navigate to Automations and Scripts, create a new script, add details, paste your Powershell code, and submit. Your script is now securely stored in Rewst, accessible via a unique URL.

## Parameter Handling with Jinja

One of the advantages of using Powershell in Rewst is the seamless two-way data flow between workflows and scripts. Parameter handling using Jinja allows dynamic adaptation to various scenarios. The example illustrates referencing CTX variables within a Powershell script, enhancing flexibility without hardcoding.

## Accessing Scripts and Integration with Workflows

Saved Powershell scripts can be accessed via unique URLs ending with a GUID acting as a unique ID. This ID is essential for future workflow integrations. The use of the unique script ID in a Jinja template call within workflows instructs Rewst to execute specific scripts as part of the workflow.

## Subworkflows for Enhanced Automation

The guide highlights the use of subworkflows, particularly relevant for breaking down specific processes in automation. It references the "Run Powershell script on selected devices" crate in the marketplace, emphasizing its utility in running Powershell scripts on RMMs.

## Conclusion and Exploration

This guide encourages exploration, experimentation, and innovation in leveraging Powershell for Rewst automation. The real power lies in exploring the vast capabilities and getting the most out of your Rewst experience. If you find this information helpful, dive into the Rewst community for additional support and discussions.

Thanks for watching! See you in the next video!
