# Server MCP API Protocol — Design Notes

These notes outline the design principles and example structure for the Server MCP (Model Context Protocol) API, which will serve as the secure gateway for agent/LLM/system interactions. Revisit and expand as needed during implementation.

---

## Core Design Principles
- RESTful or RPC-style endpoints (e.g., `/api/backup/run`, `/api/agent/create`)
- Authentication & Authorization: API key, JWT, or mTLS for all requests
- Input Validation: Strict schema validation for all payloads
- Structured JSON responses with status, result, and error fields
- Audit Logging: Every request and response is logged
- HITL (Human-in-the-Loop) support for sensitive actions

## Example API Endpoints
| Endpoint                | Method | Purpose                        | Required Role | HITL | Example Payload/Response         |
|-------------------------|--------|--------------------------------|--------------|------|----------------------------------|
| `/api/backup/run`       | POST   | Run backup script              | admin        | Yes  | `{ "target": "db" }`             |
| `/api/agent/create`     | POST   | Spin up new agent/LLM          | admin        | Yes  | `{ "type": "event", ... }`       |
| `/api/logs/fetch`       | GET    | Fetch system logs              | admin        | No   | `?since=2024-05-10`              |
| `/api/tool/list`        | GET    | List available tools           | any          | No   |                                  |
| `/api/health/check`     | GET    | Check health of a service      | any          | No   |                                  |

## Request/Response Example
**Request:**
```http
POST /api/backup/run
Authorization: Bearer <token>
Content-Type: application/json

{
  "target": "db"
}
```
**Response (Success):**
```json
{
  "status": "success",
  "result": "Backup started for db. Job ID: 12345",
  "timestamp": "2024-05-10T18:30:00Z"
}
```
**Response (HITL Required):**
```json
{
  "status": "pending_approval",
  "result": "Backup request submitted. Awaiting admin approval.",
  "approval_id": "abcde12345",
  "timestamp": "2024-05-10T18:30:00Z"
}
```
**Response (Error):**
```json
{
  "status": "error",
  "error": "Permission denied: insufficient role",
  "timestamp": "2024-05-10T18:30:00Z"
}
```

## Security Features
- Authentication: API keys, JWTs, or mTLS
- Authorization: Role/permission checks for every endpoint
- Input Validation: Strict schema validation
- Rate Limiting: Prevent abuse or accidental overload
- Audit Logging: Every request, approval, and result is logged

## HITL (Human-in-the-Loop) Workflow
1. Agent/LLM makes a request to a HITL-protected endpoint.
2. API returns `pending_approval` and notifies the human/admin.
3. Human/admin reviews and approves/denies the request.
4. API executes the action and notifies the agent/LLM of the result.

## Extensibility
- New tools/APIs can be added by registering new endpoints and updating the Tool Registry.
- Permissions and HITL requirements can be adjusted per tool/endpoint.

---
Revisit these notes when ready to design and implement the Server MCP API. 