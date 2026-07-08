---
description: Produce a test plan and file every test case as a linked Jira Test Case issue
argument-hint: <user story, feature/epic name, or Jira key>
---

Use the **qa-engineer** agent to produce a test plan and full test-case
coverage for:

**$ARGUMENTS**

1. **Plan.** Follow the test plan template in `test-case-generation`,
   using `analytical-thinking` for the risk section and
   `testing-methodologies` to justify approach and test-type mix. Cover:
   scope (in/out/assumptions), ranked risk assessment, approach and
   levels, entry/exit criteria, test data and environment needs, and
   deliverables. Flag missing information as open questions — pause if
   the story isn't testable enough to generate accurate cases.

2. **Generate cases.** Using `test-case-generation`, derive **every test
   case the coverage checklist calls for** against the story's
   acceptance criteria: happy paths, negative inputs, boundary values,
   state/permission variations, concurrency/idempotency, error handling,
   backward compatibility, and any flagged non-functional cases. Pull in
   specialist skills (`api-testing`, `security-testing`,
   `performance-testing`, `accessibility-testing`, `mobile-testing`)
   where the risk table points to them.

3. **List before filing.** Show the full list of generated test cases
   (title, priority, suite classification) with a total count, plus the
   planned structure: 1 Test Suite issue linked to the story, and N
   Test Case issues linked to that suite. Ask me to confirm before
   creating anything in Jira.

4. **File in Jira**, using the Atlassian connector, only after I confirm.
   Create everything in the **"Test Cases"** project/space — this is
   fixed regardless of which project the user story itself lives in:
   - Create one **Test Suite** issue in "Test Cases" for the story —
     summary `Test Suite: <story summary>`, description = the test plan
     from step 1. Link it to the user story with link type
     **"Test Suite"** (a cross-project link).
   - Create one **Test Case** issue in "Test Cases" per case from
     step 2 — summary = the case title, description = preconditions,
     numbered steps, and expected result (from the org template),
     priority = the case's P1/P2/P3. Link each one to the Test Suite
     issue with link type **"Test case"**.

   <!-- CUSTOMIZE: confirm the exact Jira project key behind the
   "Test Cases" project/space (e.g. TC), and that "Test Suite" and
   "Test Case" are the exact issue-type names available in it, and that
   issue link types "Test Suite" and "Test case" exist as named —
   adjust above if your instance differs. -->

End with a coverage summary (what's covered, what's not, residual risk,
open questions) and a list of every issue created with its key and link.
