# Lab 12 — Connect, Transform and Model Facilities Data in Power BI

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 05:** Introduction to Power BI  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to connect Power BI to a data source, clean and transform it with Power Query, and build a model with a relationship.

## Scenario

Contoso's management wants visibility over facilities spend. You connect Power BI Desktop to the facilities export, use Power Query to clean the deliberately messy data, then relate the requests to the rooms so the model can answer questions neither table could answer alone.

## What you will build

A Power BI model with a cleaned Facility Requests table, a Rooms table and a working relationship between them.

**Tools used:** Power BI Desktop, Power Query Editor

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/facility-requests-export.csv`](data/facility-requests-export.csv)
- [`data/rooms-export.csv`](data/rooms-export.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open Power BI Desktop. If it is not installed, download it from the Microsoft Store or powerbi.microsoft.com/desktop.

   <https://powerbi.microsoft.com/desktop>

2. Select Get data > Text/CSV and open labs/lab-12-powerbi-transform-model/data/facility-requests-export.csv.
3. In the preview select Transform data rather than Load — always inspect before you load.
4. In Power Query, examine the column quality bar. Note the errors and blanks that the export contains.
5. Set the data types: Request Title and Description to Text, Date Requested to Date, Estimated Cost to Decimal Number, Category/Priority/Status to Text.
6. Use Remove rows > Remove blank rows to drop the empty export rows.
7. Select the Estimated Cost column and use Replace values to replace the text 'N/A' with null, then Replace nulls with 0 so the column aggregates cleanly.
8. Use Transform > Format > Trim and then Capitalize Each Word on the Category column to fix the inconsistent casing in the export.
9. Use Remove columns to drop the internal 'ImportBatchId' column — data the report does not need should not reach the model.
10. Rename the query to 'Facility Requests'. Select Home > Close & Apply.
11. Repeat Get data > Text/CSV for rooms-export.csv, set the types, and name the query 'Rooms'.
12. Open Model view. Drag Room from Facility Requests onto Room Name in Rooms to create the relationship, and confirm it is many-to-one with a single cross-filter direction.
13. Verify the model: create a quick table visual showing Building and Sum of Estimated Cost. If it returns values, the relationship works (A6).

## Test it

Both tables load with no errors, Estimated Cost is numeric with no nulls, Category values are consistently cased, and a table visual of Building against Sum of Estimated Cost returns non-blank figures.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Estimated Cost will not convert to a number | Text such as 'N/A' remains. Replace it with null first, then change the data type. |
| The relationship will not create | The key columns have different data types or trailing spaces. Trim both and confirm both are Text. |
| The visual shows blank for every building | The relationship direction is wrong or the key values do not match. Check the room identifiers in both tables are written identically. |

## Checkpoint questions

1. Why transform data in Power Query instead of after loading it?
2. What does a many-to-one relationship let you do?
3. How would you prove a Power BI report matches its source system?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
