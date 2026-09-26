# ROI AI SYSTEMS — RISK REGISTER

**Snapshot:** 2026-09-26  
**Purpose:** Track high-leverage risks across the collaboration, products, research, and AI-agent infrastructure.

---

# Risk Scoring

Use:

**Impact:** 1–5  
**Likelihood:** 1–5  
**Priority:** Impact × Likelihood

Do not treat the numeric score as mathematically precise. It is a triage tool.

---

# R-001 — Hallucinated Completion

**Area:** All AI agents  
**Impact:** 5  
**Likelihood:** 4  
**Status:** Active

## Failure

Agent claims work was completed when the artifact was not actually modified or verified.

## Mitigation

- inspect files
- inspect Git
- run tests
- inspect diff
- require evidence in completion report

---

# R-002 — Self-Certification

**Area:** AI generation/evaluation  
**Impact:** 5  
**Likelihood:** 4  
**Status:** Active

## Failure

The same model generates output and decides that the output is correct.

## Mitigation

Independent critique + deterministic validation where possible.

---

# R-003 — Context Bloat

**Area:** ChatGPT / Codex  
**Impact:** 4  
**Likelihood:** 4  
**Status:** Active

## Failure

Huge instruction/context stacks consume attention and reduce task effectiveness.

## Mitigation

Keep:

- Memory rich
- AGENTS lean
- State current
- Task prompt focused

---

# R-004 — Stale Memory

**Area:** Synchronization  
**Impact:** 4  
**Likelihood:** 4  
**Status:** Active

## Failure

Historical Memory.md is mistaken for current product/repository state.

## Mitigation

Current artifacts outrank historical memory.

---

# R-005 — Divergent Context Copies

**Area:** ChatGPT ↔ Codex  
**Impact:** 4  
**Likelihood:** 3  
**Status:** Active

## Failure

ChatGPT and Codex each operate from different versions of project knowledge.

## Mitigation

Version shared Markdown through Git.

---

# R-006 — Documentation Duplication

**Area:** Knowledge system  
**Impact:** 3  
**Likelihood:** 4  
**Status:** Active

## Failure

Memory, State, Decisions, and Project docs repeat/conflict with each other.

## Mitigation

Each file has one clear semantic role.

---

# R-007 — Dangerous Repository Changes

**Area:** Coding agents  
**Impact:** 5  
**Likelihood:** 3  
**Status:** Active

## Failure

Agent modifies/deletes unrelated files or introduces irreversible behavior.

## Mitigation

- inspect status first
- constrain scope
- inspect diff
- use safe commands
- test destructive paths

---

# R-008 — Destructive Software Failure

**Area:** DiskPrune  
**Impact:** 5  
**Likelihood:** 3  
**Status:** Historical / requires current verification

## Failure

Cleanup affects the wrong files or system state.

## Mitigation

Explicit selection, preview, safeguards, test fixtures, and destructive-operation tests.

---

# R-009 — Payment State Fabrication

**Area:** DiskPrune / future products  
**Impact:** 5  
**Likelihood:** 2  
**Status:** Historical / requires current verification

## Failure

Frontend displays success without trustworthy backend/provider confirmation.

## Mitigation

Treat payment provider/backend state as authoritative.

---

# R-010 — Weak License Validation

**Area:** Commercial software  
**Impact:** 4  
**Likelihood:** 3  
**Status:** Historical / requires current verification

## Failure

Presence of a local credential is mistaken for valid authorization.

## Mitigation

Cryptographically / backend-validated license state.

---

# R-011 — Vendor / Model Overconfidence

**Area:** AI strategy  
**Impact:** 3  
**Likelihood:** 4  
**Status:** Active

## Failure

A model is chosen based on reputation rather than measured task performance.

## Mitigation

Benchmark on real workloads.

---

# R-012 — Post-Hoc Reasoning Misinterpretation

**Area:** AI research  
**Impact:** 4  
**Likelihood:** 4  
**Status:** Active

## Failure

A model explanation is treated as evidence of the actual internal causal mechanism.

## Mitigation

Controlled interventions, ablations, repeated trials, behavioral evidence.

---

# R-013 — Marketing / Product Drift

**Area:** Products  
**Impact:** 4  
**Likelihood:** 3  
**Status:** Active

## Failure

Marketing promises behavior the implementation does not provide.

## Mitigation

Claim-vs-implementation audit before launch.

---

# R-014 — Excessive Multi-Agent Complexity

**Area:** AI orchestration  
**Impact:** 4  
**Likelihood:** 3  
**Status:** Active

## Failure

Adding agents creates coordination overhead greater than the capability gain.

## Mitigation

Require measurable leverage for every additional agent.

---

# R-015 — Credential / IP Exposure

**Area:** External AI  
**Impact:** 5  
**Likelihood:** 2  
**Status:** Active

## Failure

Secrets, private repositories, or unreleased IP are unnecessarily exposed.

## Mitigation

Least privilege, secret stripping, scoped context, local processing where appropriate.

---

# R-016 — PEOS Trust Boundary Failure

**Area:** PEOS  
**Impact:** 5  
**Likelihood:** 3  
**Status:** Active

## Failure

Intent, attempted execution, actual execution, verification, and attribution are collapsed.

## Mitigation

Explicit state machine and verified-outcome eligibility boundary.

---

# R-017 — Execution Friction

**Area:** Roi workflow  
**Impact:** 4  
**Likelihood:** 4  
**Status:** Active

## Failure

Important work stalls because activation/setup/decision cost is high.

## Mitigation

- next-action engine
- reduced choices
- artificial deadlines
- automation
- short execution loops

---

# R-018 — Knowledge Rot

**Area:** Cerebro / Memory  
**Impact:** 3  
**Likelihood:** 4  
**Status:** Active

## Failure

Old context accumulates until useful signal is buried.

## Mitigation

Periodic pruning and explicit durable/ephemeral classification.

---

# R-019 — False Research Generalization

**Area:** AI evaluation  
**Impact:** 4  
**Likelihood:** 3  
**Status:** Active

## Failure

One surprising example is generalized into a broad capability claim.

## Mitigation

Repeated trials, controlled variants, reproduction, uncertainty bounds, limitations.

---

# R-020 — Time-Sensitive Fact Drift

**Area:** Immigration, software, pricing, public facts  
**Impact:** 5  
**Likelihood:** 4  
**Status:** Active

## Failure

Historical information is presented as current.

## Mitigation

Fresh web/primary-source verification when the answer depends on current facts.
