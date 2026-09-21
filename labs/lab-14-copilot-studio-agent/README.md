# Lab 14 — Build a Copilot Studio Agent with Topics and Knowledge

> **Course:** PL-900 Microsoft Power Platform Fundamentals Training (C1358)  
> **Topic 06:** Introduction to Power Virtual Agents (Microsoft Copilot Studio)  
> **Estimated duration:** 75 minutes

## Objective

By the end of this lab you will be able to build a conversational agent, author topics with trigger phrases and conditions, and ground it with a knowledge source.

## Scenario

Contoso's facilities inbox is full of the same questions. You build an agent in Copilot Studio, author a topic that collects the request category and priority through a branching conversation, add a knowledge source so the agent answers general questions generatively, and test both in the test chat.

## What you will build

A Copilot Studio agent, 'Contoso Facilities Assistant', with a custom topic using a question node and a condition, plus a configured knowledge source.

**Tools used:** Microsoft Copilot Studio, topics, entities, variables, knowledge sources

## Mock data

This lab uses the following files from the `data/` folder beside this README:

- [`data/facilities-faq.md`](data/facilities-faq.md)

## Before you start

- Sign in with your Microsoft 365 work or school account.
- **Check the environment picker** at the top right and confirm it names the same environment you used in Lab 1. Every portal remembers its own last-used environment.

## Steps

1. Open Copilot Studio, confirm the correct environment, and select Create > New agent.

   <https://copilotstudio.microsoft.com>

2. Name the agent 'Contoso Facilities Assistant'. Set the description to explain it helps employees raise and track facilities requests, then select Create.
3. Open the Topics tab and review the system topics — Greeting, Escalate, Fallback and End of Conversation come with every agent.
4. Select + Add a topic > From blank. Name it 'Report a Facility Issue'.
5. In the Trigger node add these trigger phrases: 'report an issue', 'something is broken', 'raise a facilities request', 'the printer is broken', 'I need a room set up'. Five or more phrases give the AI enough signal to match reliably.
6. Add a Message node that acknowledges the request: 'I can help you log that. Let me get a few details.'
7. Add a Question node asking 'What kind of issue is it?'. Set Identify to 'Multiple choice options' and add the options Maintenance, Equipment, Supplies and Room Setup. Save the response to a variable named Category.
8. Add a second Question node asking 'How urgent is this?' with the options Low, Medium, High and Urgent, saved to a variable named Priority.
9. Add a Condition node that checks whether Priority is equal to Urgent.
10. On the true branch add a Message node: 'This is urgent — I am flagging it to the facilities team immediately.' On the false branch add: 'Thanks, I have logged this as a standard request.'
11. Save the topic, then open the Test your agent pane and type 'the printer is broken'. Walk the conversation through both the Urgent and the Low path.
12. Open the Knowledge tab and add a knowledge source. Upload labs/lab-14-copilot-studio-agent/data/facilities-faq.md, or point the agent at a public website or SharePoint site.
13. Wait for the source to finish processing, then in the test chat ask a question that is NOT in any topic, such as 'what are the office opening hours?'. The agent should answer generatively from the knowledge source.
14. Note the difference: a topic is an authored, deterministic path; a knowledge source produces a generated answer grounded in content.

## Test it

Typing a trigger phrase starts your topic, the two questions branch correctly on Urgent versus Low, and a question outside every topic is answered from the knowledge source rather than falling back.

## If it doesn't work

| Symptom | What to do |
|---------|------------|
| The topic never triggers | The trigger phrases are too close to another topic's. Add more distinct phrases and re-test; check which topic actually fired in the test pane. |
| Knowledge answers are not generated | Generative answers may be disabled. Open Settings > Generative AI and confirm the knowledge source is enabled and finished processing. |
| The condition always takes the false branch | The variable is comparing against the wrong value. Confirm the Question node saves to the variable and that the condition compares the same option. |

## Checkpoint questions

1. What is the difference between a topic and a knowledge source?
2. What do trigger phrases actually do?
3. What is an entity used for in a conversation?

## Evidence to keep

Take a screenshot of your finished work and save it in this lab folder — it is the quickest way to revise what you built.

---

*PL-900 Microsoft Power Platform Fundamentals Training · C1358 · Tertiary Infotech Academy Pte Ltd · Version v8.0*
