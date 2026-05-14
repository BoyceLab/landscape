# Synthesis and release

What happens after the testing sessions are done: how findings are consolidated, how revisions are tracked, and how the release decision is made and documented.

## Findings synthesis

Complete this after the last testing session but before starting revisions. The goal is a single document showing every finding from every tester — deduplicated, prioritized, and assigned. Without this step, individual session notes drift into separate to-do lists and important patterns get missed.

Work through the sections in order.

### 1. Tester summary

| ID | Persona | Session date | Duration | Device(s) | Form returned? |
|----|---------|--------------|----------|-----------|----------------|
| T1 |         |              |          |           |                |
| T2 |         |              |          |           |                |
| T3 |         |              |          |           |                |
| T4 |         |              |          |           |                |
| T5 |         |              |          |           |                |

**Coverage check.** Did the panel cover all four personas? If a persona is missing, note it — it informs the release decision.

### 2. Rubric ratings

Fill in the average rating for each dimension. Flag any tester whose ratings deviated substantially from the average — their session likely contains the most actionable feedback.

| Dimension | Avg | Min | Max | Notes |
|-----------|-----|-----|-----|-------|
| First-impression clarity | | | | |
| Task success rate | | | | |
| Interpretation of categories | | | | |
| Findability | | | | |
| Trust and credibility | | | | |
| Device and accessibility | | | | |
| Overall confidence | | | | |

**Quick read.** Any dimension averaging below 3.5, or with a single rating of 1–2, deserves discussion in section 4 even if other dimensions look healthy.

### 3. Findings

Every finding from every session, deduplicated. Use severity tags from the [facilitator guide](facilitator-guide.md). Assign an owner and an action. Findings raised by multiple testers should be flagged with a count and treated as higher confidence.

| # | Severity | Finding | Raised by | Action | Owner | Status |
|---|----------|---------|-----------|--------|-------|--------|
| 1 |          |         |           |        |       |        |
| 2 |          |         |           |        |       |        |
| 3 |          |         |           |        |       |        |

Severity reminders:

- **BLOCKER** — must fix before release
- **MAJOR** — should fix before release
- **MINOR** — can be deferred
- **QUESTION** — needs team discussion before action

### 4. Patterns and themes

Issues raised by only one tester may still matter — but issues raised by multiple testers across different sessions are diagnostic of the design, not the tester.

| Theme | Evidence (which testers, what they said) |
|-------|-------------------------------------------|
|       |                                           |
|       |                                           |

### 5. What worked

Don't only document problems. Note what testers reacted positively to — these are signals about what to preserve when revising.

### 6. Recommendation for release decision

One paragraph. State the recommended decision (Release / Release with Conditions / Hold) and the single most important reason.

---

## Revision log

Record every change in response to testing feedback. Update as each revision is completed, not at the end — memory of why a change was made degrades quickly.

| # | Finding ID | Issue | Change made | Owner | Date | Verified by |
|---|------------|-------|-------------|-------|------|-------------|
| 1 |            |       |             |       |      |             |
| 2 |            |       |             |       |      |             |

**Deferred items.** Issues raised but explicitly not addressed in this cycle. Documenting them prevents loss and supports planning for the next cycle.

| # | Finding ID | Issue | Reason for deferral / planned cycle |
|---|------------|-------|--------------------------------------|
| 1 |            |       |                                      |

For public dashboards, consider exposing a short "What's new" or changelog on the site itself.

---

## Release decision memo

A one-page memo formalizing the release decision and rationale at the close of a cycle. Use this structure:

### Memo header

| | |
|---|---|
| Project / site | |
| Cycle name (e.g., "Pre-launch v1" or "Q3 update") | |
| Date of memo | |
| Author (UAT Lead) | |
| Distribution | |

### Decision

Check one:

- [ ] **Release.** The site is ready. Remaining items are cosmetic.
- [ ] **Release with conditions.** Releasing with specific caveats communicated to users.
- [ ] **Hold pending further revision.** Site not ready; a second cycle is scheduled.

### Summary of cycle

One short paragraph: who tested, what they did, and what was found at a high level.

### What changed

The three to five most consequential changes made in response to feedback.

- [Change 1]
- [Change 2]
- [Change 3]

### Conditions (if Release with Conditions)

| Condition | How communicated / when resolved |
|-----------|----------------------------------|
|           |                                  |

### Blockers (if Hold)

| Blocker | Owner / planned resolution |
|---------|----------------------------|
|         |                            |

### Risks and open questions

Anything not captured above the team or stakeholders should know about. Known data limitations, audiences not represented in this cycle, planned future work.

### Next cycle

| | |
|---|---|
| Planned trigger (date or event) | |
| Anticipated scope (full or focused) | |
| Notes | |

### Sign-off

| Role | Name | Date |
|------|------|------|
| UAT Lead | | |
| Site Owner | | |
| Other approver (e.g., Principal Investigator) | | |

---

## Cadence

For an evolving resource like this one, plan to repeat a lighter-weight version of this process on a regular cadence — quarterly, or after major content shifts — rather than treating testing as a one-time gate. A lightweight cycle typically uses two testers, a focused task bank, and an abbreviated synthesis.

The full process is for pre-launch and major releases. The lighter version keeps the resource honest between them.
