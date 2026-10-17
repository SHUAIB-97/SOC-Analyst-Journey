# Windows Process Investigation Fundamentals

## Overview
This module covers the fundamentals of Windows processes and their relevance to basic security monitoring and investigation.

## Key Concepts
- **Process:** A program that is currently running.
- **Process ID (PID):** A number used to identify a running process.
- **Parent process:** A process that starts another process.
- **Child process:** A process started by another process.
- **Process tree:** A view of relationships between parent and child processes.
- **Command line:** The instruction or arguments used to launch a process.

## Tool
**Windows Task Manager** — used to view running applications, background processes, and process IDs where available.

## Investigation Approach
When examining a process, consider:
1. Process name
2. Process ID (PID)
3. Parent process, when available
4. Command line, when available
5. Whether the activity is expected in its context

## Security Operations Relevance
SOC analysts examine process activity to identify unusual execution, investigate suspicious behavior, and understand how programs are launched.

## Practical Learning
- Located `notepad.exe` in Windows Task Manager.
- Observed its process ID (PID).
- Began learning how to inspect process details using PowerShell.

## Important Note
A process name alone does not prove that activity is malicious. Analysts should consider the process path, command line, parent process, and surrounding events when available.

---

**Project type:** Cybersecurity learning and practical exercises  
**Career focus:** Entry-level SOC Analyst