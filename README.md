# Enforcing-Mandatory-Fields-using-UI-Policies-and-Migrating-Changes-with-Updates-Sets
# Enforcing-Mandatory-Fields-using-UI-Policies-and-Migrating-Changes-with-Updates-Sets
Overview:

This project demonstrates how to enforce mandatory fields in ServiceNow forms using UI Policies and how to migrate these configurations between instances using Update Sets.

UI Policies provide a no-code/low-code way to dynamically control form behavior such as making fields mandatory, read-only, or visible based on conditions. Update Sets allow developers and administrators to move configuration changes from one ServiceNow instance to another (e.g., from Development → Test → Production).

This repository documents the steps and configurations required to implement and migrate such changes.


Objectives:

Enforce mandatory fields dynamically using UI Policies

Apply UI Policy Actions to specific form fields

Test UI Policy behavior on forms

Capture configurations in an Update Set

Migrate the changes to another instance



Technologies Used:

ServiceNow Platform

UI Policies

UI Policy Actions

Update Sets


Implementation Steps:
1. Create a UI Policy

Navigate to:

System UI → UI Policies

Click New.

Configure the following fields:

Table: Select the target table (e.g., Incident)

Short Description: Make Assignment Group Mandatory

Conditions: Define when the policy should run

On Load: True (optional depending on requirement)

Click Submit.

2. Create UI Policy Action

Open the created UI Policy.

Scroll to UI Policy Actions related list.

Click New.

Configure:

Field Name: Assignment Group

Mandatory: True

Visible: Leave unchanged or set as needed

Read Only: False

Click Submit.

Now the selected field becomes mandatory when the policy condition is met.

3. Test the UI Policy

Navigate to the target module (e.g., Incident → Create New).

Trigger the condition defined in the UI Policy.

Verify that the configured field becomes mandatory.


Migrating Changes using Update Sets:
1. Create a New Update Set

Navigate to:

System Update Sets → Local Update Sets

Click New.

Provide:

Name: UI Policy Mandatory Field

State: In Progress

Click Submit and set it as Current.

2. Capture Changes

Create or modify the UI Policy and UI Policy Actions while this Update Set is active.

ServiceNow automatically records these changes.

3. Complete the Update Set

Go to Local Update Sets.

Open the update set.

Change State → Complete.

4. Export the Update Set

Open the completed Update Set.

Click Export to XML.

5. Import to Target Instance

In the target instance navigate to:

System Update Sets → Retrieved Update Sets

Click Import Update Set from XML.

Upload the XML file.

6. Preview and Commit

Click Preview Update Set to check conflicts.

Resolve any issues.

Click Commit Update Set.

The UI Policy configuration will now be applied in the target instance.
