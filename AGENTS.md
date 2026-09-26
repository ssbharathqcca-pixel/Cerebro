# AGENTS.md — ROI / Codex Operating Contract

Roi is an AI systems/product researcher and builder.

## Core principles

- Performance > Claims
- Verify > Confidence
- Evidence > Reputation
- Execution > Prose
- Signal > Noise
- RedTeam > Trust
- Value > Features
- Leverage > Busywork

## Repository rules

1. Inspect branch, working tree, and relevant files before editing.
2. Treat current Git/files/tests/runtime evidence as stronger than historical memory.
3. Modify the actual repository; do not substitute pasted code for file changes.
4. Preserve unrelated work.
5. Keep changes scoped to the task.
6. Run relevant verification.
7. Inspect the resulting diff/state.
8. Report exact changed files and actual test results.
9. Never fabricate completion.
10. Surface unresolved issues.

## Context

Cross-project durable context lives in:

`Memory.md`

Read relevant portions only when needed. Do not mechanically load the entire file for every task.

Prefer current project-specific documents for current truth:

- `STATE.md`
- `PROJECT.md`
- `DECISIONS.md`
- `RISKS.md`
- `ARCHITECTURE.md`
- tests/source files

Current repository state outranks historical memory.

## Task contract

For substantial work, use:

OBJECTIVE
CURRENT STATE
PROBLEM
SCOPE
NON-GOALS
IMPLEMENTATION
ACCEPTANCE CRITERIA
VERIFICATION
DONE DEFINITION

## High-risk actions

Be especially deliberate with:

- deletion
- destructive operations
- authentication/authorization
- credentials/secrets
- payments
- licensing
- external side effects
- irreversible data changes

## OpenAI work

For OpenAI API, ChatGPT, Codex, plugins, or OpenAI-specific tooling, prefer current authoritative OpenAI developer documentation where available.

## Astra context discipline

Keep persistent instructions lean. Point to relevant documents instead of requiring the entire repo/documentation stack to be read before every small task.

## Definition of done

Intent → implementation → relevant verification → diff/state inspection → truthful report

A generated answer is not a completed repository change.
