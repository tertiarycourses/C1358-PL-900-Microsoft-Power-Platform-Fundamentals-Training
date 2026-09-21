# Lab 13 — Visualise, Publish and Share a Facilities Dashboard

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 05:** Introduction to Power BI  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to build report visuals, publish to the Power BI service, pin a dashboard and share it, then verify the published output against the source.

## Scenario

A model is only useful once people can see it. You build the report visuals management asked for, publish to the Power BI service, pin the key visuals to a dashboard, share it, and then verify the published figures match the source data — the final check that the integration works end to end.

## What you will build

A published Power BI report and a shared dashboard showing request volume by category, cost by building and a priority breakdown, with verified totals.

**Tools used:** Power BI Desktop, Power BI service, workspaces, dashboards

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. In Power BI Desktop, on Report view, add a Clustered column chart. Put Category on the X axis and Count of Request Title on the Y axis.
2. Add a Card visual showing Sum of Estimated Cost. Format it as currency with no decimal places.
3. Add a Bar chart with Building on the Y axis and Sum of Estimated Cost on the X axis, sorted descending.
4. Add a Donut chart showing the count of requests broken down by Priority.
5. Add a Slicer for Status so viewers can filter to open requests only.
6. Test the interactivity: select a bar in the Building chart and confirm every other visual cross-filters to that building.
7. Record the unfiltered total of Estimated Cost from the card — you will verify against this figure after publishing.
8. Save the file as 'Contoso Facilities.pbix', then select Publish and choose My workspace.
9. Open the Power BI service, go to My workspace, and open the published report.

   <https://app.powerbi.com>

10. Compare the published card total against the figure you recorded. They must match exactly — this is the verification step (A6).
11. Hover each visual and use the pin icon to pin the card, the column chart and the bar chart to a new dashboard named 'Contoso Facilities Dashboard'.
12. Open the dashboard, select Share, and note the sharing options and what a recipient needs — a Power BI licence and access to the workspace.
13. Select the dataset's Settings and note the Refresh section: state how often the data would need to refresh for this dashboard to stay accurate.
14. Explain in one sentence the difference between the report and the dashboard you just created.

## Test it

The report shows five working, cross-filtering visuals; the published report's total Estimated Cost matches the figure recorded in Desktop; and the dashboard holds three pinned tiles that open the report when selected.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Publish is greyed out | You are not signed in to Power BI Desktop, or the account has no Power BI licence. Sign in at the top right and retry. |
| Published totals differ from Desktop | A filter is applied on the published page, or the file was changed after publishing. Clear filters and re-publish. |
| Cannot pin a visual | Pinning is only available in the service, not Desktop. Open the report in app.powerbi.com first. |

## Checkpoint questions

1. What is the difference between a report and a dashboard?
2. Why must you verify published totals against the source?
3. What does a recipient need in order to open a dashboard you shared?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
