# Lab 9 — Build an Automated Cloud Flow with a Condition

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 04:** Introduction to Power Automate  
> **Estimated duration:** 75 minutes

## Objective

By the end of this lab you will be able to create an automated cloud flow triggered by a Dataverse event, add a condition and send a notification through a connector.

## Scenario

Contoso wants the facilities team alerted the moment a high-priority request arrives. You build an automated cloud flow that triggers when a row is added to Facility Request, retrieves the full row, tests the Priority value, and sends an Outlook email only when the request is High or Urgent.

## What you will build

A saved cloud flow, 'Notify on High Priority Request', with a Dataverse trigger, a Get a row by ID action, an Or condition on Priority and a Send an email action.

**Tools used:** Power Automate, Microsoft Dataverse connector, Office 365 Outlook connector

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open the Power Automate maker portal and confirm the environment picker shows your course environment.

   <https://make.powerautomate.com>

2. Select + Create, then Automated cloud flow. Name it 'Notify on High Priority Request'.
3. In the trigger search box enter 'When a row is added' and select 'When a row is added, modified or deleted (Microsoft Dataverse)'. Select Create.
4. If the trigger reports Invalid Parameters, select Change connection reference > Add new, name the connection 'Dataverse', set Authentication type OAuth, sign in, and select your account.
5. Configure the trigger: Change type = Added, Table name = Facility Requests, Scope = Organization so it fires for every user, not just you.
6. Below the trigger select + to add an action. Search for 'Get a row by ID' and select it under Microsoft Dataverse.
7. Configure it: Table name = Facility Requests, and set Row ID from Dynamic content to the trigger's Facility Request value. The trigger returns only the row's ID, so this action fetches the full record.
8. Add a Condition below the action. Set the left box from Dynamic content to Priority (under Get a row by ID), the operator to 'is equal to', and the right box to 3 — the stored value for High.

   ```
   3
   ```

9. Add a second row to the condition for Urgent, using the value 4, and change the And dropdown to Or. The condition now reads Priority = 3 OR Priority = 4.

   ```
   4
   ```

10. In the If yes branch select + > Add an action, search 'Send an email' and select Send an email (V2) from Office 365 Outlook. Sign in if prompted.
11. Configure the email: To = your own address; Subject = 'High Priority Facility Request:' followed by the Request Title from Dynamic content.

   ```
   High Priority Facility Request: @{Request Title}
   ```

12. Set the Body to a short sentence plus the Category, Priority and Description dynamic values from Get a row by ID, each on its own line. Leave the If no branch empty.
13. Select Save. Read the trigger, condition and action back as a sentence to confirm the logic before testing.

## Test it

The flow saves with no validation errors, the condition uses Or across Priority = 3 and Priority = 4, and the Send an email action sits in the If yes branch only.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Trigger shows Invalid Parameters | The Dataverse connection reference is missing. Select Change connection reference > Add new and sign in again. |
| Priority compares as text and never matches | Use the numeric Value, not the label. High is 3 and Urgent is 4 — the integers you set in Lab 3. |
| Dynamic content list is empty | The Get a row by ID action has not been saved. Save the flow, reopen it, and the dynamic tokens will appear. |

## Checkpoint questions

1. What is the difference between a trigger and an action?
2. Why is a Get a row by ID action needed after the Dataverse trigger?
3. Name the three types of cloud flow.

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
