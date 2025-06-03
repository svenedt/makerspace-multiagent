# Agent Registry

This document tracks all defined agents in the system, their roles, status, and key properties. Update this registry as new agents are created or existing ones are modified.

---

## Agent Registry Table

| Agent Name      | Description                        | Status   | Permissions         | HITL Required | Example Use Cases           |
|-----------------|------------------------------------|----------|---------------------|---------------|----------------------------|
| (example) SlackBotAgent | Answers member queries in Slack | Active   | Read-only user info | No            | Membership status, FAQs     |
|                 |                                    |          |                     |               |                            |

---

## Agent Details

### Agent Name: SlackBotAgent
- **Description:** Answers member queries in Slack, provides general info, and routes privileged requests for approval.
- **Rules/Policies:**
  - Only responds to the requesting user.
  - Never exposes sensitive data.
  - Escalates privileged requests to board agent.
- **Tools/Resources:** Slack API token, orchestrator API.
- **Permissions:** Read-only access to user info.
- **Configuration:** N/A
- **Error Handling & Fallbacks:** Retries up to 2 times, escalates on failure.
- **Audit & Logging:** Logs all requests and escalations.
- **HITL Requirements:** No (for general queries); Yes (for privileged actions).
- **Example Use Cases:** "What is my membership status?", "How do I sign up for a class?"

---

(Add new agent entries below as needed) 