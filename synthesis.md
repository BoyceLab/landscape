# Approach and rubric

This page describes the methodology behind a testing cycle: roles, the pre-test checklist, how testers are selected, what activities they work through, how we score the results, and what triggers a revision.

If you're new to user testing, start with the [Overview](index.md). If you're about to run a session, skip to [Running a session](facilitator-guide.md).

## A successful cycle answers four questions

1. Within 30 seconds of landing on the site, can a new visitor tell what this resource is and who it is for?
2. Can users from each target audience find the specific information they came for without external guidance?
3. Do users correctly interpret the status categories, badges, and other classifications without misreading them?
4. Does the site work reliably across the devices, browsers, and accessibility tools real users bring to it?

If the answer to any of these is "no," testing has surfaced a gap that would otherwise erode trust in the resource.

## Roles

One person can hold more than one role on a small project — but the Independent Reviewer must not be the same person who made the change being reviewed.

| Role | Responsibility |
|------|----------------|
| UAT Lead | Owns the testing process end-to-end. Recruits testers, runs orientations, triages feedback, decides what gets revised, signs off on release readiness. |
| Site Owner / Editor | Maintains the dashboard content and the underlying data. Responds to substantive questions raised during testing. |
| Developer / Maintainer | Implements functional, design, and accessibility fixes. May be the same person as the Site Owner on small projects. |
| Pilot Testers | External users matching the target audiences. Must be independent of the site's development. |
| Independent Reviewer | Confirms revisions resolve the issues raised. Must not be the person who made the change. |

## Pre-test readiness check

Before involving external testers, the UAT Lead confirms:

- [ ] The site loads on the production or staging URL without console errors.
- [ ] All interactive controls (filters, sorts, modals) function on at least one desktop and one mobile browser.
- [ ] Every external link in the dataset has been spot-checked in the most prominent rows.
- [ ] The "Suggest a correction" workflow has been tested end-to-end and routes to a monitored inbox.
- [ ] The data source list, last-updated date, and ownership/attribution are visible on the site itself.
- [ ] An accessibility quick-scan has been run (axe DevTools, WAVE, or Lighthouse) and obvious failures fixed.
- [ ] Analytics or session-capture tooling is configured if used during testing — with testers informed.

Time spent here protects testers' goodwill and prevents wasted cycles.

## Selecting testers

Recruit three to five testers covering the site's distinct audiences. A reference dashboard serves multiple user types whose friction points don't overlap; a single perspective will miss the friction the others experience.

### Audience personas

| Persona | What they need | What to watch for |
|---------|----------------|-------------------|
| Clinician (neurologist, geneticist) | Quick lookup of a specific gene; clinical context; pointers to registries or trials for a newly diagnosed patient. | Whether clinical terminology is used correctly; whether the path from gene to actionable resource is short. |
| Foundation / advocacy staff | Landscape view of the field; comparing community maturity; identifying gaps. | Whether status categories make sense to someone embedded in the space; whether their own foundation is represented accurately. |
| Patient or family member | Plain-language information; finding a community, registry, or trial relevant to a diagnosis. | Whether jargon blocks comprehension; whether emotional weight is handled with care; whether next steps are clear. |
| Researcher (academic or industry) | Survey of where infrastructure exists; pointers to data sources, collaborators, partnerships. | Whether sources and methods are transparent; whether the resource can be cited. |

### Selection criteria

| Criterion | Ideal | Acceptable |
|-----------|-------|------------|
| Independence | No prior involvement in building or sponsoring the site. | Loose familiarity. |
| Domain fit | Actively works in the condition area covered. | Strong adjacent expertise. |
| Audience coverage | Panel collectively covers all four personas. | At least three of four; gap documented. |
| Device diversity | At least one mobile-only user, one desktop user, and one assistive-technology user. | At least one mobile and one desktop. |
| Availability | 60–90 minutes within a one-week window. | At least 45 minutes within a flexible window. |
| Conflicts | No financial or organizational stake in how their community is represented. | Minor conflicts disclosed and reviewed. |

## Testing activities

Testers work through the activities below in order. The first two must happen before free exploration — first-impression timing only works once.

| Activity | What "good" looks like |
|----------|------------------------|
| First impression (≤ 30 seconds, no scrolling) | Tester correctly summarizes what the site is, who it's for, and what they could do with it. |
| Orientation pass (2–3 min of free exploration) | Tester locates filters, legend, data source, and feedback mechanism without help. |
| Interpret classifications | Tester describes each category accurately in their own words, matching the legend. |
| Guided lookup tasks (3–5 per persona, from the [task bank](task-bank.md)) | Tester completes each with a reasonably direct path. |
| Filter and sort behavior | Filters narrow the table as expected; sorts behave predictably. |
| External link spot check | Sampled links resolve to expected destinations. |
| Feedback workflow | Tester locates and successfully uses the "Suggest a correction" affordance. |
| Cross-device check | Functionality and readability preserved on a different device. |

## The rubric

We score each dimension against three levels. A dimension falling into the rightmost column triggers a revision cycle before release. Look for patterns across testers, not isolated complaints — though a single severe accessibility or accuracy failure is reason enough to act.

| Dimension | Ready to release | Minor revision needed | Significant revision needed |
|-----------|------------------|----------------------|----------------------------|
| First-impression clarity | All testers correctly summarize within 30 seconds. Ratings average ≥ 4.5. | Most testers get it; some need a moment. Average 3.5–4.4. | Multiple testers can't articulate what the site is. Average below 3.5. |
| Task success | All testers complete all assigned tasks correctly and directly. | Most tasks completed; minor friction. | Multiple task failures, or a critical task no tester could complete. |
| Interpretation of categories | All testers describe categories accurately in their own words. | Minor misinterpretations resolved by checking the legend. | Persistent misreading even after consulting the legend. |
| Findability | Filters, legend, sources, and feedback workflow found without help. | One or two elements found late. | Multiple elements not discovered or misidentified. |
| Trust and credibility | Site feels authoritative and citable. | Some testers want more provenance or update transparency. | Testers express doubt about accuracy, currency, or ownership. |
| Device and accessibility | Works across all tested devices. No accessibility failures. | Minor layout or interaction issues on some devices. | Unusable on a common device, or fails a basic accessibility check. |
| Overall confidence | All testers recommend release as-is or with cosmetic changes. | Testers recommend moderate revisions. | One or more testers would not recommend release in current form. |

## Risk and edge cases

| Situation | Response |
|-----------|----------|
| A tester drops out partway through. | Capture whatever feedback they completed. If their persona is now uncovered, recruit a replacement before drawing conclusions. |
| Factually incorrect information about a community is identified. | Treat as a content blocker. Investigate the source, correct, and notify the relevant community contact where appropriate. |
| A tester raises concerns about how their own community is portrayed. | Listen carefully and separate factual correction from framing preference. Correct facts; document framing decisions transparently. |
| Accessibility failure discovered by a tester using assistive technology. | Treat as a blocker for that user class. Fix at the component level. Re-test with the same setup before release. |
| Site relies on external data that changes format or goes offline mid-test. | Document the dependency, capture the impact, and plan a more resilient pipeline or caching layer. |
| Feedback is sparse or low-effort. | Follow up with a short interview. If still thin, treat the data as inconclusive and recruit a replacement. |

## Timeline

A full cycle takes about three to four weeks. Subsequent lightweight cycles (after content updates) can run in one to two weeks once the rubric and tester panel are established.

| Task | Effort | Calendar window |
|------|--------|-----------------|
| Pre-test readiness check; tester recruitment | ~4 hours (UAT Lead) | Week 1 |
| Tester orientations (15 min each) | 1–2 hours total | End of Week 1 |
| Pilot testing sessions (60–90 min per tester) | 3–8 hours total | Week 2 |
| Feedback consolidation and analysis | ~3 hours (UAT Lead) | Early Week 3 |
| Content, UX, and functional revisions | 6–16 hours typical | Week 3 |
| Confirmation re-test and sign-off | 2–3 hours | End of Week 3 or Week 4 |

For releases tied to a public announcement, conference, or funder deadline, add a one-week buffer. Testing routinely surfaces fixes that take longer than expected.

## Release decision

At the end of a cycle, the UAT Lead documents one of three decisions:

!!! success "Release"
    The site is ready. Any remaining items are cosmetic and can be handled in a future content update.

!!! note "Release with conditions"
    The site may be released with specific caveats communicated to users — a visible "beta" tag, a known-issues note, or a scheduled near-term update.

!!! warning "Hold pending further revision"
    The site is not ready. Document the blockers, plan the revisions, and schedule a second cycle.

For an evolving resource, plan to repeat a lighter-weight version of this on a regular cadence — quarterly or after major content shifts — rather than treating it as a one-time gate.

## Reference materials

- [Usability Starter Kit on digital.gov](https://digital.gov/)
- [Atlassian / Jira UAT template library](https://www.atlassian.com/software/jira/templates/user-acceptance-testing)
- [WCAG 2.1 AA quick reference](https://www.w3.org/WAI/WCAG21/quickref/)
