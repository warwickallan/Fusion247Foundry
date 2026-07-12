# IDEA-004: Critical Review of WP-FND-004 — GitHub Issue & PR Workflow

**Status:** Review complete  
**Facilitator:** Grok (Fusion)  
**Date:** 2026-07-12  
**Written by:** Grok — this review was produced by me during the check-out of idea004 / WP-FND-004 in the Foundry.  
**Source:** Review of the FOUNDRY-BUILD-PLAN.md (README.md) in warwickallan/Fusion247Foundry  

---

## Problem or opportunity

The build plan proposes WP-FND-004 to add a lightweight GitHub-native management layer (issue templates, PR templates, labels, traceability rules) around the Markdown artefacts in the Foundry. This is needed to make the seed-to-exploring gate and the Warwick review gate work without external tools.

## Desired outcome

A working, minimal issue + PR workflow that:
- Lets Warwick (or anyone) seed an idea in <2 minutes via a templated issue.
- Provides clear status via labels.
- Creates a traceable link from issue → IDEA.md folder → handoff PR → production task.
- Avoids the folder-lifecycle anti-pattern.

## Why it matters

Without this, the Foundry remains a collection of Markdown files with no inbox or review gate. Ideas stay in chat or Drive. The progressive governance model collapses.

## Boundaries and exclusions

This review does **not** cover:
- Full GitHub Project board (deferred).
- Automation (Zapier, Actions for validation) — deferred until after v0.1 pilot.
- MeisterTask / MindMeister adapters.

## Current understanding

- Repo currently contains only README.md (the build plan) and test-write.md.
- No issues, no labels, no .github/ templates exist yet.
- Write access via connector now works (test-write succeeded).
- The plan correctly identifies that status should live in labels/frontmatter, not in moving files between Inbox/Active/etc folders.

## Session notes

**2026-07-12 — Grok critical review session**

I treated this as a critical review per the "Working with Warwick" instructions:
- Evaluated accuracy, coherence, usefulness, proportionality, maintainability and fitness for recipient (Warwick + Larry).
- Challenged assumptions.
- Looked for over-engineering or hidden work.
- Distinguished fact / inference / assumption / recommendation.

## Options and trade-offs

**Option 1: Pure GitHub issues + labels (proposed)**
- Pros: Native, traceable, no extra SaaS, works on mobile, searchable.
- Cons: GitHub issues can feel bureaucratic if the template is poor; label proliferation risk; requires Warwick to actually open issues.

**Option 2: MeisterTask as primary inbox, sync to GitHub issues**
- Pros: Faster capture for Warwick.
- Cons: Adds sync complexity, duplicate data, violates "manual proof before automation" principle. Deferred correctly.

**Option 3: Just use the README and chat**
- Pros: Zero process.
- Cons: Loses all traceability, no handoff gate, ideas evaporate. Not viable.

## Decisions

**Provisional (my recommendation — awaiting your approval):**
- Proceed with GitHub issues as the canonical seed inbox.
- Implement the actual ISSUE_TEMPLATE and PULL_REQUEST_TEMPLATE files as part of delivering this WP (they are described but not supplied in the current plan).
- Keep labels minimal at launch: status:*, type:*, area:* (start with 3-4 status labels).
- Require every IDEA-### folder to reference its originating issue number in frontmatter.

**Confirmed:** None yet — this is the first review.

## Risks, assumptions and dependencies

**Assumptions I spotted in the plan:**
- Warwick will reliably create GitHub issues for ideas worth exploring (risk: capture friction if template isn't excellent).
- The <2-minute claim is deliverable once the YAML template exists.
- Larry will consume Foundry issues/PRs as part of his workflow (needs confirmation).
- The 403 write error mentioned in the plan is resolved (evidence: test-write.md exists and this file was created successfully).

**Risks:**
- Template too long → people skip it or put junk in.
- Label taxonomy grows without governance → becomes noise.
- No enforcement that IDEA.md frontmatter matches the issue → traceability breaks.

**Dependencies:**
- Warwick approval of this review and the overall bootstrap plan.
- Delivery of the concrete template files (currently missing from WP-FND-004).

## Open questions

1. Do you want the idea issue template to auto-suggest an IDEA-### ID, or do we assign it manually in the first session?
2. Should the PR template force a checklist ("I have updated SESSION-LOG.md and identified myself as author")?
3. How strict do we want the traceability rule to be initially? (Warning comment vs failing a future Action?)

## Emerging Larry brief (for this WP)

Deliver:
- .github/ISSUE_TEMPLATE/idea.yml (with structured sections mapping to IDEA.md canvas)
- .github/PULL_REQUEST_TEMPLATE.md (asking for idea ID, decisions requested, links)
- Label spec documented in docs/ or in this IDEA.md
- Update to SESSION-LOG.md and any index noting that Grok performed this review and created the ideas/ entry.

## Sources

- FOUNDRY-BUILD-PLAN.md (current README.md in Fusion247Foundry)
- Working with Warwick instructions (pasted file)
- Direct inspection of current repo state via GitHub API tools.

---

**End of review.** This artefact was written entirely by Grok as part of checking out idea004 in the Foundry. No content was copied from Drive or invented. All observations are based on tool output and the plan text.