# devops-ansible
🏢 Enterprise Infrastructure Automation Lab

Ansible • Taskfile • CI/CD • Multi-Environment DevOps Project

---

📌 Project Overview

This project simulates real enterprise infrastructure operations using modern DevOps practices.

The goal is to reproduce how large companies manage hundreds of Linux servers, virtual machines, containers, and shared services using Infrastructure as Code (IaC).

Instead of manual system administration, all operations are automated through:

- Ansible → Infrastructure automation
- Taskfile (TaskGo) → Standardized developer workflow
- GitHub Actions → Continuous Integration (CI)
- Multi-environment architecture → dev / staging / production

This repository represents a production-style DevOps automation platform, not a simple learning project.

---

🎯 What This Project Simulates

A company infrastructure including:

- Linux servers
- Docker hosts
- Web servers
- Databases
- Shared file servers (Samba)
- Backup automation
- Environment separation
- Secure secrets management

All deployments are repeatable, idempotent, and automated.

---

🧱 Architecture

enterprise-ansible-lab/
│
├── ansible/
│   ├── inventory/
│   │   ├── dev/
│   │   ├── staging/
│   │   └── production/
│   │
│   ├── playbooks/
│   │   ├── site.yml
│   │   ├── backup.yml
│   │   └── docker.yml
│   │
│   └── roles/
│       ├── webserver/
│       ├── database/
│       ├── docker/
│       ├── file-share/
│       └── backup/
│
├── Taskfile.yml
└── .github/workflows/

---

⚙️ Technologies Used

- Ansible Roles Architecture
- Handlers & Tags
- Ansible Vault (Secrets Management)
- Multi-Environment Inventory
- Docker Automation
- Linux Server Provisioning
- Backup Automation Strategy
- GitHub Actions CI/CD
- Taskfile Workflow Automation

---

🌍 Environments

Environment| Purpose
dev| Development & testing
staging| Pre-production validation
production| Real deployment configuration

Each environment has independent:

- hosts
- variables
- secrets
- configurations

---

🚀 How Deployment Works

Concept

Instead of running long Ansible commands manually:

ansible-playbook .... complicated command ....

We standardize operations using Taskfile.

Developers and CI pipelines run the same commands.

---

🧩 Taskfile Commands

✅ 1. Lint Infrastructure

Validate Ansible quality:

task lint

Runs:

- ansible-lint
- best practice validation

---

✅ 2. Syntax Check

Verify playbooks before deployment:

task syntax

Ensures infrastructure is valid without changing servers.

---

✅ 3. Deploy Development Environment

task deploy-dev

Deploys:

- Web servers
- Database services
- Docker hosts
- File sharing
- Backup configuration

---

✅ 4. Deploy Staging

task deploy-staging

Used before production release.

---

✅ 5. Deploy Production

task deploy-prod

Runs with Ansible Vault protection for secrets.

---

✅ 6. Run Backups Only

task backup

Executes backup automation without redeploying infrastructure.

---

🔐 Secrets Management

Sensitive data is encrypted using:

ansible-vault

Example:

inventory/production/group_vars/vault.yml

Secrets never appear in plain text.

---

🔄 CI/CD Pipeline

GitHub Actions automatically:

1. Checks out repository
2. Installs Ansible
3. Runs Taskfile commands
4. Executes lint & syntax validation
5. Prevents broken infrastructure merges

Workflow:

Developer Push
      ↓
GitHub Actions
      ↓
task lint
task syntax
      ↓
Validated Infrastructure

---

🧠 DevOps Practices Demonstrated

- Infrastructure as Code
- Idempotent Deployments
- Automation First Operations
- Environment Separation
- Secure Secret Handling
- Standardized Developer Workflow
- CI Validation Pipeline
- Modular Role Design

---

📈 Why This Project Matters

This repository demonstrates real skills required for:

- DevOps Engineer
- Site Reliability Engineer (SRE)
- Linux System Administrator
- Platform Engineer

It reflects how companies automate infrastructure at scale.

---

🛠 Requirements

- Linux / macOS
- Python 3.10+
- Ansible
- Taskfile

Install Task:

sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d

---

▶️ Quick Start

Clone project:

git clone <repo>
cd enterprise-ansible-lab

Run validation:

task lint

Deploy infrastructure:

task deploy-dev

---

📌 Future Extensions

- Kubernetes deployment
- GitOps workflow
- Terraform integration
- Monitoring stack (Prometheus + Grafana)
- Automated rollback strategies

---

👨‍💻 Author

DevOps Infrastructure Automation Project
Built as a production-style learning and portfolio environment.

---
