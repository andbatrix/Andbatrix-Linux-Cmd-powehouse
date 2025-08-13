# 🐧 Linux Command Cheatsheet for DevOps  
[![DevOps Journey](https://img.shields.io/badge/DevOps-Journey-blue)](https://github.com/yourusername/devops-journey)  
[![Linux Mastery](https://img.shields.io/badge/Linux-CLI%20Mastery-green)](https://linuxjourney.com)  
[![Made by Patrice](https://img.shields.io/badge/Made%20by-Patrice%20DevOps%20Engineer-orange)](https://github.com/andbatrix)

---

## 👋 About This Repo

Hi, I’m **Patrice**—a self-taught DevOps engineer in training.  
This repo is part of my **11-month roadmap**, designed to show not just what I know, but _how_ I learn, troubleshoot, and integrate into real company workflows.

By the end, you will:

✅ Master essential Linux commands  
✅ Understand real-world usage and gotchas  
✅ Build confidence for DevOps interviews and team integration  

---

## 📚 Table of Contents

- [🔧 Navigation & Files](#navigation--files)
- [🔐 Permissions & Ownership](#permissions--ownership)
- [🔍 Search & Explore](#search--explore)
- [⚙️ Processes & Monitoring](#processes--monitoring)
- [🖥️ Services & systemctl](#services--systemctl)
- [📦 Resources](#resources)

---

## 🔧 Navigation & Files

<details>
<summary><strong>cd, ls, cp, mv, rm</strong> – File Management</summary>

### `cd` – Change Directory
```bash
cd /path/to/dir       # Go to specific directory
cd ..                 # Go up one level
cd -                  # Switch to previous directory
cd                    # Go to home directory
```
💡 Tip: Use `cd -` to quickly jump between two directories.

### `ls` – List Directory Contents
```bash
ls                    # Basic list
ls -l                 # Long list with permissions
ls -a                 # Include hidden files
ls -lah               # Long + hidden + human-readable sizes
```
⚠ Heads up: Colors may vary in SSH sessions — confirm file type with `file filename`.

### `cp` – Copy Files & Directories
```bash
cp source.txt dest.txt        # Copy file
cp -r dir1 dir2               # Copy directory recursively
cp file1 file2 /path/to/dir/  # Copy multiple files
```
💡 Tip: Always use `-r` for directories.

### `mv` – Move or Rename
```bash
mv old.txt new.txt            # Rename file
mv file.txt /tmp/             # Move file
mv *.log /var/log/            # Move all .log files
```
💡 Tip: Moving files within the same disk is instant — across disks, it copies & deletes.

### `rm` – Remove Files & Directories
```bash
rm file.txt                   # Delete file
rm -r mydir                   # Delete directory recursively
rm -rf mydir                  # Force delete (no prompt)
```
⚠ Danger Zone: `rm -rf /` can destroy your OS.  
💡 Tip: Dry run first:
```bash
echo rm -rf /path/to/delete
```

</details>

---

## 🔐 Permissions & Ownership

<details>
<summary><strong>chmod, chown, umask</strong> – Access Control</summary>

### `chmod` – Change Permissions
```bash
chmod 755 file                # rwx r-x r-x
chmod u+x script.sh           # Add execute to owner
chmod g-w file                # Remove write from group
chmod -R 644 dir              # Apply recursively
```
💡 Octal format: 4=read, 2=write, 1=execute → sum per role.

### `chown` – Change Ownership
```bash
sudo chown user file          # Change owner
sudo chown user:group file    # Change owner & group
sudo chown -R user:group dir  # Recursive
```
💡 Use `ls -l` to verify changes.

### `umask` – Default Permissions
```bash
umask                         # Show current mask
umask 027                     # Owner rwx, group r-x, others ---
```
💡 Common for secure servers: `umask 027`.

</details>

---

## 🔍 Search & Explore

<details>
<summary><strong>grep, find, tree</strong> – Locate & Visualize</summary>

### `grep` – Search Inside Files
```bash
grep "ERROR" app.log          # Search for "ERROR"
grep -i "error" app.log       # Case-insensitive
grep -R "password" /etc       # Recursive search
grep -n "main()" main.c       # Show line numbers
```
💡 `grep -Rl "text" .` lists only matching file names.

### `find` – Locate Files & Dirs
```bash
find . -name "*.log"          # Find logs in current dir
find /var/log -type f -size +10M  # Files >10MB
find . -mtime -1              # Modified in last 24h
```
💡 Combine with commands:
```bash
find . -name "*.tmp" -delete
```

### `tree` – Visualize Directory Structure
```bash
tree                          # Full tree
tree -L 2                     # Limit depth
```
💡 Install on Ubuntu:
```bash
sudo apt install tree
```

</details>

---

## ⚙️ Processes & Monitoring

<details>
<summary><strong>ps, top, htop</strong> – System Insight</summary>

### `ps` – Process Snapshot
```bash
ps aux                        # All processes
ps -u $USER                   # User’s processes
ps aux | grep nginx           # Filter
```

### `top` – Live Process Monitor
```bash
top                           # Interactive view
```
💡 Press `M` to sort by memory, `P` for CPU.

### `htop` – Better top
```bash
htop                          # Install with: sudo apt install htop
```
💡 Use `F9` to kill processes from within htop.

</details>

---

## 🖥️ Services – systemctl

```bash
sudo systemctl status nginx       # Check status
sudo systemctl start nginx        # Start service
sudo systemctl stop nginx         # Stop service
sudo systemctl enable nginx       # Enable at boot
```

💡 Use `journalctl -xe` for detailed logs when services fail.

---

## 📦 Resources

| Tool | Link |
|------|------|
| 🌐 Linux Journey | [linuxjourney.com](https://linuxjourney.com) |
| ☁️ AWS CLI Docs | [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/) |
| 🐳 Docker Docs | [Docker](https://docs.docker.com/) |
| ☸️ Kubernetes Docs | [K8s](https://kubernetes.io/docs/home/) |
| 📜 Ansible Docs | [Ansible](https://docs.ansible.com/) |


