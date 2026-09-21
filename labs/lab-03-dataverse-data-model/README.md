# Lab 3 — Build the Contoso Dataverse Data Model

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 02:** Introduction to Dataverse  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to create a Dataverse table with the full range of column types and populate it with business data.

## Scenario

Contoso needs a central store for facilities request data. You create the Facility Request table in Dataverse, add text, date, currency and choice columns, and load the sample request data so later labs have something to display.

## What you will build

A Facility Request table in Dataverse with seven columns — including three choice columns — and eight sample request rows.

**Tools used:** Power Apps maker portal, Microsoft Dataverse

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/facility-requests.csv`](data/facility-requests.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Go to the maker portal, confirm your course environment is selected, and in the left navigation select Tables.

   <https://make.powerapps.com>

2. Select the + New table dropdown and choose Table (advanced properties).
3. In the Properties panel set the Display name to 'Facility Request'. The plural name auto-populates as Facility Requests.
4. Select the Primary Column tab and set its Display name to 'Request Title', then select Save. The primary column is the human-readable name of every row.
5. Under 'Facility Request columns and data' select +, and add: Display name 'Description', Data type Multiple Lines of Text. Expand Advanced options and set Maximum character count to 2000. Save.
6. Add a second column: Display name 'Date Requested', Data type Date and Time, Format Date Only. Expand Advanced options and set Time Zone adjustment to User Local. Save.
7. Add a third column: Display name 'Estimated Cost', Data type Currency. Leave the defaults and Save. Currency columns store a base and a transaction value.
8. Add the 'Category' choice column. Set Data type to Choice, set 'Sync with global choice?' to No, and add the labels Maintenance, Equipment, Supplies, Room Setup and Other. Set Default Choice to None. Save.
9. Add the 'Priority' choice column with these labels AND values — Low 1, Medium 2, High 3, Urgent 4. Set Default Choice to None and Save. Record these integers: Power Automate compares against the VALUE, not the label.
10. Add the 'Status' choice column with labels New, In Progress, Completed and Cancelled. Set Default Choice to New and Save.
11. Select Edit on the table, then + New row, and enter the eight rows from labs/lab-03-dataverse-data-model/data/facility-requests.csv, filling Request Title, Description, Category, Priority, Status, Date Requested and Estimated Cost.
12. Switch the view to the grid and confirm all eight rows display with the correct choice labels rendered as text, not numbers.

## Test it

The Facility Request table lists eight rows; Category, Priority and Status render as choice labels; and Priority values map to Low=1, Medium=2, High=3, Urgent=4.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Table (advanced properties) is missing | You are on the classic Tables view. Use + New table > Table (advanced properties); if unavailable, create the table then rename the primary column afterwards. |
| Choice values are not 1–4 | Open the Priority column, select Edit choices, and correct the Value box next to each label. Lab 8's condition depends on High=3 and Urgent=4. |
| Currency column will not save | The environment needs a base currency. Open the admin center > Environment > Settings > Product > Currencies and confirm one is set. |

## Checkpoint questions

1. Name three things Dataverse gives you that a spreadsheet does not.
2. What is the primary column used for?
3. Why does a choice column store an integer value as well as a label?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
