#  Module 01: Linux Basics & Administration

> **Status:** : Completed   
> **Main Challenge:** OverTheWire Bandit (Levels 0 ➔ 20) : Completed 

---

##  **Module Overview**

This module covers fundamental Linux administration, command-line operations, process control, text processing, and security permissions required for cloud and DevOps engineering.

###  **Core Goals**
- Navigate and manage the Linux file system via CLI.
- Implement file permissions, ownership, and security (`chmod`, `chown`, `sudo`).
- Monitor and control system processes using `ps`, `top`, `htop`, and background signals.
- Parse log files and text streams using pipelines (`grep`, `awk`, `sed`, `find`).
- Solve **OverTheWire Bandit (Levels 0–20)** to prove command-line proficiency.

---

##  **Core Linux Hands-On Tasks**

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

## **OverTheWire Bandit: Hands-On Solutions**

<details>
<summary><b>Bandit Level 00 ➔ 01: Remote Access & SSH Authentication</b></summary>

### **Objective**
Establish an SSH connection to a remote server using a non-standard port (`2220`) and read the first password from `readme`.

### **Commands**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
cat readme
```
---

</details>

<details>
<summary><b>Bandit Level 01 ➔ 02: Handling Special Filenames</b></summary>

### **Objective**
Read the password stored in a file named `-` located in the home directory.

### **Commands**
```bash
cat ./-
```
---

</details>

<details>
<summary><b>Bandit Level 02 ➔ 03: Spaces in Filenames</b></summary>

### **Objective**
Read the password stored in a file named `spaces in this filename` located in the home directory.

### **Commands**
```bash
cat "spaces in this filename"
# OR
cat spaces\ in\ this\ filename
```
---

</details>

<details>
<summary><b>Bandit Level 03 ➔ 04: Hidden Files</b></summary>

### **Objective**
Find the password stored in a hidden file inside the `inhere` directory.

### **Commands**
```bash
cd inhere
ls -la
cat .hidden
```
---

</details>

<details>
<summary><b>Bandit Level 04 ➔ 05: Human-Readable File Identification</b></summary>

### **Objective**
Identify the only human-readable ASCII file out of multiple binary files stored in the `inhere` directory.

### **Commands**
```bash
cd inhere
file ./*
cat ./-file07
```
---


</details>

<details>
<summary><b>Bandit Level 05 ➔ 06: Advanced Directory Search Filters</b></summary>

### **Objective**
Locate a specific file nested within multiple subdirectories matching exact criteria: human-readable, 1033 bytes in size, and non-executable.

### **Commands**
```bash
cd inhere
find . -type f -size 1033c ! -executable
```
---

</details>

<details>
<summary><b>Bandit Level 06 ➔ 07: System-Wide Search Filters</b></summary>

### **Objective**
Find a file somewhere on the server owned by user `bandit7`, group `bandit6`, and exactly 33 bytes in size.

### **Commands**
```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```
---

</details>

<details>
<summary><b>Bandit Level 07 ➔ 08: Pattern Matching in Large Files</b></summary>

### **Objective**
Extract the password located next to the word "millionth" inside `data.txt`.

### **Commands**
```bash
grep "millionth" data.txt
```
---

</details>

<details>
<summary><b>Bandit Level 08 ➔ 09: Unique Line Extraction</b></summary>

### **Objective**
Find the only line of text that occurs exactly once inside `data.txt`.

### **Commands**
```bash
sort data.txt | uniq -u
```
---

</details>

<details>
<summary><b>Bandit Level 09 ➔ 10: Human-Readable Strings in Binaries</b></summary>

### **Objective**
Find the password preceded by several `=` characters inside a binary file.

### **Commands**
```bash
strings data.txt | grep "=="
```
---


</details>

<details>
<summary><b>Bandit Level 10 ➔ 11: Base64 Payload Processing</b></summary>

### **Objective**
Decode base64-encoded string data contained within `data.txt` to retrieve cleartext credentials.

### **Commands**
```bash
base64 -d data.txt
```
---

</details>

<details>
<summary><b>Bandit Level 11 ➔ 12: Cipher Translation (ROT13)</b></summary>

### **Objective**
Decode a text string in `data.txt` that has been rotated by 13 positions (ROT13).

### **Commands**
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
---

</details>

<details>
<summary><b>Bandit Level 12 ➔ 13: Nested Archive Extraction</b></summary>

### **Objective**
Repeatedly decompress a file that has been compressed multiple times using `gzip`, `bzip2`, `tar`, and hex dumps.

### **Commands**
```bash
mkdir /tmp/mydata
cp data.txt /tmp/mydata && cd /tmp/mydata
xxd -r data.txt data.bin
file data.bin
# Decompress sequentially based on file type output
```
---

</details>

<details>
<summary><b>Bandit Level 13 ➔ 14: SSH Key Authentication</b></summary>

### **Objective**
Authenticate as user `bandit14` on `localhost` using a private SSH key stored in `sshkey.private`.

### **Commands**
```bash
ssh -i sshkey.private bandit14@localhost -p 2220
cat /etc/bandit_pass/bandit14
```
---

</details>

<details>
<summary><b>Bandit Level 14 ➔ 15: Local Port Submission</b></summary>

### **Objective**
Submit the current level password to port `30000` on `localhost` to retrieve the next password.

### **Commands**
```bash
nc localhost 30000
# Paste Level 14 password
```
---


</details>

<details>
<summary><b>Bandit Level 15 ➔ 16: Encrypted TLS/SSL Sockets</b></summary>

### **Objective**
Transmit the current password to port `30001` on `localhost` over an active SSL/TLS encrypted connection.

### **Commands**
```bash
openssl s_client -connect localhost:30001 -ign_eof
```
---

</details>

<details>
<summary><b>Bandit Level 16 ➔ 17: Port Scanning & RSA Key Retrieval</b></summary>

### **Objective**
Scan ports `31000-32000` on `localhost` for open SSL services, then submit credentials to obtain an RSA private key.

### **Commands**
```bash
nmap -p 31000-32000 localhost
openssl s_client -connect localhost:31790 -ign_eof
# Paste Level 16 password to receive the private key
```
---

</details>

<details>
<summary><b>Bandit Level 17 ➔ 18: File Comparison (Diffing)</b></summary>

### **Objective**
Compare `passwords.old` and `passwords.new` to find the single line that changed.

### **Commands**
```bash
diff passwords.old passwords.new
```
---

</details>

<details>
<summary><b>Bandit Level 18 ➔ 19: Bypassing Shell Escape Restrictions</b></summary>

### **Objective**
Log in via SSH when `.bashrc` automatically disconnects standard interactive shell sessions.

### **Commands**
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```
---

</details>

<details>
<summary><b>Bandit Level 19 ➔ 20: Basic SetUID Execution</b></summary>

### **Objective**
Use a SetUID binary (`bandit20-do`) to read `/etc/bandit_pass/bandit20`.

### **Commands**
```bash
./bandit20-do cat /etc/bandit_pass/bandit20
```
---


</details>

<details>
<summary><b>Bandit Level 20 ➔ 21: Local IPC & SetUID Privilege Escalation</b></summary>

### **Objective**
Spawn an active local TCP listener to pass credentials to a SetUID binary (`suconnect`), which verifies input before revealing the next level's credentials.

### **Commands**
```bash
echo "4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA" | nc -l -p 53923 &
./suconnect 53923
```
---

</details>
