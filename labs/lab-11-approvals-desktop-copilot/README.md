# Lab 11 — Approvals, Desktop Flows and Copilot-Assisted Automation

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 04:** Introduction to Power Automate  
> **Estimated duration:** 75 minutes

## Objective

By the end of this lab you will be able to describe approvals, Teams/Outlook/SharePoint automation, desktop flows (RPA) and using AI to create and modify flows.

## Scenario

Not every process is a notification. You extend the solution with an approval that pauses the flow until a manager responds, examine where desktop flows fit when a legacy system has no API, and use Copilot to draft a flow from a plain-English description — then review what it produced.

## What you will build

An approval flow for high-cost requests, a desktop-flow scenario assessment, and a Copilot-generated flow that you have reviewed and corrected.

**Tools used:** Power Automate, Approvals connector, Microsoft Teams, Power Automate for desktop, Copilot in Power Automate

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Create a second automated cloud flow named 'Approve High Cost Request', triggered by a row added to Facility Requests, with a Get a row by ID action as before.
2. Add a condition testing whether Estimated Cost is greater than 500.

   ```
   500
   ```

3. In the If yes branch add the action 'Start and wait for an approval'. Set Approval type to 'Approve/Reject - First to respond'.
4. Set the Title to include the Request Title, set Assigned to your own address, and put the cost and description in Details. Save.
5. Add a condition after the approval testing whether the Outcome is equal to Approve.

   ```
   Approve
   ```

6. In the If yes branch add a Dataverse 'Update a row' action that sets Status to In Progress; in the If no branch set Status to Cancelled.
7. Test it: add a request with an Estimated Cost above 500, respond to the approval in Outlook or Teams, and confirm the row's Status changed accordingly.
8. Now assess desktop flows. Contoso's legacy Building Services system is a Windows desktop application with no API. Write down why a cloud flow cannot integrate with it and why a desktop flow (RPA) can.
9. List three desktop-flow use cases: driving a legacy application, automating a website with no API, and working with terminal emulation software.
10. Compare attended and unattended desktop flows — who is signed in, when each runs, and what licence each needs.
11. Use Copilot: create a new flow and describe it in words, for example 'When a new facility request is added and the category is Equipment, post a message to Teams'.
12. Review the flow Copilot produced. Check the trigger, the condition and the action, correct anything wrong, and record two things you had to change. AI drafts, the maker verifies.

## Test it

The approval flow pauses until you respond and then updates the Dataverse row's Status to match your decision; you can state when a desktop flow is required instead of a cloud flow; and you have reviewed and corrected a Copilot-drafted flow.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| The approval never arrives | Assigned to must be a full email address on the same tenant. Check the run history inputs for the approval step. |
| The flow waits forever | 'Start and wait for an approval' blocks by design until someone responds. Respond in Outlook, Teams or the Power Automate Approvals page. |
| Copilot builds the wrong trigger | Expected. Delete the trigger, add the right one manually, and note the correction — reviewing AI output is an exam objective. |

## Checkpoint questions

1. What does 'Start and wait for an approval' do to the flow's execution?
2. When must you use a desktop flow instead of a cloud flow?
3. Why does a Copilot-generated flow still need a maker to review it?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
