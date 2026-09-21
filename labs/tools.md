# Tools, Portals and References

Everything you need for the 15 hands-on labs. Bookmark the five portals — you will
move between them constantly.

## The five portals

| Portal | URL | What you build there |
|--------|-----|----------------------|
| Power Apps maker portal | <https://make.powerapps.com> | Dataverse tables, canvas apps, model-driven apps, solutions |
| Power Automate | <https://make.powerautomate.com> | Cloud flows, approvals, desktop flows |
| Power BI service | <https://app.powerbi.com> | Publish reports, pin dashboards, share |
| Copilot Studio | <https://copilotstudio.microsoft.com> | Agents, topics, knowledge sources, tools |
| Power Platform admin center | <https://admin.powerplatform.microsoft.com> | Environments, DLP policies, analytics |

> **The single most important rule:** every portal remembers its **own** last-used
> environment. Check the environment picker at the top right before you build anything.

## Getting an environment

If you do not have a Power Platform environment, join the free **Power Apps Developer
Plan** — a personal environment with Dataverse, Power Automate and Copilot Studio at no
cost: <https://aka.ms/PowerAppsDevPlan>

Install **Power BI Desktop** (free) before Topic 5:
<https://powerbi.microsoft.com/desktop>

## Microsoft documentation

- PL-900 study guide — <https://learn.microsoft.com/credentials/certifications/resources/study-guides/pl-900>
- Power Platform — <https://learn.microsoft.com/power-platform/>
- Dataverse — <https://learn.microsoft.com/power-apps/maker/data-platform/>
- Power Apps — <https://learn.microsoft.com/power-apps/>
- Power Fx formula reference — <https://learn.microsoft.com/power-platform/power-fx/formula-reference>
- Power Automate — <https://learn.microsoft.com/power-automate/>
- Power BI — <https://learn.microsoft.com/power-bi/>
- Copilot Studio — <https://learn.microsoft.com/microsoft-copilot-studio/>
- Connector reference (every connector, with its tier) — <https://learn.microsoft.com/connectors/connector-reference/>
- Application lifecycle management (ALM) — <https://learn.microsoft.com/power-platform/alm/>

## Exam preparation

- Tertiary Infotech practice exam — <https://exams.tertiaryinfotech.com/practice-exams/microsoft/microsoft-pl-900>
- Microsoft free practice assessment and exam booking — <https://learn.microsoft.com/credentials/certifications/power-platform-fundamentals/>

## Mock data used in the labs

Each lab folder carries its own `data/` directory. The Contoso Facilities dataset spans:

| File | Lab | Purpose |
|------|-----|---------|
| `contoso-current-state.csv` | 2 | The as-is process, for the opportunity register |
| `connector-feasibility-template.csv` | 2 | Feasibility assessment worksheet |
| `facility-requests.csv` | 3 | Eight sample requests for the Dataverse table |
| `rooms.csv` | 4 | Three rooms for the related table |
| `dlp-policy-design.csv` | 5 | DLP Business / Non-business grouping |
| `Room Reservations.xlsx` | 6 | Excel import source for the template app |
| `fault-log-template.csv` | 10 | Flow fault log (symptom, cause, fix) |
| `facility-requests-export.csv` | 12 | Deliberately messy export for Power Query |
| `rooms-export.csv` | 12 | Room dimension for the Power BI model |
| `facilities-faq.md` | 14 | Knowledge source for the Copilot Studio agent |
| `integration-fault-log.csv` | 15 | Agent integration fault log |

## Evidence to keep

Keep a record of what you build as you go — it is the quickest way to revise:

- Screenshots of each finished build (table, app, flow run, report, agent conversation)
- Your integration opportunity register and connector feasibility assessment
- The fault logs, with the symptom, root cause and the fix you applied
- Flow run history showing both a successful run and a correctly-skipped run
