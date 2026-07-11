# Fusion247Foundry
The place for ideas

Fusion247 Foundry — Build Plan

Document type: Foundry bootstrap canvas and execution plan
Status: Draft for Warwick review
Owner and final decision-maker: Warwick
Plan author and intended executor: Fusion / ChatGPT
Build consumers: Larry and the Fusion247 build agents
Created: 11 July 2026
Target repository: "warwickallan/Fusion247Foundry"

---

1. Build objective

Create a lightweight, Git-native Fusion247 Ideas Department and Build Foundry where Warwick and Fusion can:

1. Capture ideas quickly.
2. Explore them without contaminating production governance.
3. Preserve important context, options, decisions and evidence.
4. Progressively create a work-package PRD and implementation plan.
5. Give Larry a controlled, build-ready handoff.
6. Trace the finished build back to the original idea.
7. Promote only the accepted outcome into the permanent Fusion247 system.

The Foundry is not:

- another PKA;
- a second Fusion247 Brain;
- a replacement for "Fusion247Brain";
- a full project-management system;
- Larry’s production task board;
- a dumping ground for complete chat transcripts.

It is the controlled workshop between Warwick’s thinking and Larry’s production queue.

---

2. Source material reviewed

The plan has been developed using the current conversation and the following Google Drive material:

- "/Hey Fusion.md"
- "F247.master.index"
- "F247.decision-log"
- "Session Log"
- "F247.project-operating-ontology"
- "GL-F247-001-project-entity-schema"
- "F247.proposal.mypka-gap-analysis — 2026-07-08"
- "README — Fusion247 Build Project (START HERE)"
- "F247 Brain PRD"
- "Yet another bloody build doc.madlol"
- "F247.skill.critical-panel-review"
- "F247 Drive Object Registry"

The following existing principles are inherited:

- Temporary "build.*" thinking remains separate from approved "F247.*" content.
- The agent is not the manual.
- Source evidence must be preserved and referenced.
- Uncertainty must be recorded rather than silently converted into fact.
- Work packages are first-class entities.
- Material outputs require human approval and QA.
- Duplicate instruction stores must not proliferate.
- The manual operating loop must work before dashboards and automation are added.
- The system must remember through controlled artefacts rather than depending on chat memory.

---

3. Architecture decision

3.1 Canonical responsibilities

Fusion247Foundry

Canonical home for:

- raw idea capture;
- structured brainstorming;
- options and trade-offs;
- idea-level session history;
- provisional and confirmed decisions;
- risks, assumptions, dependencies and unresolved questions;
- PRDs;
- implementation plans;
- Larry handoff packages;
- links to production implementation and QA.

Google Drive

Supporting source and evidence store for:

- existing Fusion247 governance;
- long-form source documents;
- recordings and transcripts;
- images and diagrams;
- spreadsheets;
- documents that are awkward to maintain as Markdown;
- immutable or externally supplied evidence.

Drive is not the canonical status system for Foundry ideas.

Fusion247Brain and other production repositories

Canonical home for:

- approved agents;
- skills and SOPs;
- guidelines;
- schemas;
- templates;
- runtime behaviour;
- implementation code;
- permanent architectural decisions;
- accepted product capability.

Raw Foundry exploration is not copied wholesale into production.

---

4. End-to-end operating model

Warwick has an idea
        ↓
GitHub seed issue
        ↓
Fusion checks for duplication and clarifies the intended outcome
        ↓
IDEA.md working canvas
        ↓
Structured exploration with Warwick
        ↓
Options, decisions, risks and unresolved questions
        ↓
PRD and implementation plan when justified
        ↓
HANDOFF.md
        ↓
Foundry pull request for Warwick review
        ↓
Warwick approves, rejects or sends back for refinement
        ↓
Larry creates the controlled production task and branch
        ↓
Build, tests and implementation PR
        ↓
VerifiAIr / Claude QA
        ↓
Accepted result promoted into permanent F247 artefacts
        ↓
Foundry idea linked to the production outcome and closed

The Foundry pull request is a design and handoff gate.

It is not permission to merge the Foundry folder into the production Brain.

---

5. Operating principles

5.1 Progressive governance

A passing thought should not immediately generate:

- a PRD;
- an implementation plan;
- a risk register;
- a decision register;
- a session document;
- a delivery plan;
- a small commemorative plaque.

Documentation expands only as the idea earns it.

5.2 Issues first, folders later

A new idea begins as a GitHub issue.

An idea folder is created only when:

- it is not an obvious duplicate;
- it deserves a real exploration session;
- the intended outcome is plausible;
- Warwick wishes to continue developing it.

5.3 One working document first

An active idea begins with one file:

IDEA.md

This contains the working canvas, sessions, options, decisions, risks and emerging handoff.

Separate PRD, implementation-plan and handoff files are created only when the idea becomes sufficiently mature.

5.4 Stable paths

Ideas should not be physically moved through folders named:

Inbox
Active
Converging
Ready
Building
Merged

That pattern works in Drive but creates unnecessary file moves and broken links in Git.

Status belongs in:

- issue labels;
- frontmatter or metadata;
- pull-request state;
- a future GitHub Project view.

5.5 One source of truth per fact

The same decision should not be manually copied into:

- the idea file;
- a root decision log;
- the PRD;
- the implementation plan;
- the handoff;
- the production decision log.

The canonical decision lives once. Other artefacts link to or summarise it where needed.

5.6 Human approval

Fusion may:

- structure;
- analyse;
- challenge;
- recommend;
- draft;
- maintain the Foundry artefacts.

Fusion may not silently approve its own material product, policy or architecture decisions.

Warwick remains the decision-maker.

5.7 Manual proof before automation

Do not add:

- Zapier;
- MeisterTask synchronisation;
- MindMeister synchronisation;
- automatic issue promotion;
- bots;
- custom dashboards;
- SQLite;
- semantic search;
- autonomous production handoff;

until one real idea has completed the manual lifecycle successfully.

---

6. Target repository structure

Fusion247Foundry/
├── README.md
├── FOUNDRY-BUILD-PLAN.md
│
├── docs/
│   ├── OPERATING-MODEL.md
│   ├── HANDOFF-CONTRACT.md
│   ├── DRIVE-BOUNDARY.md
│   └── QA-CHECKLIST.md
│
├── logs/
│   ├── SESSION-LOG.md
│   └── DECISION-LOG.md
│
├── templates/
│   ├── IDEA-TEMPLATE.md
│   ├── PRD-TEMPLATE.md
│   ├── IMPLEMENTATION-PLAN-TEMPLATE.md
│   └── HANDOFF-TEMPLATE.md
│
├── ideas/
│   └── IDEA-###-short-name/
│       ├── IDEA.md
│       ├── PRD.md
│       ├── IMPLEMENTATION-PLAN.md
│       ├── HANDOFF.md
│       └── sources/
│           └── README.md
│
└── .github/
    ├── ISSUE_TEMPLATE/
    │   └── idea.yml
    └── PULL_REQUEST_TEMPLATE.md

Not every idea folder will contain every listed file.

The structure represents the maximum mature package, not the minimum starting package.

---

7. Duplication controls

Root README

"README.md" is a concise front door containing:

- what the Foundry is;
- what it is not;
- the basic lifecycle;
- links to canonical operating documents;
- instructions for starting an idea.

It must not reproduce the complete operating model.

Root session log

"logs/SESSION-LOG.md" records only:

- Foundry bootstrap work;
- cross-idea reviews;
- changes to the operating model;
- template revisions;
- releases;
- repository-wide decisions and incidents.

Idea-specific sessions belong inside the idea package.

Root decision log

"logs/DECISION-LOG.md" records decisions that affect:

- the whole Foundry;
- the relationship with Drive;
- the relationship with production repositories;
- lifecycle rules;
- templates;
- QA gates;
- connector architecture.

Decisions that affect only one idea remain in that idea.

Source folders

The "sources" directory normally contains a source manifest and links.

Canonical Drive documents should not be copied into Git merely for convenience.

A snapshot may be committed only where:

- an immutable review baseline is required;
- the source may change;
- Larry requires the precise source state used for the design;
- portability genuinely requires it.

Any snapshot must state:

- original source;
- date captured;
- source owner;
- whether it is authoritative or reference-only;
- whether a newer canonical version may exist.

---

8. Idea identifiers and metadata

Identifier pattern

IDEA-001
IDEA-002
IDEA-003

Folder pattern:

ideas/IDEA-001-contextual-task-intelligence/

Required metadata

Every promoted idea must identify:

- "idea_id"
- "title"
- "status"
- "owner"
- "facilitator"
- "created"
- "last_updated"
- "source_issue"
- "related_drive_sources"
- "target_production_repo"
- "foundry_review_pr"
- "production_task"
- "production_pr"
- "qa_status"

Unknown values must be marked as unknown rather than omitted or invented.

---

9. Status model

Seed
Exploring
Converging
Ready for Warwick Review
Ready for Larry
Accepted for Build
Building
Implemented
Parked
Rejected

Seed

Captured but not yet developed.

Exploring

The problem, opportunity and possible approaches are being investigated.

Converging

A preferred direction is emerging and the work is becoming definition-ready.

Ready for Warwick Review

The package is sufficiently clear for Warwick to evaluate the proposed outcome and boundaries.

Ready for Larry

Warwick has approved the design package and Larry can consume it without inventing missing policy.

Accepted for Build

Larry has accepted the handoff into a controlled production task.

Building

Implementation is in progress.

Implemented

The production result has been merged and relevant QA has completed.

Parked

Potentially valuable but intentionally deferred.

Rejected

The idea or proposed solution will not proceed. The rationale remains preserved.

---

10. Progressive artefact model

Level 0 — Seed issue

A seed issue contains:

- the problem or idea in one sentence;
- why it may matter;
- relevant context or source link;
- suggested next investigation;
- known relationship to existing Fusion247 capabilities.

The issue should take less than two minutes to create.

Level 1 — IDEA.md canvas

Created when the seed is promoted to exploration.

Required sections:

Problem or opportunity

What is wrong, missing or potentially valuable?

Desired outcome

What would be better if the idea succeeded?

Why it matters

User value, business value, time saved, risk reduced or capability created.

Boundaries and exclusions

What the idea does not currently include.

Current understanding

Known facts and current system context.

Session notes

Dated summaries of meaningful exploration sessions.

These are summaries, not pasted transcripts.

Options and trade-offs

Plausible approaches, benefits, drawbacks and constraints.

Decisions

Clearly separated into:

- candidate;
- provisional;
- confirmed;
- superseded;
- rejected.

Risks, assumptions and dependencies

Anything that could affect feasibility or outcome.

Open questions

Questions requiring evidence or Warwick’s decision.

Emerging Larry brief

A progressively refined summary of what may eventually be built.

Sources

Links to Drive, GitHub, research or other evidence.

Level 2 — Defined package

Create separate documents once each can be reviewed independently.

PRD.md

Contains:

- user or stakeholder problem;
- desired outcome;
- user groups;
- functional requirements;
- non-functional requirements;
- scope;
- exclusions;
- constraints;
- acceptance criteria;
- dependencies;
- source traceability.

IMPLEMENTATION-PLAN.md

Contains:

- recommended technical and operating design;
- affected repositories;
- affected artefacts;
- new files or components;
- existing files to amend;
- implementation sequence;
- migrations;
- compatibility considerations;
- data or connector requirements;
- security and privacy considerations;
- tests;
- rollback or recovery approach;
- release and QA sequence.

Level 3 — HANDOFF.md

The final controlled brief for Larry.

Contains:

- agreed problem;
- agreed outcome;
- scope;
- exclusions;
- recommended solution;
- important rejected alternatives;
- confirmed decisions;
- unresolved questions Larry must not guess;
- risks and dependencies;
- affected repositories and files;
- proposed new "F247.*", "GL-F247", "SOP-F247", "WS-F247" or template artefacts;
- implementation sequence;
- acceptance criteria;
- QA requirements;
- provenance links.

---

11. Lifecycle gates

Gate A — Seed to Exploring

Required:

- meaningful problem or opportunity;
- no obvious duplicate;
- intended domain identified;
- plausible outcome;
- Warwick wants to spend further effort on it.

Action:

- assign an idea ID;
- create the idea folder;
- create "IDEA.md";
- link the originating issue.

Gate B — Exploring to Converging

Required:

- problem is clear;
- desired outcome is clear;
- major options have been considered;
- important constraints are visible;
- a preferred direction is emerging;
- major unknowns are explicitly listed.

Action:

- change status to Converging;
- create PRD or implementation plan only where justified.

Gate C — Warwick review

Required:

- scope and exclusions are explicit;
- decisions are distinguishable from assumptions;
- acceptance criteria are testable;
- material risks and dependencies are visible;
- the package makes sense without the originating chat;
- no material section is based on invented facts.

Action:

- open a Foundry pull request;
- state the decisions Warwick is being asked to approve;
- perform a pre-review QA pass.

Gate D — Ready for Larry

Required:

- Warwick has approved the intended outcome;
- Warwick has approved material boundaries;
- the production destination is identified;
- no unresolved question would force Larry to invent policy;
- handoff QA passes.

Action:

- mark package Ready for Larry;
- create or reference the production build task;
- preserve bidirectional links.

Gate E — Implementation closure

Required:

- production implementation merged;
- required QA completed;
- material deviations recorded;
- accepted reusable outputs promoted;
- rejected or superseded proposals not promoted;
- Foundry package linked to the final result.

Action:

- update status to Implemented;
- record lessons;
- close the Foundry issue and PR where appropriate.

---

12. Role boundaries

Warwick

Warwick:

- supplies intent;
- explains desired outcomes;
- sets priorities;
- defines personal and product constraints;
- resolves contested decisions;
- approves the handoff;
- accepts or rejects material implementation deviations.

Fusion / ChatGPT

Fusion:

- facilitates the exploration;
- challenges premature solutions;
- checks for duplication;
- maintains the idea canvas;
- separates fact, assumption, decision and uncertainty;
- researches where required;
- develops the PRD;
- develops the implementation plan;
- produces the Larry handoff;
- runs the pre-handoff review;
- maintains traceability after build.

Fusion does not:

- approve its own material product decisions;
- silently change production governance;
- treat chat memory as authoritative;
- promote provisional conclusions into permanent "F247.*" material;
- create unnecessary files merely because a template exists.

Larry and builders

Larry:

- consumes the approved handoff;
- converts it into controlled production tasks;
- identifies technical gaps;
- escalates decisions rather than silently redefining intent;
- builds in the correct production repository;
- records deviations;
- provides links back to the Foundry package.

VerifiAIr and Claude QA

QA checks:

- source traceability;
- requirement coverage;
- acceptance criteria;
- duplicate capability;
- invented facts;
- schema drift;
- wrong repository or domain boundary;
- undocumented implementation deviation;
- leakage of raw brainstorm into permanent doctrine;
- consistency between Foundry handoff and production result.

---

13. Build work packages

WP-FND-001 — Minimum repository bootstrap

Purpose

Create the smallest usable Foundry structure.

Outputs

- "README.md"
- "docs/OPERATING-MODEL.md"
- "logs/SESSION-LOG.md"
- "logs/DECISION-LOG.md"
- "templates/"
- "ideas/"
- ".github/"

Acceptance criteria

- A new participant can understand the Foundry within five minutes.
- The README is a front door, not a duplicated manual.
- No permanent Drive governance is copied in as local authority.
- The repository contains no speculative database, dashboard or automation.
- The boundary between Foundry, Drive and production is explicit.

Dependency

Warwick approval of this plan.

---

WP-FND-002 — Idea canvas and lifecycle

Purpose

Implement the progressive one-document-first model.

Outputs

- "templates/IDEA-TEMPLATE.md"
- metadata standard;
- idea ID rules;
- status vocabulary;
- Gate A and Gate B instructions.

Acceptance criteria

- A seed issue can be created in under two minutes.
- "IDEA.md" can be understood without reopening the chat.
- Confirmed decisions are clearly distinguishable from provisional ones.
- Assumptions and uncertainty remain visible.
- The template does not force unnecessary empty documents.

---

WP-FND-003 — PRD and handoff package

Purpose

Ensure Larry receives consistent, build-ready material.

Outputs

- "templates/PRD-TEMPLATE.md"
- "templates/IMPLEMENTATION-PLAN-TEMPLATE.md"
- "templates/HANDOFF-TEMPLATE.md"
- "docs/HANDOFF-CONTRACT.md"

Acceptance criteria

- The handoff stands alone.
- Scope and exclusions are explicit.
- Production destinations are identified.
- Requirements map to acceptance criteria.
- Unresolved questions cannot be mistaken for approved requirements.
- Source provenance is included.
- Larry can begin technical planning without reconstructing the original conversation.

---

WP-FND-004 — GitHub issue and pull-request workflow

Purpose

Add a lightweight management layer around the Markdown artefacts.

Outputs

- idea issue form;
- pull-request template;
- label specification;
- issue-to-folder relationship;
- Foundry-to-production traceability rules.

Proposed status labels

status:seed
status:exploring
status:converging
status:ready-for-review
status:ready-for-larry
status:accepted-for-build
status:building
status:implemented
status:parked
status:rejected

Proposed type labels

type:feature
type:skill
type:agent
type:integration
type:architecture
type:process
type:research

Proposed area labels

area:fusion247
area:careerair
area:project-manager
area:personal-os
area:connectors
area:dashboard
area:knowledge

Acceptance criteria

- Issue status and idea metadata agree.
- Every active idea links to its source issue.
- Every handoff PR identifies its production destination.
- Production tasks link back to the Foundry idea.
- The process works without requiring a GitHub Project board.

Known implementation constraint

The current GitHub integration can read the repository but rejected direct file creation with a 403 integration-scope error.

Repository writes may initially require:

- a repaired GitHub app installation;
- Larry using GitHub CLI;
- Codex or Claude Code;
- manual creation through the GitHub interface.

---

WP-FND-005 — Google Drive provenance boundary

Purpose

Allow the Foundry to use Drive evidence without creating competing knowledge bases.

Outputs

- "docs/DRIVE-BOUNDARY.md"
- source-reference format;
- snapshot rule;
- stale-source check;
- source-access QA rule.

Rules

- Link to the canonical Drive object whenever possible.
- Record title, source role and access date.
- Copy source content into Git only when justified.
- Mark copied content as a dated snapshot.
- Never imply that a Foundry summary replaces its source.
- Do not update permanent Drive governance merely because an idea is being explored.
- Promotion into permanent Drive or production content requires a separate approved action.

Acceptance criteria

- Material claims in a handoff have traceable evidence.
- Drive and Git have clear, non-overlapping responsibilities.
- No silent duplication occurs.
- Missing access or stale evidence is disclosed.

---

WP-FND-006 — End-to-end pilot

Purpose

Prove the Foundry manually using a genuine idea.

Recommended pilot

Contextual Task Intelligence and Three-Times-Daily Brief Orchestration

This is a suitable pilot because it already includes:

- a real Warwick need;
- proactive task suggestions;
- timing and notification intelligence;
- priority-dependent lead times;
- meeting preparation;
- task dependencies;
- multiple potential connectors;
- a future dashboard dimension;
- clear risk of premature overengineering.

Pilot lifecycle

Seed issue
→ IDEA.md
→ structured exploration
→ options and architecture
→ decisions
→ PRD
→ implementation plan
→ handoff
→ Foundry review PR
→ Warwick approval
→ Larry production task
→ production build
→ QA
→ Foundry closure

Acceptance criteria

- No important context is dependent on the original chat.
- Warwick can review the package comfortably on mobile.
- Larry can understand what is required and what is not.
- Unresolved decisions remain visible.
- The process records useful provenance without becoming onerous.
- Lessons lead to evidence-based template refinement.

---

WP-FND-007 — QA and v0.1 baseline

Purpose

Stabilise the Foundry after the pilot.

Outputs

- "docs/QA-CHECKLIST.md"
- pilot lessons;
- corrected templates;
- Foundry-wide decision record;
- v0.1 release note;
- clear deferred-improvement list.

QA checklist

Before approving a handoff:

- Confirm the active idea ID.
- Confirm status.
- Search for duplicates.
- Confirm sources are accessible.
- Distinguish fact, decision, assumption and question.
- Check scope and exclusions for contradiction.
- Trace requirements to acceptance criteria.
- Trace implementation steps to requirements.
- Check that production artefacts are identified.
- Check that Larry is not being asked to invent policy.
- Confirm no permanent document was modified during brainstorming.
- Confirm the handoff makes sense without chat.
- Confirm material risks and dependencies.
- Confirm Warwick’s decisions are recorded.

After implementation:

- Link the production task and PR.
- Record deviations.
- Verify accepted outputs were promoted.
- Verify rejected alternatives were not accidentally promoted.
- Record lessons.
- Close the idea only after QA.

Acceptance criteria

- One real pilot has completed or produced enough evidence for a deliberate stop.
- Warwick approves the operating model.
- Templates are lean enough for repeated use.
- The process works without external task software.
- Deferred automation remains deferred unless evidence supports it.

---

14. Execution sequence

Following Warwick’s approval:

1. Create a dedicated bootstrap branch.
2. Complete WP-FND-001.
3. Complete WP-FND-002.
4. Complete WP-FND-003.
5. Complete WP-FND-004.
6. Complete WP-FND-005.
7. Open one Foundry bootstrap pull request.
8. Review the structure with Warwick in chat.
9. Amend the same PR where needed.
10. Merge only after Warwick approves the operating model.
11. Create the pilot seed issue.
12. Complete WP-FND-006.
13. Review the pilot and complete WP-FND-007.
14. Declare v0.1 only after the pilot validates the workflow.

The bootstrap should be one coherent PR rather than seven tiny ceremonial PRs.

The pilot should be its own separate PR and review cycle.

---

15. Non-goals for v0.1

Do not build:

- a second Fusion247 Brain;
- a full project ontology;
- a full PKA structure;
- SQLite;
- a hosted backend;
- a bespoke dashboard;
- semantic search;
- embeddings;
- autonomous idea promotion;
- automatic production merges;
- MeisterTask synchronisation;
- MindMeister synchronisation;
- a complex RAID database;
- one file per trivial task;
- duplicate copies of Drive governance;
- comprehensive governance for ideas that have not earned it.

---

16. Future enhancements only after v0.1

Potential later improvements:

GitHub Project view

A visual board driven by issue metadata:

Seed
Exploring
Converging
Warwick Review
Ready for Larry
Building
Implemented
Parked

This is a view over canonical issues, not a separate database.

MeisterTask capture adapter

Potential flow:

MeisterTask quick capture
→ Zapier
→ GitHub seed issue
→ GitHub becomes canonical

No bidirectional synchronisation should be attempted initially.

MindMeister source adapter

A map may be:

- linked;
- exported;
- attached as evidence;
- used during architecture sessions.

It does not become the decision or session-history system.

Automated Foundry QA

Possible later checks:

- missing metadata;
- broken source links;
- inconsistent status;
- missing acceptance criteria;
- unresolved questions in Ready-for-Larry packages;
- missing production links;
- accidental duplication of permanent artefacts.

Foundry dashboard

Only justified after the issue and Markdown model produces enough real data to show what Warwick genuinely needs to see.

---

17. Decisions requested from Warwick

Approval is requested for these decisions:

1. "Fusion247Foundry" is the canonical ideas, convergence and handoff layer.
2. GitHub Issues are the idea inbox.
3. An active idea begins with one "IDEA.md" canvas.
4. PRD, implementation plan and handoff split out only as the idea matures.
5. Status is stored in metadata and issues, not lifecycle folders.
6. Drive is a linked evidence store, not the Foundry source of truth.
7. A Foundry pull request is the Warwick review and handoff gate.
8. Larry builds from the approved handoff in the appropriate production repository.
9. Raw brainstorm material is not merged wholesale into production.
10. Only accepted outcomes are promoted into permanent "F247.*" material.
11. MeisterTask, MindMeister, dashboards and automation remain deferred adapters.
12. The first pilot uses a real idea rather than a synthetic example.
13. Foundry v0.1 is not approved until one end-to-end pilot validates it.
14. The bootstrap is delivered as one PR and reviewed in chat before merge.

---

18. Completion record

Completed

- Reviewed the current conversation.
- Confirmed the "Fusion247Foundry" repository exists.
- Confirmed the repository is currently empty.
- Reviewed the relevant Drive governance and build documents.
- Reconciled the previous Google Drive Foundry proposal with the Git-native Foundry proposal.
- Designed the progressive artefact model.
- Defined the Foundry lifecycle and gates.
- Defined roles and system boundaries.
- Produced seven implementation work packages.
- Produced the proposed execution sequence and acceptance criteria.

Partially completed

- Attempted to create "FOUNDRY-BUILD-PLAN.md" in the repository.

Blocked

GitHub rejected the file write with:

403 — Resource not accessible by integration

The connector can currently see the repository but cannot commit repository content.

Not completed

- No repository bootstrap files have been created.
- No branch has been created.
- No pull request has been opened.
- No labels have been created.
- No GitHub Project has been created.
- No pilot idea has been started.
- MeisterTask has not been enabled.
- MindMeister has not been connected.
- No Google Drive document has been changed.
- No production Fusion247 repository has been changed.
