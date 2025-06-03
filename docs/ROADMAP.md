# Project Roadmap

This roadmap outlines the step-by-step phases for building the Anchorage Makerspace AI Orchestration system.

## Phase 1: Foundation & Environment Setup
- Prepare Unraid server, confirm GPU and network setup
- Spin up/validate VMs (MCP, Data Storage, Orchestrator)
- Install Docker, deploy n8n/Node-RED, test basic workflow

## Phase 2: Data Integration & Local DB
- Set up MariaDB/Postgres, create schema and tables
- Sync membership data from Fabman/HubSpot
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

See `ARCHITECTURE.md` and the white paper for more details on each phase. 