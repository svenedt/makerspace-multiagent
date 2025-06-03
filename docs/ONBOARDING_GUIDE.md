# Onboarding Guide

Welcome to the makerspace-multiagent project! This guide will help new contributors and administrators get up to speed quickly and effectively.

---

## Project Overview
- makerspace-multiagent is a modular, multi-agent orchestration system for automating makerspace operations using LLMs, agents, and secure workflows.

## Repository Structure
- `repo/` — Main code, docs, workflows, and scripts
- `db/`, `redis/`, `vector_db/`, `docker/`, `vm_disks/`, `backups/`, `tmp/`, `secrets/` — Data, storage, and infrastructure
- See `README.md` for a full directory breakdown

## Key Documentation
- `README.md` — Project intro and structure
- `JOURNAL.md` — Living changelog and decision log
- `ARCHITECTURE.md` — System architecture
- `ROADMAP.md` — Project phases and milestones
- `AGENT_TEMPLATE.md`, `AGENT_REGISTRY.md` — Agent definitions and registry
- `WORKFLOW_TEMPLATE.md` — Workflow definitions
- `SECURITY_POLICY.md` — Security best practices
- `MONITORING_ALERTING_PLAN.md` — Monitoring and alerting
- `ERROR_HANDLING_POLICY.md` — Error handling and graceful failure
- `AGENT_POLICY.md` — Agent/LLM spin-up policy

## Getting Started
1. Clone the repository and review the `README.md`.
2. Read through the `JOURNAL.md` for project history and context.
3. Familiarize yourself with the architecture and roadmap.
4. Review the agent and workflow templates before adding new components.
5. Follow security and error handling policies at all times.

## Setup Steps
- Set up your development environment (Python, Node.js, Docker, etc. as needed)
- Install required dependencies (see future `requirements.txt` or `package.json`)
- Configure secrets and environment variables (never commit secrets to git)
- Run or test workflows as described in the docs

## Best Practices
- Commit early and often, with clear messages
- Update documentation and the journal for all significant changes
- Use branches and pull requests for new features or fixes
- Review and follow all project policies

## Where to Find Help
- Check the documentation in `repo/docs/`
- Review past decisions and context in `JOURNAL.md`
- Open an issue or contact a project admin for questions

--- 