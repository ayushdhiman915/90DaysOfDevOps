# Day 02 – Linux Architecture and Process Management 🚀

## Core Components of Linux

### Kernel
- The kernel is the core part of Linux.
- It manages CPU, memory, devices, and processes.
- It acts as a bridge between hardware and software.

### User Space
- User space is where users and applications run.
- Programs cannot directly access hardware.
- Applications communicate with the kernel using system calls.

### Init / systemd
- `systemd` is the first process started during boot.
- It manages services and background processes.
- It helps start, stop, restart, and monitor services.

---

# Process Management in Linux

## How Processes Are Created
- A process is a running program.
- Processes are created using `fork()`.
- Each process has a unique Process ID (PID).

## Process States

- **Running** → Process is actively using CPU
- **Sleeping** → Waiting for input/output
- **Stopped** → Process paused manually
- **Zombie** → Process finished but entry still exists in process table

---

# Why systemd Matters

- Starts system services during boot
- Handles background services
- Restarts failed services automatically
- Improves system management and monitoring

Example:
```bash
systemctl status nginx
```

---

# 5 Linux Commands Used Daily

```bash
ps aux
top
htop
systemctl status
kill -9 PID
```

---

# What I Learned Today

- Linux architecture basics
- Process lifecycle and states
- Importance of systemd in DevOps
- Basic troubleshooting commands
