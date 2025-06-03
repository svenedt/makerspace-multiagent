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