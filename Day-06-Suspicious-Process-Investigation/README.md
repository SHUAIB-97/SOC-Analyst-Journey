# Day 6 — Suspicious Process Investigation

## Overview
This practical focused on learning how to inspect Windows processes and understand which process details can help a SOC Analyst identify potentially suspicious activity.

## Tools Used
- Windows PowerShell
- Windows process information using CIM

## Key Concepts
- **Process:** A program currently running on a computer.
- **PID:** A unique identifier assigned to a running process.
- **Executable Path:** The location from which a program runs.
- **Command Line:** The command and arguments used to start a process.
- **Suspicious Process:** A process whose name, location, parent process, command line, or behavior requires further investigation.

## Practical 1 — List Running Processes

Command:

```powershell
Get-Process | Select-Object Id, ProcessName, CPU | Sort-Object ProcessName
```

Observation: The command displayed running processes with their IDs, names, and CPU information.

## Practical 2 — Inspect Windows Explorer

Command:

```powershell
Get-Process -Name explorer | Select-Object Id, ProcessName, CPU
```

Observed process:
- Process name: explorer
- Process ID: 7464

## Practical 3 — Check Executable Path and Command Line

Command:

```powershell
Get-CimInstance Win32_Process -Filter "ProcessId = 7464" |
Select-Object ProcessId, Name, ExecutablePath, CommandLine
```

Observed results:
- Process ID: 7464
- Process name: explorer.exe
- Executable path: C:\WINDOWS\Explorer.EXE
- Command line: C:\WINDOWS\Explorer.EXE

## Indicators to Investigate

A SOC Analyst may investigate a process when they observe:
- An executable running from an unusual location, such as a suspicious temporary or public folder.
- An unexpected parent process.
- An unusual or suspicious command line.
- Behavior that does not match the program's expected purpose.

## Important Security Lesson

A suspicious-looking process is not automatically malware. Analysts should verify the executable path, parent process, command line, and surrounding activity before drawing conclusions.

## Learning Outcome

I practised listing running processes, identifying Windows Explorer, and examining its executable path and command line using PowerShell.

This practical did not establish that a malicious process was present. It helped me understand how process information can support security investigations.

---
**Project:** SOC Analyst Journey  
**Focus:** Windows process investigation and basic threat detection  
**Purpose:** Educational learning and hands-on practice