# Lab 10 — Test the Flow and Diagnose a Failed Run

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 04:** Introduction to Power Automate  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to test a flow end to end, read the run history, and diagnose and resolve a failing connection between two application programs.

## Scenario

A flow that saves is not a flow that works. You trigger the flow with real data, read the run history step by step, then deliberately break the integration and diagnose it from the error — the testing and verification skills this course builds.

## What you will build

A successful flow run with an email received, plus a fault log recording one induced failure, the error message and the fix applied.

**Tools used:** Power Automate run history, Microsoft Dataverse, Office 365 Outlook

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/fault-log-template.csv`](data/fault-log-template.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open the Facility Request table (or the model-driven app from Lab 8) and add a new row with Priority set to High.
2. In Power Automate select My flows, open your flow, and look at the 28-day run history. Confirm a run appears with the status Succeeded.
3. Open the run and expand every step. Record the inputs and outputs of the trigger, Get a row by ID, and the condition — note the condition evaluated to true.
4. Check your inbox and confirm the notification arrived with the correct request title, category, priority and description.
5. Now test the negative path: add a second row with Priority set to Low. Confirm the flow ran, the condition evaluated FALSE, and no email was sent. A flow that correctly does nothing is still a passing test (A6).
6. Induce a fault. Edit the Send an email action and clear the To field, then Save.
7. Add another High priority row and let the flow run. Open the failed run in the history and read the error message on the red step.
8. Record the failure in labs/lab-10-flow-testing-diagnostics/data/fault-log-template.csv: the symptom, the step that failed, the exact error text, the root cause and the fix (A7).
9. Restore the To address, Save, and use Resubmit on the failed run rather than creating a new row — this re-runs the same trigger data (A8).
10. Confirm the resubmitted run now succeeds and the email arrives.
11. Induce a second, different fault of your choosing — for example compare Priority against the label 'High' instead of 3 — and log its symptom, cause and fix.
12. Write a two-sentence verification statement: what you tested, and what evidence proves the integration between Dataverse and Outlook works.

## Test it

Your run history shows at least one Succeeded run that sent an email, one run where the condition correctly evaluated false, and one Failed run that you diagnosed, fixed and successfully resubmitted.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| No run appears at all | The trigger scope is User rather than Organization, or the row was added in a different environment. Check both. |
| Run succeeded but no email arrived | Check the junk folder, then confirm the To address in the action's run inputs is the address you actually monitor. |
| Resubmit is greyed out | Resubmit only applies to a failed or cancelled run. Open the run itself, not the flow, to find the button. |

## Checkpoint questions

1. Where do you look to find out exactly why a flow failed?
2. Why is a run where the condition is false still a valid test result?
3. What does Resubmit do that adding a new row does not?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
