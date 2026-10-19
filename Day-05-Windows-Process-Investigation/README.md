# Day 5 — Windows Process Investigation with PowerShell

## Overview
This practical covers how to inspect running Windows processes using PowerShell and identify parent-child process relationships.

## Tools Used
- Windows PowerShell
- Windows Notepad
- Windows Process Information (CIM)

## Key Concepts
- **Process:** A program that is currently running.
- **PID:** A unique identifier for a running process.
- **Parent PID:** The process ID of the process that started another process.
- **Process Investigation:** Examining process details to understand their activity and context.

## Practical 1 — List Running Processes

Command:
```powershell
Get-Process
```

**Observation:** The command displayed the running processes on my computer.

## Practical 2 — Find Notepad

Command:
```powershell
Get-Process notepad
```

**Observation:**
- Process name: Notepad
- PID: 11740
- CPU time: 0.31 seconds at the time of observation

## Practical 3 — Identify the Parent Process

Command:
```powershell
Get-CimInstance Win32_Process -Filter "Name = 'notepad.exe'" |
Select-Object ProcessId, ParentProcessId, Name
```

**Observed results:**
- Process ID: 11740
- Parent Process ID: 7464
- Process name: Notepad.exe

To identify the parent process, I ran:

```powershell
Get-Process -Id 7464
```

**Observation:** The process was identified as Explorer (`explorer.exe`).

## Security Operations Relevance
SOC analysts examine process names, process IDs, parent processes, and other available details to investigate potentially suspicious activity.

A process name or parent-child relationship alone does not prove malicious activity. Additional context and evidence are required.

## Learning Outcome
I practised listing running processes, identifying a specific process, retrieving its parent process ID, and checking the parent process using PowerShell.

---
**Project type:** Cybersecurity learning and hands-on practice  
**Career focus:** Entry-level SOC Analyst