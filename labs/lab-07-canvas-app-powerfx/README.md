# Lab 7 — Extend the Canvas App with a New Screen and Power Fx Navigation

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 03:** Introduction to Power Apps  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to add a screen and a form to a canvas app and wire navigation with Power Fx functions that call the underlying data API.

## Scenario

Coordinators also need to add rooms without leaving the app. You add a second screen containing an edit form bound to the Room table, then use the Power Fx functions NewForm, SubmitForm and Navigate to move between screens and commit the record — API-level integration expressed as formulas.

## What you will build

A second screen, 'New Room Screen', with a working Room edit form and two buttons that navigate between the request list and the room form.

**Tools used:** Power Apps Studio, Microsoft Dataverse, Power Fx

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open Facility Request App in Power Apps Studio and select Edit.
2. From the command bar select New screen, then choose the Header and Footer layout.
3. In Tree view rename the new screen from Screen1 to 'New Room Screen'.
4. Select + in the header container, insert a Text label, and set its Text property to "Add New Room". Format it white on blue, right aligned, height 52.

   ```
   "Add New Room"
   ```

5. Select the Header container itself and set its Fill to Blue so the two screens match.
6. In the main container select + Insert > Edit form. In the data Search field enter 'Room' and select the Rooms table.
7. If the form shows system columns such as Import Sequence Number, Time Zone Rule Version Number or Record Created On, select each in Tree view and delete it.
8. In the form's Properties pane set Default mode to New so the form opens blank ready for data entry.
9. Select the footer, insert a Button, set its Text to "Submit", and set its OnSelect property to the formula below — SubmitForm writes the row to Dataverse, then Navigate returns to the list.

   ```
   SubmitForm(Form2); Navigate('Facility Requests screen')
   ```

10. Return to the Facility Requests screen, select the gallery, and from the command bar insert a Button. Set its Text to "New Room".

   ```
   "New Room"
   ```

11. Set that button's OnSelect to the formula below — NewForm resets the form to a blank record before navigating, so you never edit the previous row by accident.

   ```
   NewForm(Form2); Navigate('New Room Screen')
   ```

12. Select Play, choose New Room, add a fourth room (for example 512 / West / Kepler / 5 / Yes), select Submit, and confirm you land back on the request list.
13. Open the Room table in the maker portal and confirm the new room was written to Dataverse. Save and Publish the app.

## Test it

Selecting New Room opens a blank Room form; Submit writes the row to the Dataverse Room table and returns you to the request list; the new room is visible in the maker portal.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Submit does nothing | The formula names the wrong form. Check the form's actual name in Tree view — it may be Form1 rather than Form2 — and update SubmitForm() to match. |
| The form saves over an existing room | NewForm() is missing from the navigation button. Without it the form keeps the last selected record and SubmitForm updates rather than creates. |
| Navigate reports the screen does not exist | Screen names are literal. Use the exact name from Tree view, in single quotes if it contains spaces. |

## Checkpoint questions

1. What is the difference between NewForm() and EditForm()?
2. Which Power Fx function commits the form's data to Dataverse?
3. How does a Power Fx function relate to an API call?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
