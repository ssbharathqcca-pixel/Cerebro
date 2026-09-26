# ROI — Canonical Decision Log

**Version:** 1.0  
**Snapshot:** 2026-09-26  
**Purpose:** Durable record of important technical, product, research, and collaboration decisions.

> `Memory.md` = durable collaboration knowledge  
> `DECISIONS.md` = why important choices were made  
> `STATE.md` = what is true now  
> `AGENTS.md` = how coding agents should operate

---

## Decision format

Each durable decision should record:

- Context
- Problem
- Decision
- Why
- Alternatives
- Trade-offs
- Consequences
- Reversal conditions
- Date
- Evidence

---

# D-001 — Use Explicit Canonical Memory

**Status:** Accepted

Maintain a portable `Memory.md` as the durable collaboration context for Roi and AI collaborators.

**Rationale:** Hidden AI memory is useful but is not a reliable, inspectable, portable database of every important fact. A Markdown artifact can be versioned, reviewed, committed, backed up, and moved between AI systems.

---

# D-002 — Separate Memory, Instructions, State, and Tasks

**Status:** Accepted

Maintain distinct layers:

```text
Memory.md       → durable knowledge
AGENTS.md       → operating instructions
STATE.md        → current project state
DECISIONS.md    → why important choices were made
Task / issue    → what must happen now
```

**Rationale:** These layers change at different rates and serve different purposes. One giant context file would become noisy and stale.

---

# D-003 — Current Artifacts Outrank Historical Memory

**Status:** Accepted

For engineering work, actual files, Git state, tests, builds, and runtime behavior outrank historical memory.

Preferred hierarchy:

```text
actual artifact / Git / tests / runtime
    > current project docs
    > current conversation
    > historical Memory.md
```

**Rationale:** Memory can become stale. Repository state is the better source of truth for implementation.

---

# D-004 — Keep AGENTS.md Lean

**Status:** Accepted

`AGENTS.md` should contain concise persistent operating rules and pointers to deeper documentation. It should not duplicate all of `Memory.md`.

**Rationale:** Large always-injected instruction stacks waste context and can distract an agent from the active task.

---

# D-005 — Use a ChatGPT Project for Long-Running Cross-Project Context

**Status:** Accepted

Maintain a dedicated ChatGPT Project for Roi's AI systems work, with `Memory.md`, relevant sources, and project instructions.

**Rationale:** This creates a stable workspace for related chats/files/instructions while preserving a portable canonical memory artifact.

---

# D-006 — Synchronize ChatGPT and Codex Through Explicit Artifacts

**Status:** Accepted

Do not depend on hidden cross-product memory synchronization. Use explicit shared artifacts and Git:

```text
Memory.md
AGENTS.md
STATE.md
DECISIONS.md
Git
```

**Rationale:** ChatGPT and Codex operate in different contexts and execution environments. Explicit artifacts are inspectable and portable.

---

# D-007 — Luna / Astra Role Separation

**Status:** Accepted

Use ChatGPT/Luna primarily for research, architecture, strategic reasoning, cross-project synthesis, planning, prompt engineering, and review.

Use Astra/Codex primarily for repository inspection, implementation, refactoring, testing, debugging, builds, and difficult coding execution.

**Rationale:** Complementary environments are more useful than forcing one agent to own every task.

---

# D-008 — Select Models by Measured Performance

**Status:** Accepted

Model assignments must follow observed performance on actual tasks rather than reputation, branding, or benchmark mythology.

**Rationale:** Different models have different strengths, costs, tool access, and failure modes.

---

# D-009 — Specialize Multi-Model Pipelines When They Create Measurable Leverage

**Status:** Accepted

For high-value workflows, separate functions such as:

```text
generation
→ correction
→ independent critique
→ deterministic validation
→ human sample review
```

**Rationale:** One model should not automatically generate, judge, and certify its own output.

**Caveat:** More agents are not inherently better; coordination cost must be justified by measured improvement.

---

# D-010 — Deterministic Validation Is a First-Class Gate

**Status:** Accepted

Use deterministic validation wherever requirements can be expressed mechanically:

- schemas
- duplicate checks
- source checks
- tests
- type checks
- lint
- invariant checks
- builds

**Rationale:** Probabilistic models can produce plausible errors. Mechanical checks provide stronger guarantees for mechanical properties.

---

# D-011 — Attempted Work Is Not Executed Work

**Status:** Accepted

For PEOS and other execution systems, distinguish:

```text
intent
→ attempted action
→ tool invocation
→ actual execution
→ verified outcome
→ attribution
```

**Rationale:** Collapsing these states creates false success and destroys trust.

---

# D-012 — Repository Agents Must Modify Real Artifacts

**Status:** Accepted

When instructed to implement repository work, an agent must modify the requested files rather than merely pasting code/JSON into chat.

**Definition of done:** repository changes + relevant verification + diff/state inspection + truthful report.

**Rationale:** Generated text is not equivalent to an implementation.

---

# D-013 — Dangerous Operations Need Elevated Verification

**Status:** Accepted

Deletion, payment, licensing, authentication, authorization, and irreversible state changes require stronger verification than ordinary text/UI changes.

**Rationale:** Failures can create irreversible data, financial, or security harm.

---

# D-014 — DiskPrune Is Trust-First

**Status:** Accepted

DiskPrune should prioritize safe, explicit, reviewable cleanup over aggressive automation.

Historical audit findings that informed this decision included reported issues with:

- purge affecting more than explicit user selection
- unconditional Time Machine snapshot deletion
- missing Stripe webhook signature verification
- weak license validation
- fabricated/assumed payment success state
- marketing claims for a review workflow not present in the product

**Consequence:** Future cleanup, payment, and licensing work starts with a trust-boundary audit.

---

# D-015 — One-Time / Local-First Products Are Strategically Valuable

**Status:** Accepted as a product preference

For suitable independent products, prefer one-time payment, static/local-first architecture, minimal recurring infrastructure, and customer-owned AI inference where practical.

**Rationale:** Can reduce ongoing cost, maintenance, vendor dependency, and operational complexity.

---

# D-016 — Product Progression: Simple → Useful → Trustworthy → Sellable → Scalable

**Status:** Accepted

Use this as a product-development heuristic.

**Rationale:** Feature volume should not precede customer value and trust.

---

# D-017 — Capability Must Be Demonstrated, Not Assumed

**Status:** Accepted research principle

Use Capability Boundary Probing to test what systems can actually do, including capabilities that emerge by composing available primitives.

**Method:**

```text
claimed boundary
→ accessible primitives
→ composition
→ probe
→ observed behavior
→ variation
→ reproducibility
→ classification
```

**Rationale:** UI/marketing claims and apparent one-off outputs are insufficient evidence of general capability.

---

# D-018 — Post-Hoc Model Explanations Are Not Automatically Causal Evidence

**Status:** Accepted research principle

Do not assume a model's verbal explanation is the mechanism that caused its behavior.

**Preferred evidence for mechanism claims:** controlled interventions, ablations, repeated trials, and behavioral evidence.

---

# D-019 — Build Professional Evidence From Real Work

**Status:** Accepted

Prefer:

```text
real work
→ artifact
→ independent validation
→ public record
```

over self-described prestige.

**Rationale:** Independently verifiable evidence is more durable and defensible.

---

# D-020 — Cerebro Is the Human-Controlled Knowledge Layer

**Status:** Strategic direction

Use Cerebro as the durable second-brain/knowledge system for research, project knowledge, decisions, reusable methods, lessons learned, and memory migration.

**Rationale:** Important knowledge should remain explicit, portable, and controlled by Roi rather than trapped in conversational history.

---

# D-021 — Minimize Context Waste

**Status:** Accepted

Large context should be available but loaded selectively.

Preferred flow:

```text
task
→ identify relevant domain
→ load relevant context
→ inspect actual artifact
→ execute
→ verify
```

**Rationale:** More context is not automatically more useful context.

---

# D-022 — Convert Important Failures Into Reusable Rules

**Status:** Accepted

When a system fails, record the reusable lesson, not only the incident.

Example:

```text
Failure: agent claimed it updated files but only pasted JSON.
Lesson: artifact creation must be verified at filesystem/Git level.
```

**Rationale:** The engineering system should become harder to fool over time.

---

# D-023 — Do Not Let the AI Define Its Own Success Criteria

**Status:** Accepted

Success conditions should come from the task specification, acceptance criteria, tests, or independent review.

**Rationale:** Self-defined completion enables self-certified failure.

---

# D-024 — Human Retains Decision Authority

**Status:** Accepted

AI should improve information quality and execution but not make consequential personal, legal, financial, political, or irreversible decisions on Roi's behalf.

**Consequence:** Provide evidence, alternatives, risks, and implications; preserve human agency.

---

# D-025 — Optimize for Reliable Progress, Not Conversational Impressiveness

**Status:** Foundational

The overall objective is:

```text
reliable progress
→ verified artifacts
→ reusable systems
→ public evidence
→ product / business leverage
```

A tested artifact is more valuable than a brilliant discussion that changes nothing.

---

# D-026 — Current State Requires Explicit Documentation

**Status:** Proposed / not yet universal

For serious repositories, consider standardizing:

```text
PROJECT.md
STATE.md
DECISIONS.md
RISKS.md
EVALS.md
```

**Reason:** This cleanly separates current status, rationale, risks, and evaluation evidence.

**Reversal condition:** If the documentation burden materially slows execution without improving recoverability or verification.

---

# D-027 — Canonical Memory vs Cerebro Boundary

**Status:** Strategic direction, not fully finalized

Working model:

```text
Memory.md
→ portable AI collaboration bootstrap

Cerebro
→ full human-controlled knowledge system
```

**Open issue:** Determine whether updates can eventually be synchronized automatically without creating conflicting sources of truth.

---

# D-028 — Category-Specific Authority and Cerebro Sync

**Status:** Accepted  
**Date:** 2026-09-26

Cerebro is the human-controlled canonical repository for the ROI OS knowledge
system. Authority remains category-specific: verified artifacts own observable
truth, `STATE.md` owns current state, `DECISIONS.md` owns rationale,
`RISKS.md` owns active risks, `EVALS.md` owns evaluation evidence, and
`Memory.md` owns durable cross-project context.

ChatGPT Project sources and Codex context are synchronized projections of
Cerebro, not independent canonical copies. Every material refresh requires a
Cerebro commit plus a sync receipt. Unverified refreshes are incomplete.

**Rationale:** A single repository provides reviewable history and recovery,
while category ownership prevents one large memory file from overriding current
evidence or duplicating every other document.

**Reversal condition:** Replace this model only if an automated system provides
equivalent provenance, conflict handling, inspectability, and recovery.

---

# OPEN DECISION QUEUE

## Q-001 — Final Cerebro schema

Finalize folders, links, note types, and archival rules.

## Q-002 — PEOS post-Battle-16 architecture

Inspect the repository before treating the historical battle report as current truth.

## Q-003 — Permanent model-routing matrix

Run comparable task evaluations before making durable vendor assignments.

## Q-004 — Universal project-doc standard

Decide whether all substantial repos should require PROJECT/STATE/DECISIONS/RISKS/EVALS.

## Q-005 — Memory/Cerebro synchronization

Define a controlled update protocol and source-of-truth hierarchy.

---

# Decision Hygiene

When adding a decision:

1. State the decision clearly.
2. Record the problem it solves.
3. Record material alternatives.
4. Record trade-offs.
5. Record reversal conditions.
6. Date it.
7. Link evidence.
8. Mark superseded decisions instead of silently deleting them.
9. Keep temporary implementation details in project docs unless they are durable decisions.
10. Never rewrite the rationale merely because the outcome became known later.
