# Day 05 – Linux Troubleshooting Drill: CPU, Memory, and Logs 🚨

## Objective

Today’s goal was to perform a structured Linux troubleshooting drill by:

- Capturing system health snapshots
- Monitoring CPU, memory, disk, and network usage
- Reviewing service logs
- Creating a repeatable troubleshooting runbook

This exercise helps build practical DevOps troubleshooting skills used in real production environments.

---

# Target Service / Process

For today’s troubleshooting practice, the following service was inspected:

- SSH Service (`ssh`)

Activities performed:

- Verified service health
- Monitored system resources
- Checked disk and network status
- Reviewed service logs
- Practiced troubleshooting workflow

---

# Environment Basics

| Command | Purpose |
|----------|----------|
| `uname -a` | Display Linux kernel and system information |
| `cat /etc/os-release` | Show Linux distribution details |

### Observations

- Verified system architecture and kernel version
- Confirmed Linux distribution information successfully

---

# Filesystem Sanity Checks

| Command | Purpose |
|----------|----------|
| `mkdir /tmp/runbook-demo` | Create temporary troubleshooting directory |
| `cp /etc/hosts /tmp/runbook-demo/hosts-copy` | Copy sample file for testing |
| `ls -l /tmp/runbook-demo` | Verify copied file and permissions |

### Observations

- Temporary directory created successfully
- File operations worked normally
- Permissions and file ownership displayed correctly

---

# Snapshot: CPU & Memory

| Command | Purpose |
|----------|----------|
| `top` | Monitor real-time CPU and memory usage |
| `free -h` | Display memory usage in human-readable format |
| `ps -o pid,pcpu,pmem,comm -p $(pgrep ssh \| head -1)` | Inspect SSH process resource usage |

### Observations

- CPU usage remained stable during inspection
- Memory usage was within normal range
- SSH process consumed very low resources

---

# Snapshot: Disk & IO

| Command | Purpose |
|----------|----------|
| `df -h` | Check filesystem disk usage |
| `du -sh /var/log` | Check total size of log directory |
| `vmstat 1 5` | Monitor CPU, memory, and IO statistics |

### Observations

- Disk usage was healthy with sufficient free space
- `/var/log` directory size appeared normal
- No abnormal IO wait or performance spikes observed

---

# Snapshot: Network

| Command | Purpose |
|----------|----------|
| `ss -tulpn` | Display listening ports and active network services |
| `curl -I localhost` | Test local service/network response |

### Observations

- SSH service was actively listening on expected port
- Localhost responded successfully
- No unexpected network services detected

---

# Logs Reviewed

| Command | Purpose |
|----------|----------|
| `journalctl -u ssh -n 50` | View latest SSH service logs |
| `tail -n 50 /var/log/syslog` | Display recent system log entries |

### Observations

- No recent SSH service failures detected
- System logs showed normal activity
- No repeated critical errors found

---

# Mini Troubleshooting Runbook

| Step | Action |
|------|---------|
| 1 | Identified SSH process using `pgrep ssh` |
| 2 | Monitored CPU and memory usage using `top` and `free -h` |
| 3 | Verified disk usage using `df -h` |
| 4 | Checked network ports using `ss -tulpn` |
| 5 | Reviewed SSH logs using `journalctl` |
| 6 | Inspected system logs using `tail` |
| 7 | Confirmed overall service health and responsiveness |

---

# Quick Findings

- System resources were operating normally
- SSH service remained stable and responsive
- No disk pressure or excessive memory usage observed
- Logs did not contain critical service failures

---

# If This Worsens (Next Steps)

If issues become more severe, the following actions would be taken:

## 1. Restart the SSH Service

```bash
systemctl restart ssh
```

## 2. Collect Detailed Logs

```bash
journalctl -xe
```

## 3. Trace Process Activity

```bash
strace -p <PID>
```

## 4. Investigate System Performance

```bash
iostat
vmstat
top
```

---

# Commands Practiced Summary

| Category | Command | What the Command Does |
|----------|----------|----------------------|
| Environment | `uname -a` | Displays detailed Linux kernel and system information |
| Environment | `cat /etc/os-release` | Shows Linux distribution and OS version details |
| Filesystem | `mkdir /tmp/runbook-demo` | Creates a temporary directory for testing |
| Filesystem | `cp /etc/hosts /tmp/runbook-demo/hosts-copy` | Copies a file from one location to another |
| Filesystem | `ls -l /tmp/runbook-demo` | Lists files with permissions, ownership, and sizes |
| CPU & Memory | `top` | Displays real-time CPU, memory, and process usage |
| CPU & Memory | `free -h` | Shows system memory and swap usage |
| CPU & Memory | `ps -o pid,pcpu,pmem,comm -p <PID>` | Displays resource usage for a specific process |
| Disk & IO | `df -h` | Shows disk space usage of mounted filesystems |
| Disk & IO | `du -sh /var/log` | Displays total size of the log directory |
| Disk & IO | `vmstat 1 5` | Reports CPU, memory, and IO statistics |
| Network | `ss -tulpn` | Displays active listening ports and services |
| Network | `curl -I localhost` | Tests local network/service connectivity |
| Logs | `journalctl -u ssh -n 50` | Displays recent SSH service logs |
| Logs | `tail -n 50 /var/log/syslog` | Shows latest system log entries |
| Process Monitoring | `pgrep ssh` | Finds the PID of the SSH service |
| Troubleshooting | `journalctl -xe` | Displays detailed system error logs |
| Troubleshooting | `strace -p <PID>` | Traces system calls of a running process |
| Service Management | `systemctl restart ssh` | Restarts the SSH service |
| Performance Monitoring | `iostat` | Displays CPU and disk IO statistics |

---

# What I Learned Today

- Capturing Linux system health snapshots
- Monitoring CPU and memory usage
- Investigating disk and network health
- Reading and analyzing Linux logs
- Building structured troubleshooting workflows
- Writing repeatable incident response runbooks

---

# Why Troubleshooting Runbooks Matter in DevOps

Runbooks are important because they help engineers:

- Troubleshoot issues faster
- Standardize operational procedures
- Respond consistently during incidents
- Reduce downtime in production environments
- Improve service reliability
- Create repeatable recovery workflows

Linux troubleshooting and incident response are essential skills for DevOps and System Administration roles.

---

# Practice Outcome

This hands-on troubleshooting drill improved my understanding of:

- Linux system monitoring
- Resource utilization analysis
- Service troubleshooting workflows
- Log investigation techniques
- Incident response practices
- Production troubleshooting fundamentals

These are critical day-to-day skills required in Linux-based DevOps environments.
