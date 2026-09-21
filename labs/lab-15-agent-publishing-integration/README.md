# Lab 15 — Add a Tool, Publish the Agent and Resolve Integration Issues

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 06:** Introduction to Power Virtual Agents (Microsoft Copilot Studio)  
> **Estimated duration:** 75 minutes

## Objective

By the end of this lab you will be able to call a Power Automate flow from an agent, publish to a channel, then diagnose and resolve integration failures and implement improvements.

## Scenario

An agent that only talks is not integrated. You give the agent a tool — a Power Automate flow that writes the request into Dataverse — publish it to a channel, then work through the integration failures that appear when an agent calls a backend system, log each one and implement the fix.

## What you will build

An agent that writes a real Facility Request row to Dataverse through a flow, published to a channel, plus a completed integration fault log.

**Tools used:** Microsoft Copilot Studio, Power Automate, Microsoft Dataverse, publishing channels, analytics

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/integration-fault-log.csv`](data/integration-fault-log.csv)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. In your topic, after the Priority question, select + and choose Add a tool > New Power Automate flow. The Power Automate designer opens with the agent trigger and response already in place.
2. In the flow, add inputs to the trigger for Category and Priority as text.
3. Add a Dataverse 'Add a new row' action targeting Facility Requests. Map Request Title to a fixed string plus the Category input, and map Category and Priority from the inputs.
4. In the 'Respond to the agent' action add an output named Result and set it to a confirmation message. Save the flow and name it 'Create Facility Request'.
5. Return to Copilot Studio, refresh the tool list, and select your flow. Map the topic's Category and Priority variables to the flow's inputs.
6. Add a Message node after the tool that returns the flow's Result output to the user.
7. Test it in the test chat. Complete the conversation, then check the Facility Request table in the maker portal for the new row (A4).
8. Now diagnose the common integration failures. Induce the first: remove the mapping for the Priority input, re-test, and record the error the agent returns.
9. Log it in labs/lab-15-agent-publishing-integration/data/integration-fault-log.csv — symptom, component, error text, root cause, fix. This is ability A7.
10. Restore the mapping and re-test to confirm the fix (A8). Then induce a second fault: change the flow's Dataverse action to a table the agent's user cannot access, and record the permission error.
11. Fix the second fault and note the general rule: an agent runs the flow under a connection, so the connection's identity must have rights to the table.
12. Open the Publish tab and select Publish. Then open Channels and review the available options — Teams, a demo website, a custom website, and others.
13. Publish to the Demo website channel, open the generated link, and run one full conversation as an end user would.
14. Open Analytics and review the available measures — session count, engagement rate, resolution rate and the topics that triggered. State how you would use these to identify a topic that needs improvement.
15. Write two improvement recommendations for the agent based on what you observed, and state what you would change to implement each (A8).

## Test it

A completed conversation in the published channel creates a real row in the Facility Request table, and your fault log records at least two induced failures with the error text, root cause and the verified fix for each.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| The tool does not appear in Copilot Studio | The flow must be in the same environment and saved. Refresh the tool list, and check the flow's solution is in the agent's environment. |
| The flow runs but no row is created | A required Dataverse column is unmapped. Open the flow run history and read the Add a new row step's inputs. |
| Published agent shows an old version | Changes require a fresh Publish. Publish again and hard-refresh the channel link. |

## Checkpoint questions

1. What is a tool in Copilot Studio, and why does it matter for integration?
2. Name two integration failures an agent calling a backend can hit, and their fixes.
3. Which channel would you use to put an agent in front of employees at Contoso?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
