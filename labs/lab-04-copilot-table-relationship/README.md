# Lab 4 — Create a Related Table with Copilot and Build a Relationship

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 02:** Introduction to Dataverse  
> **Estimated duration:** 45 minutes

## Objective

By the end of this lab you will be able to use AI to create and edit tables and columns, and connect two tables with a lookup relationship.

## Scenario

Contoso's requests need to be tied to a specific room. You create a Room table using the Copilot pane instead of the form designer, then add a lookup column on Facility Request so every request points at one room — a one-to-many relationship.

## What you will build

A Room table with five columns and three sample rows, plus a Room lookup column on Facility Request creating a one-to-many relationship.

**Tools used:** Power Apps maker portal, Microsoft Dataverse, Copilot in Dataverse

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/rooms.csv`](data/rooms.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. In the maker portal select Tables, then 'Start with a blank table'.
2. Rename the table from Table1 to 'Room'.
3. In the Copilot pane, rename the default column by entering: Rename New Column in the Room table to Room Name
4. In the Copilot pane, add three text columns at once by entering: Add new columns named Campus, Building, and Floor to the Room table
5. In the Copilot pane, add the yes/no column by entering: Add a new yes/no column named Conference Room to the Room table
6. Review what Copilot produced. Copilot results vary — check each column's data type and correct any that are wrong before saving. This review step is the maker's job.
7. Add the three sample rows from labs/lab-04-copilot-table-relationship/data/rooms.csv — 301 A / North / HighPoint / 3 / Yes, 233 / South / Sierra / 2 / No, and 401 B / East / Jacobson / 4 / Yes.
8. Select Save and exit, then in the 'Done working?' dialog select Save and exit.
9. Return to Tables, select All, search for 'Facility', and open the Facility Request table.
10. Under Schema select Columns, then + New column. Set Display name 'Room', Data type Lookup, and Related table 'Room'. Save.
11. Open the Facility Request rows and set the Room value on at least three requests, confirming the lookup offers only the three rooms you created.
12. Open the Room table and select Relationships. Confirm a one-to-many relationship from Room to Facility Request now exists.

## Test it

The Room table holds three rows, Facility Request has a working Room lookup that resolves to a room name, and the Relationships tab shows the one-to-many link.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Copilot pane is not visible | Copilot may be disabled for the environment or region. Add the columns manually with + New column — the learning outcome is the data model, not the tool. |
| Copilot created the wrong data type | Expected. Open the column, correct the type, and note the correction — reviewing AI output is part of the exam objective. |
| Lookup shows no rooms | The Room rows were not saved. Reopen the Room table, confirm the rows persisted, then refresh the Facility Request form. |

## Checkpoint questions

1. What kind of relationship does a lookup column create?
2. Why must a maker review what Copilot generates?
3. Which table holds the lookup column in a one-to-many relationship?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
