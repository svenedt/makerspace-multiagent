# System Architecture

## Overview
The Anchorage Makerspace AI Orchestration system is designed to automate and streamline operations using a modular, multi-agent approach. The infrastructure is hosted on an Unraid server with dual A4500 GPUs, supporting VMs and Docker containers for various services.

## Core Components
- **MCP VM:** Integrates with Fabman, HubSpot, Slack, and Email for membership and communication management.
- **Orchestrator VM:** Runs n8n or Node-RED for workflow automation, error handling, and approvals.
- **Data Storage VM/Docker:** Hosts MariaDB/Postgres (and optionally Redis) as the local "shadow" database.
- **AI/LLM Containers:** GPU-enabled containers (e.g., Ollama) for local inference and text generation.
- **Vector Database:** Qdrant, Weaviate, or Milvus container for RAG and historical data retrieval.

## Network Layout
- All services run internally on the Unraid server, with optional dedicated project network.
- No external ports or reverse proxies are exposed by default.

## Security
- Minimal permissions for each agent and service.
- Approval workflows for privileged actions.
- Secure credential storage using environment variables, Docker secrets, or Vaultwarden.

For a detailed breakdown, see the full white paper and roadmap in this documentation folder. 