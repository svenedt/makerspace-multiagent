# Phase 1: Foundation & Environment Setup Checklist

- [ ] Update Unraid server and confirm NVIDIA plugin, GPU recognition
- [ ] Plan network configuration for VMs/containers
- [ ] Validate MCP VM (ensure OS is up to date)
- [ ] Create/validate Data Storage VM (install MariaDB/Postgres)
- [ ] Set up backup/snapshot routines for Data VM
- [ ] Create Orchestrator VM (Ubuntu or similar)
- [ ] Install Docker and docker-compose on Orchestrator VM
- [ ] Deploy n8n (or Node-RED) container
- [ ] Configure baseline security (username/password, SSL)
- [ ] Create and test a minimal 'Hello World' workflow 

# Audit-Driven Implementation Checklist (2024-06)

- [ ] Implement runtime HITL enforcement and approval logging
- [ ] Add runtime RBAC/ABAC checks for agent/tool/workflow execution
- [ ] Separate audit logs for privileged actions, approvals, and escalations
- [ ] Implement explicit escalation paths in code (escalate_to_admin, notification system)
- [ ] Integrate with external monitoring/alerting systems (Prometheus, Grafana, Loki, etc.)
- [ ] Add automated security and error handling tests (CI/CD)
- [ ] Review and document Docker/VM network isolation and enforcement 