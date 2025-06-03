# Project Roadmap

This roadmap outlines the step-by-step phases for building the Anchorage Makerspace AI Orchestration system.

## Phase 1: Foundation & Environment Setup
- Prepare Unraid server, confirm GPU and network setup
- Spin up/validate VMs (MCP-VM as Model Context Protocol server, Data Storage, Orchestrator)
- Install Docker, deploy n8n/Node-RED, test basic workflow
- **Implement robust error handling and graceful failure mechanisms from the start. See `ERROR_HANDLING_POLICY.md`.**

## Phase 2: Data Integration & Local DB
- Set up MariaDB/Postgres, create schema and tables
- Sync membership data from Fabman/HubSpot via MCP-VM protocol servers
- Integrate Slack user data into the local DB

## Phase 3: Basic Workflows & Automation
- Slack bot for membership queries
- Monthly reporting workflow
- Error handling and notifications

## Phase 4: Agent Role Separation & Approvals
- Implement safe-check/manager agent for privileged actions
- Credential segregation and approval logging

## Phase 5: LLMs & RAG
- Deploy LLM container (Ollama, etc.)
- Set up vector DB (Qdrant/Weaviate)
- Ingest Slack/email data, enable RAG queries

## Phase 6: Hierarchical Agents & Super Agent
- Define and restrict access to the super agent
- Integrate with orchestrator for workflow management

## Phase 7: Polishing & Scaling
- Web portal, SSO, advanced policies
- Data retention, monitoring, and observability

See `ARCHITECTURE.md`, `ERROR_HANDLING_POLICY.md`, and the white paper for more details on each phase.

# Audit-Driven Implementation Milestones (2024-06)

The following milestones are required for production readiness, as identified in the 2024-06 Security & Code Audit Report (see `research/AutoAgent/SECURITY_AUDIT_REPORT.md`). These items must be completed in addition to the phase-based roadmap above:

- Implement runtime Human-in-the-Loop (HITL) enforcement and approval logging for sensitive actions
- Add runtime RBAC/ABAC checks for agent, tool, and workflow execution
- Separate audit logs for privileged actions, approvals, and escalations
- Implement explicit escalation paths in code (e.g., escalate_to_admin, notification system)
- Integrate with external monitoring and alerting systems (e.g., Prometheus, Grafana, Loki)
- Add automated security and error handling tests (consider CI/CD integration)
- Review and document Docker/VM network isolation and privilege boundaries

These milestones are tracked in the project checklist and must be referenced in all relevant design and implementation discussions. 