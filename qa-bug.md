---
description: Triage a bug and open a Jira Bug issue with the drafted report
argument-hint: <bug description, error, or Jira key>
---

Use the **qa-engineer** agent to triage:

**$ARGUMENTS**

Apply `bug-triage`: attempt/plan reproduction, isolate the variable,
classify root-cause area (product / test / environment / data /
third-party), assign severity via the matrix, and propose priority with
a one-line business rationale. Check whether it looks like a regression.
If the symptoms suggest a security issue, switch to `security-testing`
escalation rules instead of filing on a public board.

Draft the report in the org template:
- Summary (also the ticket title)
- Environment
- Steps to reproduce
- Actual result / Expected result
- Severity (matrix) and Priority (with rationale)

Then **create the Jira issue** using the Atlassian connector:
- **Project**: <!-- CUSTOMIZE: default Jira project key, e.g. PROJ --> —
  or whatever project is clear from `$ARGUMENTS`/context
- **Issue type**: Bug
- **Summary**: the one-line summary from the report
- **Description**: the full drafted report
- **Priority**: the proposed priority from triage

If the target project isn't clear, ask before creating. Otherwise create
the ticket directly — no additional confirmation needed for this command.
If the issue looks like a duplicate, flag the existing ticket instead of
filing a new one.

Report back the created issue key and link.
