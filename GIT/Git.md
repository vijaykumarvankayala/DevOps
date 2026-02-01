# 🔧 Git – Distributed Version Control System

## Overview

Git is a **distributed version control system (VCS)** used to track changes in source code, infrastructure, and configuration files.  
In our organization, Git is the **single source of truth** for application code, infrastructure-as-code (Terraform), Kubernetes manifests, Helm charts, and documentation.

Git enables **collaboration, traceability, rollback, and auditability**, making it foundational to DevOps, GitOps, and CI/CD workflows.

---

## What Problems Git Solves

- Code conflicts and overwrites in multi-developer teams
- Lack of traceability for changes
- Risky manual deployments and configuration drift
- Difficulty rolling back breaking changes
- Poor auditability in regulated environments

---

## Key Concepts

| Concept | Description |
|------|-------------|
| Repository (Repo) | Collection of files and history |
| Commit | Snapshot of changes |
| Branch | Isolated line of development |
| Merge | Combine changes from branches |
| Pull / Merge Request | Review and approve changes |
| Tag | Immutable reference (releases) |

---

## How Git Fits into Our Workflow

Developer
|
v
Git Commit → Branch → Merge Request
|
v
CI Pipeline (Build / Test / Scan)
|
v
Main / Release Branch
|
v
CD / GitOps Deployment

yaml
Copy code

Git acts as the **control plane for change**.

---

## Benefits

| Area | Benefit |
|---|---|
| Collaboration | Multiple developers work safely in parallel |
| Reliability | Easy rollback to known-good states |
| Auditability | Full change history with author and timestamp |
| Velocity | Faster development with isolated branches |
| DevOps | Enables CI/CD and GitOps workflows |
| Security | Controlled access and reviewed changes |

---

## Branching Strategy (Standard)

### 🌱 Common Model
main (or master)
│
├── develop
│ ├── feature/*
│ ├── bugfix/*
│
├── release/*
└── hotfix/*

yaml
Copy code

### Guidelines
- `main` → production-ready code
- `feature/*` → short-lived branches
- `hotfix/*` → emergency production fixes
- No direct commits to `main`

---

## How We Use Git (Day-to-Day)

### ✍️ Development
- Create feature branches per task
- Commit small, logical changes
- Write meaningful commit messages

### 🔍 Code Review
- All changes go through Merge Requests
- Peer review is mandatory
- CI must pass before merge

### 🚀 Deployment
- Git triggers CI/CD pipelines
- GitOps tools (Argo CD) sync from Git
- Production changes are auditable and reversible

---

## Common Git Commands

### Clone a Repository
```bash
git clone https://gitlab.com/org/project.git
Create a Branch
bash
Copy code
git checkout -b feature/new-api
Commit Changes
bash
Copy code
git add .
git commit -m "Add API validation logic"
Push Changes
bash
Copy code
git push origin feature/new-api
Sync with Main
bash
Copy code
git pull origin main
Commit Message Best Practices
php-template
Copy code
<type>: <short summary>

Optional longer description
Examples

feat: add user authentication

fix: resolve memory leak in worker

chore: update dependencies

Git + CI/CD Integration
Git integrates tightly with:

GitLab CI / GitHub Actions

Jenkins

Argo CD (GitOps)

Key Principle:

If it’s not in Git, it doesn’t exist.

GitOps Usage
Kubernetes manifests stored in Git

Git is the desired state

Argo CD reconciles cluster state with Git

Rollback = revert commit

Access Control & Security
Role-based access (Developer, Maintainer)

Protected branches (main, release)

Mandatory reviews and CI checks

Signed commits (where required)

Audit logs enabled

Best Practices
Keep branches short-lived

Avoid large, long-running feature branches

Rebase before merge when possible

Never commit secrets

Use .gitignore effectively

Tag releases

Common Anti-Patterns to Avoid
❌ Direct commits to main
❌ Large, unreviewed commits
❌ Storing secrets in Git
❌ Long-lived feature branches
❌ Manual production changes

When Git Alone Is Not Enough
Binary artifact storage → use Artifactory/S3

Secrets management → use Vault / AWS Secrets Manager

Runtime configuration → use ConfigMaps / Parameters

Git manages desired state, not runtime secrets.

Summary
Git is the foundation of our DevOps and GitOps practices, providing a reliable, auditable, and collaborative way to manage code and infrastructure.
By enforcing disciplined workflows and reviews, Git enables faster delivery without compromising stability or security.

References
