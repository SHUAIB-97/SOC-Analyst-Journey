# Windows Event Viewer for Security Monitoring

## Overview
This module explores Windows Event Viewer and its role in reviewing system and security events during basic security investigations.

## Tool
**Windows Event Viewer** — a Windows utility for viewing and examining recorded system and security events.

## Areas Covered
- Windows Event Viewer navigation
- Windows Logs and the Security log
- Event IDs and their meanings
- Successful and failed logon events
- Reviewing event details and timestamps

## Security Event Reference

| Event ID | Description |
|---|---|
| 4624 | Successful logon |
| 4625 | Failed logon |
| 4634 | An account logged off |
| 4688 | A new process was created, when the relevant auditing is enabled |

## Investigation Workflow
1. Open Event Viewer.
2. Navigate to **Windows Logs → Security**.
3. Identify an event by its Event ID.
4. Review the timestamp, account details, logon type, and available source information.
5. Consider related events before deciding whether activity is suspicious.

## Security Operations Relevance
Windows event logs can help analysts investigate authentication activity, identify unusual login patterns, and gather evidence during an investigation.

## Key Principle
A single event does not automatically prove malicious activity. Findings should be assessed using context and related evidence.

---

**Project type:** Cybersecurity learning and practical exercises  
**Career focus:** Entry-level SOC Analyst