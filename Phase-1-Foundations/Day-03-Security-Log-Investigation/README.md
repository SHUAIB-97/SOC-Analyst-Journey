# Windows Security Log Investigation

## Overview
This module documents the review of Windows Security events to understand authentication activity and identify patterns that may require further investigation.

## Investigation Scope
- Successful and failed logon events
- Event IDs and timestamps
- Account and logon details
- Logon types
- Source information when available
- Correlation of related events

## Key Event IDs

| Event ID | Description |
|---|---|
| 4624 | Successful logon |
| 4625 | Failed logon |
| 4740 | A user account was locked out |
| 4672 | Special privileges assigned to a new logon |

## Investigation Workflow
1. Open Event Viewer.
2. Navigate to **Windows Logs → Security**.
3. Filter or locate relevant event IDs.
4. Review the timestamp and available event details.
5. Examine account, logon type, and source information when present.
6. Compare related events before reaching a conclusion.

## Security Operations Relevance
Repeated failed logons, unusual authentication patterns, or unexpected privileged logons may warrant further investigation. A single event does not automatically confirm malicious activity.

## Analysis Principles
- Establish context before judging an event.
- Compare related events and timestamps.
- Separate observed facts from assumptions.
- Protect usernames and sensitive log details when sharing examples.

## Learning Outcome
Developing a structured approach to reviewing Windows Security events and documenting investigation findings.

---

**Project type:** Cybersecurity learning and practical exercises  
**Career focus:** Entry-level SOC Analyst