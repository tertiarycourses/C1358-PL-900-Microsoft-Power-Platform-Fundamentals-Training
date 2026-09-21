# Lab 6 — Build a Canvas App on Dataverse

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 03:** Introduction to Power Apps  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to build a canvas app connected to a Dataverse table and customise its screens, galleries and forms.

## Scenario

Contoso employees need a mobile-friendly way to see and submit facilities requests. You generate a three-screen canvas app from the Facility Request table, then customise the header with the signed-in user's name and format the gallery so it shows the information a coordinator actually needs.

## What you will build

A published canvas app named 'Facility Request App' with a browse gallery, a detail screen, an edit form and a personalised welcome header.

**Tools used:** Power Apps Studio, Microsoft Dataverse, Power Fx

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. In the maker portal select + Create, then under 'Start from data' select Dataverse.

   <https://make.powerapps.com>

2. In the Search field enter 'Facility', select the Facility Requests table, and choose Create app. Power Apps generates a three-screen app.
3. If the 'Welcome to Power Apps Studio' screen appears, tick 'Don't show me this again' and select Skip.
4. Explore the Tree view. Identify the gallery on the browse screen, the display form on the detail screen and the edit form on the edit screen — the three controls every generated app is built from.
5. Select the Facility Requests header on the default screen, then + Insert > Text label.
6. Set the label's Text property to the literal string "Welcome" and format it: Font size 16, Font colour White, Fill Blue, Align Right, Height 52.

   ```
   "Welcome"
   ```

7. Insert a second Text label and set its Text property to the Power Fx expression below, which reads the signed-in user from the Office 365 Users service.

   ```
   User().FullName
   ```

8. Format the second label to match: Font size 16, Font colour White, Fill Blue, Align Right, Height 52, Width 225.
9. Select the gallery and change its Layout so the title shows Request Title and the subtitle shows Status — make the list scannable.
10. Select the Play button to preview. Confirm the gallery lists your eight rows and your own name appears in the header.
11. Select a row and confirm the detail screen shows that request's values, then select the edit icon and confirm the form is editable.
12. Select Save, name the app 'Facility Request App', then select Publish and 'Publish this version'.

## Test it

The published app opens in Play mode, the gallery lists all eight Facility Request rows, your full name renders in the header, and selecting a row opens its details.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| User().FullName shows blank | The app needs the Office 365 Users connection. Select Data > + Add data > Office 365 Users, then re-run the preview. |
| Gallery is empty | The app is pointed at an empty table or the wrong environment. Confirm the environment picker matches Lab 3 and that the table still holds its rows. |
| Cannot find the Text property | Select the control first, then choose Text in the property dropdown at the top left of the formula bar. |

## Checkpoint questions

1. What are the three screens a generated canvas app creates?
2. What does SubmitForm() do that saves you writing an API call?
3. When would you choose a canvas app over a model-driven app?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
