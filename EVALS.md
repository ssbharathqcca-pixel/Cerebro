# ROI AI SYSTEMS — EVALUATION REGISTRY

**Snapshot:** 2026-09-26  
**Purpose:** Record what has actually been tested, what the result was, and what remains unverified.

> This is an evidence registry. It should contain observations and test results, not vibes.

---

# Evaluation Record Format

```markdown
# EVAL-XXX — Title

## Hypothesis

## System

## Version / Date

## Environment

## Task

## Expected

## Observed

## Evidence

## Reproduction

## Limitations

## Result

## Confidence

## Follow-up
```

---

# EVAL-001 — Repository-Agent Completion

**Status:** Observed repeatedly

## Hypothesis

An AI coding agent can falsely report repository completion if the task prompt does not require explicit file/diff/test verification.

## Observed

Historical workflows included agents/models generating or pasting code/JSON in chat instead of completing the requested repository file changes.

## Result

**Failure mode confirmed as a workflow risk.**

## Mitigation

Require:

- actual file modification
- changed-file report
- diff inspection
- tests
- unresolved issues

---

# EVAL-002 — Model Self-Reported Reasoning

**Status:** Research observation

## Hypothesis

A model's verbal explanation after an output is not necessarily the causal process that produced that output.

## Observed

In recent analysis of a model-selection behavior, selection appeared to occur through filtering/selection behavior before a post-hoc explanation was requested.

## Result

Treat verbalized reasoning as **reported explanation**, not automatically as a causal trace.

## Follow-up

Formalize controlled intervention tests.

---

# EVAL-003 — DiskPrune Safety Audit

**Status:** Historical audit

## Scope

- purge behavior
- local Time Machine snapshot deletion
- Stripe webhook
- license activation
- payment success state
- marketing/product parity

## Historical observations

Multiple high-risk trust-boundary defects were identified.

## Result

Product required security/safety hardening before strong trust claims.

## Current status

Re-test current repository because implementation may have changed.

---

# EVAL-004 — PEOS Execution Semantics

**Status:** Historical milestone

## Scope

Define distinction between:

```text
Attempted execution
Executed work
Verified outcome
Attribution
```

## Result

Battles 13–15 were used to formalize these boundaries.

## Current status

Battle 16 and all later changes require Git verification.

---

# EVAL-005 — Content Pipeline Integrity

**Status:** Design/evaluation principle

## Scope

French lesson/content generation.

## Pipeline

```text
generation
→ correction
→ independent critique
→ deterministic validation
→ duplication check
→ source check
→ confidence
→ founder sample
```

## Result

The workflow is intended to prevent one model from silently certifying its own output.

## Current status

The actual implementation should be inspected before claiming the pipeline is fully automated.

---

# EVAL-006 — Capability Boundary Probing

**Status:** Method established; benchmark not finalized

## Objective

Measure latent capability by composing available primitives.

## Result

Conceptually established as a reusable AI evaluation method.

## Missing

- formal benchmark suite
- standardized scoring
- reproducibility harness
- public result archive

---

# EVAL-007 — Multi-Agent Specialization

**Status:** Working hypothesis

## Hypothesis

Specialized agents can outperform a single generalist when tasks have genuinely separable capabilities.

## Required evidence

Compare:

```text
single model
vs
specialized pipeline
```

on identical tasks using:

- accuracy
- completion rate
- latency
- token/cost consumption
- verification burden
- failure severity

---

# EVAL-008 — Context Compression

**Status:** Open experiment

## Hypothesis

A concise role-specific instruction layer plus targeted retrieval will outperform blindly injecting a giant memory document into every task.

## Proposed comparison

### Condition A
Full memory every task.

### Condition B
Lean AGENTS + targeted context.

### Condition C
Lean AGENTS + state + targeted project docs.

Measure:

- task success
- errors
- latency
- context consumption
- unnecessary tool calls

---

# EVAL-009 — ChatGPT / Codex Synchronization

**Status:** Architecture under development

## Hypothesis

Explicit shared Markdown + Git state can create more reliable cross-agent synchronization than relying on hidden conversational memory alone.

## Proposed evidence

Run equivalent tasks with:

1. conversation-only handoff
2. Memory-only handoff
3. Memory + project state
4. Memory + state + decisions + Git

Compare:

- context reconstruction accuracy
- incorrect assumptions
- task completion
- stale-state errors
- unnecessary rework

---

# EVAL-010 — AI Execution Friction

**Status:** Open research direction

## Hypothesis

A task-prioritization/execution layer can reduce activation friction and increase completion rate.

## Suggested metrics

- time-to-first-action
- task completion rate
- abandoned tasks
- context switches
- decision count
- reminder/escalation events
- subjective friction

---

# Current Evaluation Gaps

1. Formal PEOS benchmark.
2. Formal Capability Boundary Probing benchmark.
3. Model-routing benchmark.
4. ChatGPT/Codex context-sync benchmark.
5. AI Execution Machine outcome metrics.
6. Public reproducibility repository.
7. Longitudinal evidence that multi-agent workflows outperform simpler baselines.

---

# EVAL-011 — Cerebro Synchronization Baseline

**Status:** Verified repository baseline  
**Date:** 2026-09-26

## Task

Establish Cerebro as the canonical repository and import the ROI OS memory,
state, decisions, risks, evaluations, agent contract, and sync documentation.

## Observed

The repository began at commit `4659c5d` with only `README.md`. The context
documents were imported from the ROI OS ChatGPT Project mirror and a
category-specific authority model was added.

## Evidence

Git diff, file inventory, Markdown link checks, and the resulting Cerebro commit.

## Limitations

Refreshing the ChatGPT Project source is a separate product action. Codex chat
history is also separate and must not be treated as automatically synchronized.
