# 🐧 Linux Fundamentals

> My structured, hands-on journey through Linux — the foundation of every DevOps career.
> Every note, command, and script here was written and tested by me on a real system.

![Linux](https://img.shields.io/badge/OS-Ubuntu%2022.04-E95420?logo=ubuntu&logoColor=white)
![Shell](https://img.shields.io/badge/Shell-Bash-4EAA25?logo=gnubash&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active%20Learning-brightgreen)

## Why This Repo Exists

You cannot administer Kubernetes clusters, write Terraform, or debug CI/CD pipelines without being comfortable in a Linux terminal. This repository documents my mastery of Linux fundamentals as the first stage of my DevOps roadmap: **Linux → Docker → Kubernetes (CKA) → Terraform/AWS**.

## 📁 Repository Structure

```
linux-fundamentals/
├── 01-basics/              # Filesystem hierarchy, navigation, help systems
├── 02-file-management/     # Creating, copying, moving, finding files
├── 03-text-processing/     # grep, sed, awk, cut, sort, pipes & redirection
├── 04-users-permissions/   # Users, groups, chmod, chown, sudo, umask
├── 05-processes/           # ps, top, kill, jobs, systemd services
├── 06-networking/          # ip, ss, curl, dig, SSH, firewalls (ufw)
├── 07-package-management/  # apt, dpkg, repositories
├── 08-storage/             # Disks, partitions, mounting, LVM basics
├── 09-shell-scripting/     # Variables, loops, conditionals, real scripts
└── 10-logs-monitoring/     # journalctl, /var/log, cron, system health
```

Each folder contains:
- `notes.md` — concepts explained in my own words
- `commands.md` — a tested command reference with output examples
- `practice/` — exercises and scripts I wrote

## 🗺️ Learning Path

### Module 1 — Basics
- Filesystem Hierarchy Standard: what lives in `/etc`, `/var`, `/home`, `/usr`, `/opt`
- Navigation: `pwd`, `cd`, `ls -la`, absolute vs relative paths
- Getting help: `man`, `--help`, `tldr`

### Module 2 — File Management
- `touch`, `mkdir -p`, `cp -r`, `mv`, `rm -rf` (and why to fear it)
- Links: hard links vs symbolic links (`ln`, `ln -s`)
- Finding things: `find /var -name "*.log" -mtime -7`, `locate`, `which`

### Module 3 — Text Processing (the DevOps superpower)
- Pipes and redirection: `|`, `>`, `>>`, `2>&1`
- `grep -rEi`, `sed 's/old/new/g'`, `awk '{print $1, $3}'`
- `sort | uniq -c | sort -rn` — the log-analysis one-liner pattern

### Module 4 — Users & Permissions
- `useradd`, `usermod`, `groupadd`, `/etc/passwd`, `/etc/shadow`
- Permission model: `rwx` for user/group/other, octal notation (`chmod 644`, `755`)
- `chown`, `sudo`, `visudo`, `umask`

### Module 5 — Processes & Services
- `ps aux`, `top`/`htop`, foreground/background jobs, signals (`kill -9` vs `-15`)
- **systemd**: `systemctl start|stop|enable|status`, writing a basic unit file

### Module 6 — Networking
- `ip addr`, `ip route`, `ss -tulpn`, `ping`, `curl -I`, `dig`
- SSH: key-based auth, `ssh-keygen`, `~/.ssh/config`, `scp`
- Firewall basics with `ufw`

### Module 7 — Package Management
- `apt update` vs `apt upgrade`, `apt install`, `apt search`, `dpkg -l`

### Module 8 — Storage
- `lsblk`, `df -h`, `du -sh`, `fdisk`, mounting with `/etc/fstab`
- LVM concepts: PV → VG → LV

### Module 9 — Shell Scripting
- Shebang, variables, `$1`/`$@`, exit codes, `if`/`case`, `for`/`while`
- Real scripts in this repo: backup script, log rotation helper, disk-space alert

### Module 10 — Logs & Monitoring
- `journalctl -u nginx --since "1 hour ago"`, `/var/log/syslog`, `dmesg`
- Scheduling with `cron` (`crontab -e`) and systemd timers

## ⚡ Quick Reference — My Most-Used Commands

```bash
# What is eating my disk?
du -sh /* 2>/dev/null | sort -rh | head -10

# Which process is listening on port 8080?
ss -tulpn | grep :8080

# Find errors in a service log from the last boot
journalctl -u myapp -b -p err

# Safely test a permissions change
stat -c "%a %n" file.txt && chmod 640 file.txt && stat -c "%a %n" file.txt
```

## 🎯 Goals & Progress

- [x] Modules 1–4: core navigation, files, text processing, permissions
- [ ] Modules 5–7: processes, networking, packages
- [ ] Modules 8–10: storage, scripting projects, monitoring
- [ ] Capstone: provision and harden a fresh Ubuntu server end-to-end, documented as a runbook

## 📚 Resources I'm Learning From

- *The Linux Command Line* — William Shotts (free book)
- Linux Journey (linuxjourney.com)
- OverTheWire: Bandit (hands-on practice)
- `man` pages — always the source of truth

---

**Part of my DevOps roadmap:** [`linux-fundamentals`](../../) → [`kubernetes-labs`](https://github.com/ijlalpk/kubernetes-labs) → [`terraform-aws-basics`](https://github.com/ijlalpk/terraform-aws-basics) → [`100-days-of-devops`](https://github.com/ijlalpk/100-days-of-devops)

*Maintained by [Ijlal (@ijlalpk)](https://github.com/ijlalpk) — feedback and suggestions welcome via Issues.*
