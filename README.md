<div align="center">

  <h1>🚀 DevOps Journey </h1>
  <p><i>Documenting my learning, hands-on labs, and real-world projects across 9 DevOps core modules.</i></p>

  <!-- Badges -->
  <a href="https://github.com/Sy7Dev/DevOps-Journey">
    <img src="https://img.shields.io/badge/Progress-2%2F9%20Modules%20Completed-brightgreen?style=for-the-badge&logo=github" alt="Progress Badge" />
  </a>
  <a href="https://coderco.io">
    <img src="https://img.shields.io/badge/Learning%20At-CoderCo-blue?style=for-the-badge" alt="CoderCo Badge" />
  </a>

</div>

<hr />

## 📌 Table of Contents
- [🎯 Overview](#-overview)
- [📊 Journey Tracker](#-journey-tracker)
- [📂 Module Breakdowns](#-module-breakdowns)
  - [1. Linux Basics & Administration](#1-linux-basics--administration)
  - [2. Bash Scripting & Automation](#2-bash-scripting--automation)
- [🛠 Repo Structure](#-repo-structure)
- [📬 Connect With Me](#-connect-with-me)

---

## 🎯 Overview

Welcome to my DevOps showcase repository! This repository acts as a central hub for my notes, practice scripts, architecture diagrams, and mini-projects completed during my **DevOps Journey**.

The goal of this repo is to maintain clean, reproducible documentation as I transition from foundational systems administration to cloud-native automation and orchestration.

---

## 📊 Journey Tracker

| Module # | Module Name | Status | Main Topics Covered | Folder Link |
| :---: | :--- | :---: | :--- | :---: |
| **01** | **Linux** | ✅ `Completed` | File Permissions, User Management, CLI Tools | [`/01-linux`](./01-linux) |
| **02** | **Bash Scripting** | ✅ `Completed` | Shell Variables, Loops, Cron Jobs, Automation | [`/02-bash`](./02-bash) |
| **03** | **Git & GitHub** | ⏳ `In Progress` | Version Control, Branching, Pull Requests | [`/03-git`](./03-git) |
| **04** | **Networking** | ⏸️ `Upcoming` | TCP/IP, DNS, Subnetting, OSI Model | [`/04-networking`](./04-networking) |
| **05** | **Containers & Docker** | ⏸️ `Upcoming` | Dockerfiles, Docker Compose, Volumes | [`/05-docker`](./05-docker) |
| **06** | **AWS Cloud** | ⏸️ `Upcoming` | EC2, S3, IAM, VPC, CloudWatch | [`/06-aws`](./06-aws) |
| **07** | **Terraform (IaC)** | ⏸️ `Upcoming` | HCL Syntax, Modules, State Files | [`/07-terraform`](./07-terraform) |
| **08** | **CI/CD Pipelines** | ⏸️ `Upcoming` | GitHub Actions, Automation, Testing | [`/08-cicd`](./08-cicd) |
| **09** | **Kubernetes** | ⏸️ `Upcoming` | Pods, Deployments, Services, Ingress | [`/09-kubernetes`](./09-kubernetes) |

---

## 📂 Module Breakdowns

<details>
<summary><h3>1. Linux Basics & Administration 🐧</h3></summary>

### 📖 Summary
Learned foundational system administration skills, working with the command-line interface, managing files, system permissions, and monitoring processes.

### 🔑 Key Skills & Commands
- **File System Navigation:** `ls`, `cd`, `find`, `grep`, `awk`, `sed`
- **Permissions & Security:** `chmod`, `chown`, `sudo`, `umask`
- **Process Management:** `ps`, `top`, `htop`, `kill`, `systemctl`

### 💻 Featured Practice / Mini Project
* **Task:** System Health Audit & Security Hardening script setup.
* **Location:** [`./01-linux/README.md`](./01-linux)

---
</details>

<details>
<summary><h3>2. Bash Scripting & Automation 🐚</h3></summary>

### 📖 Summary
Automated repetitive system tasks using shell scripts. Focused on writing modular, clean code utilizing control logic, subroutines, and scheduled tasks via Cron.

### 🔑 Key Skills & Concepts
- **Script Logic:** Positional arguments, `if/else`, `case` statements, `for`/`while` loops.
- **Automation:** Automation scripts, scheduling background jobs with `cron` / `crontab`.
- **Output Handling:** Input redirection (`<`, `>`), piping (`|`), and error logs (`2>&1`).

### 💻 Featured Practice / Mini Project
* **Script:** [Automated System Backup & Alert Script](./02-bash/backup_script.sh)
* **Description:** A bash script that backs up selected directories, compresses them to a `.tar.gz` file, and sends a log output.

---
</details>

---

## 🛠 Repo Structure

Keep your repository organized with this recommended folder layout:

```text
.
├── 01-linux/
│   ├── notes.md
│   └── commands-cheatsheet.md
├── 02-bash/
│   ├── scripts/
│   │   ├── system_audit.sh
│   │   └── backup_script.sh
│   └── notes.md
├── 03-git/
├── 04-networking/
├── 05-docker/
├── 06-aws/
├── 07-terraform/
├── 08-cicd/
└── 09-kubernetes/
