# IDEA-004 — Briefing, Output and Connector Orchestration

**Status:** Exploring  
**Owner:** Warwick  
**Facilitator:** Fusion / ChatGPT  
**Created:** 12 July 2026  
**Imported to GitHub:** 12 July 2026 by Grok from Google Drive fallback  
**Source:** Google Doc "IDEA.md - IDEA-004 Briefing, Output and Connector Orchestration" (file ID: 1nNmNQoc37uxyWUCsmoMdH_U-SCHcNeQgL0TKyHUWV30, link: https://docs.google.com/document/d/1nNmNQoc37uxyWUCsmoMdH_U-SCHcNeQgL0TKyHUWV30/edit)  
**Target production repository:** warwickallan/Fusion247PKA

**Note on provenance:** This package was created in the Google Drive Foundry fallback during the period when the GitHub connector had write restrictions (403). It has now been imported to GitHub as the canonical location for active Foundry ideas. The original Drive document remains the source of record for this version. Grok performed the import and added the critical review below.

EXPLORATION ONLY  
This package is not approved for production build and must not be treated as a Larry handoff.

---

## PROBLEM OR OPPORTUNITY

Fusion247 already contains several pieces of a broader output architecture, but they are currently being discussed as if they were separate capabilities:

• Four NPL-derived Project ManagAIr outputs: Project Meeting Prep, Implementation & Configuration Guide, Meeting Summary and Consultant Summary.  
• The Client Delivery query-layer concept that retrieves the records that matter for a meeting or decision.  
• Scheduled daily briefings covering tasks, calendar, email, deadlines and tomorrow-readiness.  
• Transcript-triggered summaries and debriefs.  
• An existing ChatGPT Gmail Clean Sweep task that already runs against a connected mailbox.  
• Multiple Microsoft and Google mailbox identities split across different AI platforms.

The missing design is not another isolated briefing prompt. It is a governed way to connect:

1. Canonical instructions and records.  
2. Intelligence and retrieval skills.  
3. Purpose-specific output skills.  
4. Execution runtimes such as ChatGPT, Claude Code or a service.  
5. Provider connectors and APIs.  
6. Schedules and event triggers.  
7. Rendered briefings, guides, summaries and Cockpit views.

Without that separation, each platform risks becoming its own partial system with duplicated prompts, incomplete mailbox coverage and no shared record of what has already been classified or actioned.

## DESIRED OUTCOME

Define a reusable Briefing and Output Orchestration capability in which:

• Larry and the Fusion247 Markdown artefacts own the governed method, routing rules and durable operational state.  
• Specialist skills own domain reasoning such as inbox classification, task intelligence, transcript extraction and project retrieval.  
• ChatGPT, Claude, Codex, local scripts or hosted services act as replaceable execution runtimes.  
• Gmail, Microsoft Graph, Rocketlane and other connectors provide the physical read/write capability.  
• Schedules or events wake the relevant runtime.  
• Output-specific profiles select, rank and present only what matters for the current purpose.  
• Source links, freshness, confidence and action permissions remain visible.  
• Work and personal data remain separate security domains even when a combined coordination view is useful.

## WHY IT MATTERS

Warwick wants concise, actionable information brought forward at the right time rather than another place to inspect manually. A successful design would:

• Reuse the NPL output work rather than rebuilding it under a new name.  
• Turn existing inbox sweep results into useful briefing inputs.  
• Reduce dependence on whichever AI platform happens to hold a particular account connection.  
• Prevent duplicate or contradictory automation across ChatGPT and Claude.  
• Allow the same canonical capability to survive future platform changes.  
• Support progressive movement from passive documents to linked and eventually actionable Cockpit views.

## CURRENT EVIDENCE AND WORKING CONTEXT

Existing NPL output family

1. Project Meeting Prep — pre-event decision and action briefing.  
2. Implementation & Configuration Guide — durable reference output.  
3. Meeting Summary — factual post-event record.  
4. Consultant Summary — explicitly interpretive advisory output.

These should remain distinct output purposes even where they share retrieval, composition, provenance and rendering mechanisms.

Client Delivery query layer

IDEA-003 proposes:

Canonical structured Markdown  
        ↓  
Generated SQLite mirror  
        ↓  
Cockpit / AI skills / briefs

Its “Ten Things” retrieval proof — returning the records that matter for tomorrow’s NPL meeting — is directly reusable as a briefing-selection pattern.

Existing Gmail execution proof

A ChatGPT Scheduled Task named Gmail Clean Sweep is currently enabled and scheduled at 06:00 and 15:00 Europe/London. It uses embedded instructions to clean obvious noise cautiously and surface potentially important messages. It is a useful runtime proof, but it is not yet a governed Fusion247 skill adapter and does not automatically inherit future changes to Larry’s Markdown instructions.

Mailbox fragmentation

The current estate includes multiple Microsoft identities spanning work and personal use plus Gmail. Coverage is presently achieved by connecting overlapping accounts to ChatGPT and Claude. This provides practical access but creates architectural weaknesses:

• Account coverage depends on platform-specific authentication.  
• The same mailbox may be inspected by more than one runtime.  
• One personal Microsoft identity may be visible to one platform but not another.  
• Prompts and permissions can drift.  
• There is no shared executor-of-record or common triage state.  
• A combined briefing cannot prove that every intended source was refreshed.

No email addresses or credentials belong in the Foundry repository.

## CORE ARCHITECTURAL DISTINCTION

Larry governs and orchestrates. The active runtime reasons and invokes tools. Connectors, scripts and services perform the physical operations.

Larry / canonical artefacts own:

• Routing and specialist responsibilities.  
• Inbox-sweep policy and deletion safeguards.  
• Briefing-selection principles.  
• Output definitions and interpretation boundaries.  
• Approval thresholds and action permissions.  
• Durable task, project and decision state.  
• Audit and provenance expectations.

Execution runtimes own:

• Loading the applicable instructions.  
• Reasoning over current source data.  
• Invoking the tools available in that environment.  
• Returning normalized results and disclosed failures.  
• Applying only the permissions available to that runtime.

Connectors and services own:

• Authentication and token handling.  
• Reading and mutating external systems.  
• Incremental synchronization.  
• Retries, idempotency and structured logs.  
• Stable provider identifiers and source links.  
• Reporting permission or freshness failures.

## PROPOSED CAPABILITY MODEL

Source systems  
  Gmail / Microsoft / Rocketlane / Calendar / transcripts / project records  
        ↓  
Provider adapters and connector runtimes  
        ↓  
Normalized operational records and source links  
        ↓  
Domain intelligence skills  
  Inbox Sweep / Task Intelligence / Transcript Intake / Project Retrieval  
        ↓  
Output-specific skill or profile  
  Meeting Prep / Meeting Summary / Consultant Summary / Daily Brief  
        ↓  
Shared composition and rendering layer  
        ↓  
Cockpit / Markdown / email / Teams / Telegram / PDF / voice

The template controls presentation. The output skill controls purpose, evidence selection and permitted interpretation. The runtime adapter controls how a particular platform executes the governed method.

## CANDIDATE BRIEFING PRODUCTS

• Personal Morning Brief — once daily.  
• Work Morning Brief — weekday orientation and preparation.  
• Work Midday Reset — changes, slippage and afternoon replan.  
• Work Closeout Brief — carry-over and tomorrow-readiness.  
• Project Meeting Prep — one meeting or engagement.  
• Meeting Summary — factual transcript-derived debrief.  
• Consultant Summary — evidence-grounded interpretation.  
• Project or Topic Brief — on demand.  
• Exception Brief — only when delay until the next scheduled brief would create material risk.

The exact work closeout time remains provisional; previous discussion used both 16:30 and 17:00.

## BRIEFING INFORMATION DESIGN HYPOTHESIS

The first screen should normally contain:

1. Situation and source freshness.  
2. Up to five best actions now.  
3. A non-duplicative critical watchlist.  
4. New or materially changed items since the previous brief.  
5. Upcoming commitments and preparation status.  
6. Waiting, blocked and delegated exceptions.  
7. Links to complete registers rather than dumping every open item.

“Most valuable” and “most critical” are different scoring dimensions. They should inform one action ranking plus a separate watchlist, not create ten competing priorities.

## COMMON OUTPUT-ITEM CONTRACT HYPOTHESIS

Each contributing skill should be able to return:

• Stable identity and provider/source.  
• Work or personal domain.  
• Title and concise summary.  
• Owner and status.  
• Due date or useful action window.  
• Value, criticality and readiness.  
• Suggested next action and why it matters now.  
• Dependencies and blockers.  
• Source and action links.  
• Last changed and last refreshed.  
• Confidence and unresolved uncertainty.  
• Sensitivity and permitted actions.

This is a candidate contract, not an approved schema.

## BOUNDARIES AND EXCLUSIONS

This idea does not yet approve:

• A single giant Briefing agent that duplicates every domain skill.  
• Copying complete work email bodies into a personal system.  
• Permanent dual-write between Markdown and external databases.  
• Autonomous email sending or destructive mailbox actions.  
• One AI platform becoming the canonical mailbox store.  
• Storing OAuth tokens or credentials in Markdown or Git.  
• A dashboard build before the read-only information flow is proven.  
• Implementation-specific classes, libraries, tables or deployment choices.

## WORK AND PERSONAL BOUNDARY

Separate data, authority and execution; optionally combine a restricted coordination view.

A personal command view may show that work contains a critical item or an early meeting without copying sensitive customer content outside the work-authorized environment. The detailed work record remains inside the work security plane.

## DECISIONS

Provisional:

• Treat this as a shared output and orchestration architecture, not simply a Daily Brief skill.  
• Preserve the four NPL outputs as distinct purposes.  
• Keep templates separate from selection and reasoning logic.  
• Require one automated executor of record per mailbox or external account.  
• Treat the existing Gmail task as an execution proof and future adapter candidate, not the canonical skill.  
• Keep work and personal stores separate while allowing a minimal coordination summary.

Confirmed:

None yet. Warwick has asked for a Foundry exploration pack and Grok review, not production approval.

## OPEN QUESTIONS

1. Should the capability be named Briefing and Output Orchestration, Operational Briefing Framework, or something else?  
2. Is the personal morning brief one combined view with sealed work/personal sections, or two separately delivered products?  
3. Which runtime should be executor of record for each existing mailbox?  
4. Can each target AI platform maintain multiple simultaneous identities for the same mail provider, and with which permissions?  
5. Should multi-mailbox ingestion be part of this idea or a linked Mack integration idea?  
6. Where should normalized mail intelligence live before full Client Delivery and Personal OS schemas converge?  
7. How much state may a hosted platform task retain versus what must be written back into canonical Fusion247 records?  
8. What is the minimum safe write capability for the first proof: read-only, label/archive, or task creation?  
9. Which channel should be authoritative for delivery: Cockpit, ChatGPT task conversation, email, Teams or Telegram?  
10. What data may cross from the Bellrock work environment into a personal combined briefing?  
11. How should adapters declare the canonical skill version they implement and detect drift?  
12. Should the briefing snapshot itself be retained, and if so for how long and at what level of detail?

## RISKS AND TENSIONS

• Platform lock-in disguised as convenience.  
• Duplicated prompts drifting away from canonical skills.  
• Two runtimes mutating the same mailbox inconsistently.  
• Sensitive work material leaking into personal storage.  
• A briefing becoming another overloaded inbox.  
• Ranking logic hiding why something was selected or omitted.  
• Stale connector data presented with unwarranted confidence.  
• Building multi-account infrastructure before proving a useful briefing.  
• Collapsing factual summaries and interpretive advice into one ambiguous output.

## SMALLEST USEFUL PROOF

Use the existing Gmail Clean Sweep as the first execution input, but change the proof question from “can it clean email?” to:

Can one scheduled sweep produce a normalized, source-linked set of important items that a separate Personal Morning Brief can consume without rereading the whole mailbox or duplicating the sweep logic?

The first proof should remain read-mostly and should disclose freshness, failures and the connected account identity without storing credentials.

## SESSION NOTE — 12 JULY 2026

• Began with scheduled work and personal briefing formats.  
• Recognized that the NPL four-output model already contains the same purpose-specific output pattern.  
• Separated output skills from templates, triggers and renderers.  
• Clarified that Larry is governed method and orchestration, while AI runtimes and connectors physically execute.  
• Identified the existing ChatGPT Gmail Clean Sweep as a live but platform-local adapter proof.  
• Exposed the multi-Microsoft-account split as a runtime ownership and shared-state problem rather than merely a connector inconvenience.  
• Created this Foundry package for external challenge by Grok before any Larry handoff.

## NEXT INVESTIGATION

Ask Grok to challenge:

• Whether one idea is carrying too much scope.  
• Whether Briefing Orchestration and Multi-Mailbox Integration should be split.  
• Whether the runtime/connector boundary is correctly drawn.  
• Whether the work-package order proves value before infrastructure.  
• Whether the proposed common item contract is too early or too generic.  
• What important failure or security mode has been missed.  

---

## Grok Critical Review of Real IDEA-004 (Briefing, Output and Connector Orchestration)

**Review written by:** Grok (Fusion) on 12 July 2026 — this section added during the correction and proper check-out of IDEA-004. Previous mistaken review of retired WP-FND-004 has been deleted and logged as error in SESSION-LOG.md.

**Facts from the artefact:**
- Clear separation of concerns: Larry owns governance/orchestration, runtimes own reasoning/execution, connectors own I/O. This is a strong first-principles distinction.
- Reuses existing NPL outputs and Gmail Clean Sweep proof rather than inventing new ones. Good.
- Explicit work/personal boundary and security domains called out.
- Many open questions listed — appropriately left unresolved.
- Smallest useful proof defined narrowly around the existing Gmail task.

**Strengths:**
- The architectural model (source → adapters → skills → output profiles → rendering) is clean and avoids the "one giant agent" trap.
- Treating the four NPL outputs as distinct purposes even if they share mechanisms is exactly right.
- Risks section is honest about platform lock-in, duplication, and leakage.
- The item contract hypothesis is pragmatic without over-specifying.

**Weaknesses / areas to challenge:**
- Scope is broad: Briefing orchestration + multi-mailbox + output profiles + rendering layer + connector adapters. The "one idea carrying too much scope" question in the NEXT INVESTIGATION section is well-placed. This could easily become the kitchen sink. Recommend splitting Multi-Mailbox Integration into a linked but separate idea if the first proof succeeds.
- The "common output-item contract" is proposed but not yet tested against the existing NPL outputs. Might need iteration once real data flows.
- No explicit mention of how this interacts with IDEA-003 (Client Delivery query layer). There is overlap in the "retrieval" layer — worth mapping explicitly to avoid duplicate work.
- The personal vs work boundary is stated but the mechanism for a "combined coordination view" without leaking sensitive data is left as future work. That could be a material risk if not designed early.
- 12 open questions is a lot for one package. Some could be parked or split.

**Assumptions in the artefact:**
- That Larry/Markdown can be the single source of truth for routing and policy without performance issues.
- That existing proofs (Gmail Clean Sweep, NPL outputs) can be adapted without major rewrite.
- That multiple runtimes can coexist with shared state via canonical records.

**Recommendations:**
- Proceed with the smallest proof using Gmail Clean Sweep → normalized items → Personal Morning Brief. Keep it read-mostly.
- After proof, split the multi-mailbox and connector ownership questions into a follow-on idea.
- Explicitly map dependencies to IDEA-003 before converging on shared retrieval.
- Add a simple provenance/freshness contract to the item model early.
- This is a high-value idea. The separation of governance vs execution is the kind of thinking that prevents the exact kind of provenance error I just made.

**Overall verdict:** Coherent, well-structured, proportionate for an exploration pack. The scope risk is real but acknowledged in the document itself. Ready for your review, Warwick. Not over-engineered, but watch the boundary creep.

**End of Grok review.** This review and the import were performed by Grok following the cleanup of the previous namespace mistake. I have updated the session log with full transparency.

---

*This IDEA.md now contains the genuine IDEA-004 imported from Drive + Grok's critical review. All authorship clearly identified.*