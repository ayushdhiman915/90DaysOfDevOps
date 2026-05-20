
# Day 03 – Linux Commands Cheat Sheet 🚀

## Process Management Commands

| Command | Usage |
|---------|--------|
| `ps aux` | Show all running processes |
| `top` | Real-time process monitoring |
| `htop` | Interactive process viewer |
| `kill PID` | Stop a process by PID |
| `kill -9 PID` | Force kill a process |
| `pgrep nginx` | Find process ID by name |
| `jobs` | Show background jobs |
| `bg` | Run stopped job in background |
| `fg` | Bring background job to foreground |
| `nice -n 10 command` | Start process with priority |

---

## File System Commands

| Command | Usage |
|---------|--------|
| `pwd` | Show current directory |
| `ls -la` | List files with details |
| `cd /path` | Change directory |
| `mkdir folder` | Create directory |
| `rm -rf folder` | Remove directory forcefully |
| `cp file1 file2` | Copy files |
| `mv old new` | Move or rename files |
| `touch file.txt` | Create empty file |
| `cat file.txt` | Display file content |
| `nano file.txt` | Edit file using nano |
| `find / -name file.txt` | Search for file |
| `chmod +x script.sh` | Make script executable |
| `df -h` | Check disk usage |
| `du -sh folder` | Check folder size |

---

## Networking Troubleshooting Commands

| Command | Usage |
|---------|--------|
| `ping google.com` | Check network connectivity |
| `ip addr` | Show IP addresses |
| `curl https://example.com` | Test HTTP request |
| `dig google.com` | DNS lookup |
| `netstat -tulnp` | Show listening ports |
| `ss -tulnp` | Modern alternative to netstat |
| `traceroute google.com` | Trace network path |
| `wget URL` | Download files from internet |

---

## Log & System Monitoring Commands

| Command | Usage |
|---------|--------|
| `journalctl -xe` | View system logs |
| `tail -f /var/log/syslog` | Monitor logs live |
| `free -h` | Check memory usage |
| `uptime` | Show system uptime |
| `uname -a` | Show system information |

---

# What I Learned Today

- Important Linux troubleshooting commands
- Process and system monitoring basics
- Networking diagnostic commands
- File system navigation and management
- Log inspection for debugging

---

# Why These Commands Matter in DevOps

These commands help in:

- Troubleshooting production servers
- Monitoring system health
- Diagnosing networking issues
- Managing processes and services
- Debugging application failures

Linux command-line skills are essential for every DevOps engineer.
