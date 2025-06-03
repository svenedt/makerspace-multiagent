# Agent Definition Template

Use this template to define new agents in the system. Copy and fill out for each new agent.

---

## Agent Name

## Description
- Briefly describe the agent's purpose and main responsibilities.

## Rules/Policies
- List the rules, policies, or behaviors the agent must follow.
  - (e.g., Only respond to membership queries for the requesting user)

## Tools/Resources
- APIs, secrets, MCPs, and other resources the agent can access.
  - (e.g., Slack API token, Fabman MCP, Redis DB)

## Permissions
- What actions/data is the agent allowed to access or modify?
  - (e.g., Read-only access to user table, can trigger door code generation)

## Configuration
- Any configurable parameters (temperature, model, max tokens, etc.)
  - (e.g., LLM temperature=0.2, max tokens=512)

## Error Handling & Fallbacks
- How should the agent handle errors, retries, and failures?
  - (e.g., Retry up to 3 times, escalate to human if still failing)

## Audit & Logging
- What actions should be logged, and where?
  - (e.g., Log all privileged actions to central DB, include timestamp and user)

## Human-in-the-Loop (HITL) Requirements
- When does the agent require explicit human approval?
  - (e.g., For membership changes, key grants, or sensitive actions)

## Example Use Cases
- List a few example tasks or scenarios for this agent.

--- 