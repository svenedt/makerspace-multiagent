# Tool Registry

This document tracks all system tools, APIs, and capabilities available to the Admin LLM and agents. Update this registry as new tools are added or existing ones are modified.

---

## Tool Registry Table

| Tool Name     | Description                  | Endpoint/Command      | Required Role | HITL Required | Example Usage                |
|---------------|-----------------------------|----------------------|--------------|---------------|-----------------------------|
| run_backup    | Run the system backup script | /api/backup/run      | admin        | Yes           | POST /api/backup/run {"target": "db"} |
|               |                             |                      |              |               |                             |

---

## Tool Details

### Tool Name: run_backup
- **Description:** Run the system backup script for a specified target (e.g., database, files).
- **Endpoint/Command:** /api/backup/run (POST)
- **Required Role:** admin
- **HITL Required:** Yes
- **Example Usage:**
  ```json
  POST /api/backup/run { "target": "db" }
  ```
- **Notes:** Only available to Admin LLM or with explicit human approval. All invocations are logged.

---

(Add new tool entries below as needed) 