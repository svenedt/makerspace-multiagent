# System Architecture

## Overview
The Anchorage Makerspace AI Orchestration system is designed to automate and streamline operations using a modular, multi-agent approach. The infrastructure is hosted on an Unraid server with dual A4500 GPUs, supporting VMs and Docker containers for various services.

## Core Components
- **MCP-VM (Model Context Protocol Server):** Hosts protocol servers for Fabman, Slack, HubSpot, and other integrations. Acts as a context and data broker for agent workflows, not as a membership control panel.
- **Orchestrator VM:** Runs n8n or Node-RED for workflow automation, error handling, and approvals.
- **Data Storage VM/Docker:** Hosts MariaDB/Postgres (and optionally Redis) as the local "shadow" database.
- **AI/LLM Containers:** GPU-enabled containers (e.g., Ollama) for local inference and text generation.
- **Vector Database:** Qdrant, Weaviate, or Milvus container for RAG and historical data retrieval.

## Network Layout
- All services run internally on the Unraid server, with optional dedicated project network.
- No external ports or reverse proxies are exposed by default.

## Security & Reliability
- Minimal permissions for each agent and service.
- Approval workflows for privileged actions.
- Secure credential storage using environment variables, Docker secrets, or Vaultwarden.
- **Robust error handling and graceful failure are foundational requirements for all agents, LLMs, and workflows. See `ERROR_HANDLING_POLICY.md` for details.**

For a detailed breakdown, see the full white paper and roadmap in this documentation folder.

# Audit-Driven Implementation Milestones (2024-06)

As of June 2024, the following audit-driven milestones are required for production readiness and tracked in ROADMAP.md and PHASE1_CHECKLIST.md:
- Runtime HITL enforcement and approval logging
- Runtime RBAC/ABAC checks for agent/tool/workflow execution
- Separate audit logs for privileged actions, approvals, and escalations
- Explicit escalation paths in code
- Integration with external monitoring/alerting systems
- Automated security and error handling tests
- Review and documentation of Docker/VM network isolation

See `research/AutoAgent/SECURITY_AUDIT_REPORT.md` for details. 