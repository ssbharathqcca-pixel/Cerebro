# ROI OS Knowledge System

**Audit date:** 2026-09-26  
**Scope:** `Memory.md`, `AGENTS.md`, `ChatGPT-Sync.md`, `DECISIONS.md`, `STATE.md`, `EVALS.md`, and `RISKS.md` in the ChatGPT project mirror.

## Canonical model

There is no single file that is canonical for every kind of truth. Canonical ownership is category-specific:

| Information | Canonical owner | Rule |
|---|---|---|
| Observable implementation truth | Artifact, Git, tests, runtime, or primary external source | Outranks every narrative document |
| Current project state | Project-local `STATE.md` | Include date, source, observation, verification, and status |
| Durable decisions and rationale | `DECISIONS.md` | Append or supersede; do not silently rewrite history |
| Active risks and mitigations | `RISKS.md` | Update status and evidence when risk changes |
| Evaluation results | `EVALS.md` | Separate observed results from hypotheses and proposals |
| Durable cross-project context | `Memory.md` | Bootstrap and retrieval index, not live state |
| Persistent agent behavior | Lean `AGENTS.md` | Rules and routing pointers only |
| Immediate objective and acceptance criteria | Current task or handoff | Expires when the task closes |

Conflict order: **verified evidence → current project docs → current task context → durable memory → historical memory**.

## Findings

1. **“Canonical Memory” is ambiguous.** `Memory.md` is canonical only for durable cross-project context. `STATE.md` and verified artifacts are canonical for current facts.
2. **`Memory.md` duplicates other layers.** Its sync protocol, agent contract, current project matrix, risks, evaluation lessons, and appendices substantially repeat `AGENTS.md`, `STATE.md`, `DECISIONS.md`, `RISKS.md`, and `EVALS.md`.
3. **The sync guide is incomplete.** `ChatGPT-Sync.md` says to refresh sources but does not define file ownership, conflict resolution, revision proof, or failure recovery.
4. **State language overreaches.** `STATE.md` calls a seven-file set “canonical context artifacts”; this should be a role map, because authority depends on the information category.
5. **Evidence records need stronger provenance.** Several `EVALS.md` entries are historical observations or design principles without artifact links, reproduction details, versions, or dates.

## Sync protocol

1. **Classify at capture time (1 min).** Put verified current facts in project `STATE.md`; rationale in `DECISIONS.md`; risks in `RISKS.md`; test observations in `EVALS.md`; cross-project durable context in `Memory.md`; agent rules in `AGENTS.md`.
2. **Update one owner (2–10 min).** Link from other files instead of copying prose. Mark claims `VERIFIED`, `HISTORICAL`, `UNVERIFIED`, or `TIME-SENSITIVE` where ambiguity matters.
3. **Verify before promotion (2–15 min).** Record date, source/artifact, check performed, and result. A chat statement is not verification.
4. **Publish and refresh (2–5 min).** Commit authoritative repository files where Git exists, then replace the corresponding ChatGPT Project source. Record source revision or SHA-256 and refresh time in the work report.
5. **Reconstruct selectively (under 2 min).** ChatGPT and Codex read lean instructions first, then only task-relevant state/decision/risk/eval sections. On conflict, apply the hierarchy above and flag unresolved divergence.

## Proposed upstream edits

- `ChatGPT-Sync.md`: replace “Memory.md = canonical durable context” with “canonical for durable cross-project context”; add the five-step protocol and a refresh receipt (`file`, `revision/hash`, `refreshed_at`, `actor`).
- `STATE.md`: rename “Canonical context artifacts” to “Knowledge-system role map”; add `last_verified_at`, source, and status to each live project claim.
- `DECISIONS.md`: accept a new decision formalizing category-specific authority and close Q-005 only after the refresh-receipt workflow is tested.
- `EVALS.md`: distinguish `Observed`, `Historical report`, `Hypothesis`, and `Design principle`; require evidence/reproduction fields before an item is called confirmed.
- `Memory.md`: prune duplicated operating contracts and current-state sections after upstream files are updated; keep compact summaries and links, with project specifics marked historical unless verified.

## Synchronization constraints

- This folder is a generated local mirror. Everything under `sources/` is read-only and may be replaced when a future task refreshes the ChatGPT Project.
- ChatGPT Project context and Codex chat history are separate product surfaces. Neither should be assumed to update the other automatically.
- ChatGPT project memory is retrieval context, not an inspectable authoritative database; project settings and plan/workspace rules affect what can be recalled.
- The current mirror is not a Git working tree, so these local changes cannot be committed or pushed here.
- Durable Codex memory is a separate store with its own update controls. Project files should remain the portable source; any Codex-memory entry should be a small pointer/summary, not a competing copy.

## Acceptance check

- Lean `AGENTS.md` carries the conflict hierarchy without duplicating the knowledge base.
- The ownership table assigns one canonical home per information category.
- The protocol requires verification and a refresh receipt.
- Synced source files remain unchanged.
