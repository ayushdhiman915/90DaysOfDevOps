# Day 06 – Linux Fundamentals: Read and Write Text Files 📝

## File Read/Write Commands

| Command | Usage |
|---------|--------|
| `touch notes.txt` | Create an empty file |
| `echo "text" > file.txt` | Write text to a file (overwrites) |
| `echo "text" >> file.txt` | Append text to a file |
| `echo "text" \| tee -a file.txt` | Append and display at the same time |
| `cat file.txt` | Read and display full file content |
| `head -n 2 file.txt` | Display first N lines of a file |
| `tail -n 2 file.txt` | Display last N lines of a file |

---

## Command Flow Practiced Today

| Step | Command | Action |
|------|---------|--------|
| 1 | `touch notes.txt` | Created an empty file |
| 2 | `echo "Line 1" > notes.txt` | Wrote first line (overwrite) |
| 3 | `echo "Line 2" >> notes.txt` | Appended second line |
| 4 | `echo "Line 3" \| tee -a notes.txt` | Appended third line and displayed output |
| 5 | `cat notes.txt` | Read and verified full file content |
| 6 | `head -n 2 notes.txt` | Read only the first 2 lines |
| 7 | `tail -n 2 notes.txt` | Read only the last 2 lines |

---

## Files Created Today

| File | Description |
|------|-------------|
| `notes.txt` | Practice text file with 3 written lines |
| `file-io-practice.md` | Markdown documentation of today's practice |

---

## What I Learned Today

- Creating files using `touch`
- Writing and overwriting file content using `>` (redirection)
- Appending new lines to existing files using `>>`
- Using `tee` to write to a file and display output simultaneously
- Reading full file content with `cat`
- Reading partial file content with `head` and `tail`

---

## Why These Commands Matter in DevOps

These file I/O commands are foundational because they are used to:

- Write and update configuration files on Linux servers
- Append logs and output to monitoring files
- Automate file creation and editing in shell scripts
- Read and verify config or log file contents quickly
- Pipe command outputs into files during CI/CD pipelines

Basic file read/write operations are everyday tasks in any DevOps or SysAdmin workflow.

---

## Commands Practiced Summary

| Category | Commands Covered |
|----------|------------------|
| File Creation | `touch` |
| Write / Append | `>`, `>>`, `tee` |
| Read Commands | `cat`, `head`, `tail` |

---

## Practice Outcome

This hands-on Linux practice improved my understanding of:

- File creation and management on Linux
- Redirection operators (`>` and `>>`)
- Using `tee` for simultaneous write and display
- Partial file reading with `head` and `tail`
- Building repeatable file I/O workflows for shell scripting
