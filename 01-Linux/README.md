# 🐧 Module 01: Linux Basics & Administration

> **Status:** ✅ Completed   
> **Main Challenge:** OverTheWire Bandit (Levels 0 ➔ 20) ✅ Completed 

---

## 📌 Module Overview

This module covers fundamental Linux administration, command-line operations, process control, text processing, and security permissions required for cloud and DevOps engineering.

### 🎯 Core Goals
- Navigate and manage the Linux file system via CLI.
- Implement file permissions, ownership, and security (`chmod`, `chown`, `sudo`).
- Monitor and control system processes using `ps`, `top`, `htop`, and background signals.
- Parse log files and text streams using pipelines (`grep`, `awk`, `sed`, `find`).
- Solve **OverTheWire Bandit (Levels 0–20)** to prove command-line proficiency.

---

## 🛠️ Core Linux Hands-On Tasks

<details>
<summary><b>Task 1: System Verification & Navigation</b></summary>

### System Check Commands
```bash
uname -a    # Display system architecture and kernel version
whoami      # Display active user
pwd         # Output current directory
```
---
</details>

---

## 🎮 OverTheWire Bandit: Hands-On Milestone Solutions

<details>
<summary><b>Bandit Level 00 ➔ 01: Remote Access & SSH Authentication</b></summary>

### 🎯 Objective
Establish an SSH connection to a remote server using a non-standard port (`2220`) and read the first password from `readme`.

### 🛠️ Commands
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
cat readme
```

<details>
<summary><b>Bandit Level 05 ➔ 06: Advanced Directory Search Filters</b></summary>

### 🎯 Objective
Locate a specific file nested within multiple subdirectories matching exact criteria: human-readable, 1033 bytes in size, and non-executable.

### 🛠️ Commands
```bash
cd inhere
find . -type f -size 1033c ! -executable
```

<details>
<summary><b>Bandit Level 10 ➔ 11: Base64 Payload Processing</b></summary>

### 🎯 Objective
Decode base64-encoded string data contained within `data.txt` to retrieve cleartext credentials.

### 🛠️ Commands
```bash
base64 -d data.txt
```
<details>
<summary><b>Bandit Level 15 ➔ 16: Encrypted TLS/SSL Sockets</b></summary>

### 🎯 Objective
Transmit the current password to port `30001` on `localhost` over an active SSL/TLS encrypted connection.

### 🛠️ Commands
```bash
openssl s_client -connect localhost:30001 -ign_eof
```
<details>
<summary><b>Bandit Level 20 ➔ 21: Local IPC & SetUID Privilege Escalation</b></summary>

### 🎯 Objective
Spawn an active local TCP listener to pass credentials to a SetUID binary (`suconnect`), which verifies input before revealing the next level's credentials.

### 🛠️ Commands
```bash
echo "4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA" | nc -l -p 53923 &
./suconnect 53923
```
