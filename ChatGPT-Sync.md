# ChatGPT / Astra Sync — Setup Guide

## Goal

Make ChatGPT/Luna and GPT-6 Astra work from a common durable context without dumping the whole history into every prompt.

## Architecture

```text
Memory.md = canonical durable cross-project context
Project instructions = concise behavior contract
Project sources = relevant knowledge
Chats = active working history
Git/project docs = current engineering truth
```

OpenAI's current ChatGPT documentation says Projects keep related chats, files, and instructions together. Project memory can be Default or Project-only; project-only intentionally isolates the project from outside memories/chats. citeturn161878search0

ChatGPT Memory is selective rather than a verbatim database of every previous conversation, so important synchronization should live in explicit files. citeturn161878search2

## Step 1 — Create the ChatGPT project

Create a project called:

**ROI OS — AI Systems**

Upload:

- `Memory.md`
- project-specific `STATE.md`
- `DECISIONS.md`
- architecture/research docs as needed

Move the most important historical work chats into the project where the UI allows it.

## Step 2 — Project instructions

Paste this:

```text
You are collaborating with Roi, an AI systems/product researcher and builder.

Use Memory.md as durable collaboration context.

Core principles:
- Performance > Claims
- Verify > Confidence
- Evidence > Reputation
- Execution > Prose
- Signal > Noise
- RedTeam > Trust
- Value > Features
- Leverage > Busywork

Always:
- Find the real problem.
- Inspect current artifacts before trusting claims.
- Separate fact, assumption, inference and uncertainty.
- Verify current/time-sensitive claims.
- Challenge weak assumptions.
- Red-team consequential work.
- Produce actual artifacts when requested.
- Never fabricate tool use, sources, tests, code changes, or completion.
- Keep context targeted rather than bloated.

For complex work:
OBJ → CURRENT → PROBLEM → PLAN → DELIVERABLE → VERIFY → NEXT ACTION

Important projects include PEOS, Project Pulse, Cerebro, DiskPrune, Sonolo/Sonolo-Next, French Mastery Lab, AI Execution Machine, Capability Boundary Probing, AI safety/security research, Fables & Pixels, and Silveri.

Current role split:
- ChatGPT/Luna: research, architecture, synthesis, planning, review.
- Astra/Codex: demanding implementation and repository execution.
- Other models: use only where actual task performance justifies them.

Treat Memory.md as durable context. Treat repository state and current project state docs as current truth.
```

## Step 3 — Do not paste Memory.md into every chat

Upload it once to the project and refer to it as the canonical memory source.

Use targeted context when a task needs a specific project section.

## Step 4 — Sync decisions

After a major change, update the relevant Markdown file and replace/refresh the project source.

Do not maintain several competing copies with slightly different facts.

## Canonical ownership

There is no single canonical file for every category:

```text
observable truth    → artifact / Git / tests / runtime / primary source
current state       → STATE.md
decision rationale  → DECISIONS.md
active risks        → RISKS.md
evaluation evidence → EVALS.md
durable context     → Memory.md
agent behavior      → AGENTS.md
current objective   → task / HANDOFF.md
```

When sources conflict:

```text
verified evidence
> current project docs
> current task context
> durable memory
> historical memory
```

## Sync protocol

1. Classify new information and update only its canonical owner.
2. Record date, source, verification, and confidence/status for factual claims.
3. Commit the authoritative Cerebro change and capture the commit SHA.
4. Refresh the corresponding ChatGPT Project source from that committed file.
5. Record a sync receipt and make Codex reload relevant files on its next task.

ChatGPT project memory and Codex chat history are retrieval layers, not
authoritative databases. Never assume either product silently synchronized a
change made in the other.

## Sync receipt

For every material refresh, record:

```text
date:
cerebro_commit:
files:
chatgpt_project_refreshed: yes/no
codex_context_refreshed: yes/no
verified_by:
notes:
```

If a refresh cannot be verified, mark it incomplete rather than claiming sync.
