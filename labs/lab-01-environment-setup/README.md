# Lab 1 — Validate the Lab Environment and Tour the Maker Portals

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 01:** Introduction to Microsoft Power Platform  
> **Estimated duration:** 45 minutes

## Objective

By the end of this lab you will be able to sign in to the Power Platform, confirm the environment and licence, and navigate the four maker portals used throughout the course.

## Scenario

Before building anything you confirm you have a working environment. You sign in to the Power Apps maker portal, verify which environment you are in, check your licence, and tour the Power Automate, Power BI and Copilot Studio portals so you know where each service lives.

## What you will build

A validated Power Platform environment plus a portal reference sheet recording your environment name, region, licence type and the Dataverse state.

**Tools used:** Power Apps maker portal, Power Automate, Power BI service, Copilot Studio, Power Platform admin center

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open a private/InPrivate browser window and go to the Power Apps maker portal, then sign in with your Microsoft 365 work or school account.

   <https://make.powerapps.com>

2. Read the environment picker at the top right. Note the environment NAME and REGION — every lab in this course must be built in this same environment.
3. If a Dataverse database has not been provisioned, select the environment picker and choose an environment whose Type is 'Developer' or 'Trial (subscription)'. A developer environment is free and includes Dataverse.
4. Select the gear icon, then Session details. Record the Environment ID, the Tenant ID and the Power Apps version on your reference sheet.
5. In the left navigation select Tables, then switch the filter from Default to All. Confirm you can see the standard tables such as Account and Contact — this proves Dataverse is live in this environment.
6. Open the Power Automate portal in a new tab and confirm the SAME environment is selected in the environment picker.

   <https://make.powerautomate.com>

7. Open the Power BI service in a third tab and confirm you can reach My workspace.

   <https://app.powerbi.com>

8. Open Copilot Studio in a fourth tab and confirm the same environment is selected.

   <https://copilotstudio.microsoft.com>

9. Open the Power Platform admin center and select Environments. Note which environments you can see and what your role is — this is the governance view.

   <https://admin.powerplatform.microsoft.com>

10. Complete the portal reference sheet: for each of the five portals record its URL, what you build there, and who in an organisation typically uses it.

## Test it

You can open all five portals signed in as the same user, the SAME environment name appears in the picker on the Power Apps, Power Automate and Copilot Studio portals, and Tables shows the standard Dataverse tables.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| No environment with Dataverse | Create a free developer environment at https://aka.ms/PowerAppsDevPlan, then re-check the environment picker. |
| 'You need permission' on the admin center | You are not an environment or tenant admin. This is expected for a maker account — record what you CAN see and continue. |
| Wrong environment selected | Every portal keeps its own last-used environment. Set the picker explicitly in each tab before you build anything. |

## Checkpoint questions

1. Which portal do you use to build a canvas app, and which to set a DLP policy?
2. Why must every lab be built in the same environment?
3. What does it mean if Tables shows no tables at all?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
