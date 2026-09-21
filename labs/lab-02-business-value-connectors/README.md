# Lab 2 — Assess the Business Case and Map Connectors to an Integration Need

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 01:** Introduction to Microsoft Power Platform  
> **Estimated duration:** 60 minutes

## Objective

By the end of this lab you will be able to identify integration opportunities across Contoso's systems and perform a feasibility assessment that selects the right connector for each need.

## Scenario

Contoso's facilities process is spread across email, a spreadsheet and a legacy web system. You analyse the current state, identify where Power Platform can create connections between those systems, and perform a feasibility scan that decides which connector — standard, premium or custom — serves each requirement.

## What you will build

A completed integration opportunity register and a connector feasibility assessment recommending a connector and licence tier for each of Contoso's six integration needs.

**Tools used:** Power Platform connector reference, Power Apps maker portal, Microsoft Learn documentation

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/contoso-current-state.csv`](data/contoso-current-state.csv)
- [`data/connector-feasibility-template.csv`](data/connector-feasibility-template.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open labs/lab-02-business-value-connectors/data/contoso-current-state.csv. It lists how Contoso handles facilities requests today, system by system.
2. For each row, write down the PAIN it causes — rekeying, delay, no audit trail, no visibility. This is the evidence for the business case.
3. Complete the integration opportunity register: for each pain point, record the two systems that need to be connected, the data that must move between them, and the direction of flow. This is ability A1.
4. In the maker portal, select Data then Connectors. Filter the list and search for each system named in the CSV: Outlook, SharePoint, Excel, SQL Server, Teams.
5. For each connector, open it and record whether it is Standard or Premium, and list two triggers and two actions it exposes. Those triggers and actions ARE the API surface (K5).
6. Search the connector list for Contoso's legacy 'Building Services' REST API. It is not there — note that this need requires a CUSTOM connector built from an OpenAPI definition, a Postman collection or from blank.
7. Complete the feasibility assessment in connector-feasibility-template.csv. For each need score: is a connector available, is it standard or premium, does it need a gateway, and what is the licence impact. This is ability A2.
8. Write a one-paragraph recommendation naming the connector for each of the six needs and flagging which two require premium licensing.
9. Classify each of Contoso's target platforms — web, mobile, desktop and Teams — and note that one Power Platform solution serves all four without a rewrite (K3).
10. Review the DLP implication: if a policy puts SharePoint in Business and the custom connector in Non-business, the two cannot be used in the same app or flow.

## Test it

Your register names both systems and the data direction for every opportunity, and your feasibility assessment recommends a specific connector with its licence tier for all six needs, including a custom connector for the legacy REST API.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| Cannot find a connector in the maker portal | Use https://learn.microsoft.com/connectors/connector-reference/ — it lists every connector and its tier without needing a licence. |
| Unsure whether a connector is premium | The connector card shows a PREMIUM badge. Premium requires a per-user or per-app Power Apps/Power Automate licence. |
| No API for a legacy system | If it exposes no API at all, the integration path is a desktop flow (RPA) driving the UI, not a connector. |

## Checkpoint questions

1. What makes Power Platform 'middleware' in this scenario?
2. Name the three ways to create a custom connector.
3. Why does a DLP policy break an app that uses two connectors from different groups?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
