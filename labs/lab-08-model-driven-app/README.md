# Lab 8 — Build a Model-Driven App with Custom Forms and Views

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 03:** Introduction to Power Apps  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to build a model-driven app from the Dataverse model, customise its form and view, and publish it.

## Scenario

The facilities team manages requests all day on a desktop, so they need a full-featured app rather than a mobile canvas. You build a model-driven app using the modern designer, group its navigation, then customise the Facility Request main form and the Active Facility Requests view so the columns the team needs are visible.

## What you will build

A published model-driven app, 'Contoso Facilities Management', with grouped navigation, a customised main form and a customised public view.

**Tools used:** Power Apps modern app designer, Microsoft Dataverse, forms and views

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. In the maker portal select + Create, then choose 'Blank Page with navigation'. Name the app 'Contoso Facilities Management' and select Create.

   <https://make.powerapps.com>

2. In the App Designer select + Add page, choose Dataverse table, and select the Facility Request, Room, Account and Contact tables.
3. Ensure 'Show in navigation' is ticked, then select Add.
4. On the left select Pages. Under Navigation select New group and rename it to 'Customers'.
5. Select the three dots beside the Customers group, choose New group, and rename that one to 'Facilities'.
6. Select the Facility Requests view and use Move down until it sits inside the Facilities group. Repeat for the Rooms view. Save.
7. In a new tab open Tables, search for Facility Request, open it, and under Data experiences select Forms.
8. Open the Information form whose Form type is Main, using Commands (...) > Edit > Edit in new tab.
9. Drag Owner and Status into the Header area — header fields stay visible as the user scrolls.
10. Drag Description, Date Requested, Estimated Cost, Category and Priority into the body in that order, then select Save and publish and close the designer.
11. Back on the table, under Data experiences select Views, and edit the 'Active Facility Requests' view.
12. Remove the Created On column, then add Description, Date Requested, Estimated Cost, Category, Priority and Status. Save and publish, then close.
13. Return to Apps, open Contoso Facilities Management, select Save and Publish, then Play.
14. Verify the navigation shows the Facilities group, the list view shows your columns, and opening a record shows the form layout you built.

## Test it

The published app opens with grouped navigation; the Active Facility Requests view shows the six added columns; and a record's form shows Owner and Status in the header with the other fields in the order you set.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Changes do not appear in the app | Forms and views must be published separately from the app. Select Save and publish in the form/view designer, then Save and Publish the app. |
| Move down will not place the view in the group | Groups only accept pages below them. Keep selecting Move down until the item indents under the group heading. |
| The table is missing from + Add page | You are in the wrong environment. Check the environment picker matches Lab 3. |

## Checkpoint questions

1. Where does a model-driven app get its user interface from?
2. Name two things a model-driven app gives you for free that you must build by hand in a canvas app.
3. Why must you publish a form after editing it?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
