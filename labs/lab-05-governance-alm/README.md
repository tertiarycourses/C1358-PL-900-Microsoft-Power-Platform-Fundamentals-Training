# Lab 5 — Environments, Security, DLP and Solution-Based ALM

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 02:** Introduction to Dataverse  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to describe environments, the security model, data policies and how solutions and pipelines move work between environments.

## Scenario

Contoso must govern what makers can build. You examine the environment list, inspect security roles on the Dataverse table you built, design a DLP policy that separates business from non-business connectors, and package your work into a solution so it can be promoted from development to production.

## What you will build

A governance pack: an environment strategy table, a security role mapping for the Facility Request table, a two-group DLP policy design, and an exported unmanaged solution containing your tables.

**Tools used:** Power Platform admin center, Power Apps maker portal, Dataverse security roles, solutions and pipelines

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/dlp-policy-design.csv`](data/dlp-policy-design.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open the Power Platform admin center and select Environments. Record the name, type and region of every environment you can see.

   <https://admin.powerplatform.microsoft.com>

2. Complete the environment strategy table: state what Default, Developer, Sandbox and Production environments are each FOR, and why production work must never be built in Default.
3. In the maker portal open the Facility Request table, select the Settings gear then Advanced, and review the security roles that grant access to it.
4. Map the Dataverse security model on paper: environment access, then security role, then table privilege (Create/Read/Write/Delete), then row-level access scope (User / Business Unit / Organization).
5. Decide which Contoso persona gets which scope — an employee sees only their own requests (User), a coordinator sees the whole organisation (Organization).
6. In the admin center select Policies then Data policies. Review any existing policy and note its Business, Non-business and Blocked groups.
7. Complete labs/lab-05-governance-alm/data/dlp-policy-design.csv: place Dataverse, Office 365 Outlook, SharePoint and Teams in Business, and place consumer connectors such as Twitter/X, Dropbox and Facebook in Non-business.
8. Write down the consequence: an app or flow may not combine a Business connector with a Non-business one. Explain how that stops data leaving Contoso.
9. In the maker portal select Solutions, then + New solution. Name it 'Contoso Facilities', set the publisher, and create it.
10. Select Add existing > Table and add both Facility Request and Room, choosing to include all components.
11. Select Export solution, choose Unmanaged, and download the .zip. Note that unmanaged is for source control and managed is for production.
12. Describe the ALM path in your own words: Dev environment (unmanaged) → solution or Power Platform pipeline → Test → Production (managed), with no manual rebuild.

## Test it

You can name the purpose of each environment type, state the row-level scope for both Contoso personas, explain what your DLP policy blocks, and you hold an exported unmanaged solution .zip containing both tables.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Data policies is greyed out | DLP policies need tenant or environment admin rights. Complete the design on paper — the exam objective is to DESCRIBE the policy, not to create one. |
| Solution export fails | A component is still publishing. Select Publish all customizations on the solution, wait for it to finish, then export again. |
| Cannot see other environments | You only see environments you have a role in. Record what is visible and note why the list is short. |

## Checkpoint questions

1. Why should you never build a production app in the Default environment?
2. What is the difference between a managed and an unmanaged solution?
3. How does a DLP policy actually prevent data exfiltration?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
