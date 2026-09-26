# ROI AI SYSTEMS — CURRENT STATE

**Snapshot:** 2026-09-26  
**Rule:** This file is deliberately conservative. A statement here should represent the latest *known* state, not an old claim that merely sounds current.

---

# 1. Global State

## Collaboration

The current strategic model is:

```text
ChatGPT / Luna
→ research
→ architecture
→ synthesis
→ adversarial review
→ planning

Astra / Codex
→ repository inspection
→ implementation
→ tests
→ debugging
→ difficult coding execution

Deterministic systems
→ validation
→ invariants
→ schemas
→ tests

Human
→ final judgment
→ acceptance
→ consequential decisions
```

## Context synchronization

Knowledge-system role map:

```text
Memory.md
DECISIONS.md
PROJECT.md
STATE.md
RISKS.md
EVALS.md
AGENTS.md
```

---

# 2. Memory System State

**Current goal:** Establish a portable, explicit memory layer that can be used across ChatGPT and Codex/Astra.

**Current canonical file:**

`Memory.md`

**Purpose:** durable collaboration context.

**Important:** It is not a live implementation state database.

---

# 3. Decision System State

**Current canonical file:**

`DECISIONS.md`

**Purpose:** record durable architectural/strategic choices and their rationale.

**Current state:** initial decision log created.

---

# 4. Project Documentation State

The intended standard now includes:

```text
PROJECT.md
STATE.md
DECISIONS.md
RISKS.md
EVALS.md
AGENTS.md
```

These should be maintained close to the relevant repository/project.

Authority is category-specific. Verified artifacts and primary sources outrank
all narrative documentation; `Memory.md` is canonical only for durable
cross-project context.

---

# 5. PEOS State

Historical verified milestones exist in Memory/Decision documentation.

Reported recent state:

- branch: `codex/product-ui-phase1`
- Battle 16 work was reported as completed
- previous HEAD reference: `d637fbeaab51dc98d7ebfc3a65fd3fddb24b3ff9`

**CURRENT VERIFICATION REQUIRED**

Do not use the above as present repository truth until Git/repository inspection confirms it.

Required refresh:

```text
git status
git branch
git log -n 10
git diff
test suite
current UI/product flow
```

---

# 6. Project Pulse State

Historical status:

- post-MVP capabilities were reported in draft PR `#11`.

**Current verification required.**

---

# 7. Cerebro State

**Strategic state:** Cerebro is intended to become the human-controlled knowledge layer.

**Open work:**

- finalize exact folder/schema conventions
- establish durable migration workflow
- determine relationship between project docs and global memory
- avoid turning Cerebro into an unmaintainable note dump

---

# 8. DiskPrune State

**Product direction:**

- free scanning
- paid cleanup
- lifetime purchase model was explored
- developer-storage wedge

**Critical engineering state:**

Prior audit identified trust/security defects.

**Current verification required before further product claims:**

- inspect purge selection
- inspect Time Machine deletion behavior
- inspect Stripe webhook verification
- inspect license validation
- inspect payment success state
- inspect marketing/product parity
- test destructive flows

---

# 9. Sonolo State

Historical architecture is documented in `Memory.md` and `PROJECT.md`.

**Current verification required** before changing architecture or claiming current feature completeness.

---

# 10. French Mastery Lab State

**Current strategy:**

- one-time product model
- static/local-first bias
- customer-owned inference where practical
- gated content pipeline

**Known historical lesson:**

An agent/model generated content in chat instead of updating files. File-level execution verification remains mandatory.

---

# 11. AI Execution Machine State

Still primarily an architecture/product concept.

Core design remains:

```text
intent
→ priority
→ next action
→ execution
→ verification
→ escalation/recovery
```

---

# 12. Capability Boundary Probing State

Method is conceptually established.

Remaining opportunity:

- formalize benchmark/test harness
- define capability taxonomy
- define evidence requirements
- create reproducibility protocol
- publish findings

---

# 13. Open Blockers / Questions

1. Exact Cerebro filesystem/schema.
2. Final PEOS state after Battle 16.
3. Standard repository documentation template.
4. Permanent model-routing matrix.
5. Automated Memory ↔ Cerebro synchronization.
6. Stronger ChatGPT ↔ Codex state synchronization.
7. Publication-grade AI evaluation harness.

---

# 14. State Update Rule

A current-state claim should ideally include:

```text
DATE
SOURCE
OBSERVATION
VERIFICATION
STATUS
```

Example:

```text
2026-09-26
Source: Git
Observation: branch X contains commit Y
Verification: tests A/B/C pass
Status: verified
```

This keeps state from becoming another narrative memory dump.
