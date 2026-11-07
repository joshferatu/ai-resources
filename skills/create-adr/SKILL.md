---
name: create-adr
description: Creates an Architecture Decision Record (ADR) capturing a single significant architectural choice with its context, decision, alternatives and consequences. Use when the user asks to write/record an ADR (e.g. "/create-adr use PostgreSQL for primary DB") or when a significant architectural decision has just been made and should be documented.
argument-hint: <decision summary>
---

Create an ADR for: $ARGUMENTS

An ADR is a short, structured record of ONE significant architectural decision. Keep it to about one page. ADRs are append-only: once `Accepted`, never rewrite or delete one. If direction changes, write a new ADR that supersedes the old one.

## 1. Locate the ADR directory
- Look for an existing one: `docs/adr`, `doc/adr`, `docs/decisions`, `adr`. Use it if found.
- Otherwise use `docs/adr/` and create it.

## 2. Determine the number
- List existing files matching `NNNN-*.md` in the directory; the next number is the highest + 1, zero-padded to 4 digits (`0001`, `0002`, ...). Start at `0001` if none exist.
- If existing files use a different padding, follow the existing convention and tell the user.

## 3. Gather context
- Use the argument and the current conversation first. Skim relevant repo code/docs and existing ADRs (to link or supersede) as needed.
- If the decision, the driving forces, or the alternatives considered are unclear, ask the user concise questions (AskUserQuestion if available). Do not invent rationale or alternatives; ask instead.
- One ADR = one decision. If the request bundles several, propose splitting them.

## 4. Write the file
Path: `<adr-dir>/NNNN-<short-title>.md`, where `<short-title>` is a lowercase kebab-case slug of a few words (e.g. `0001-use-postgresql-for-primary-db.md`).

Use this template:

```markdown
# NNNN. <Title>

- Status: Proposed
- Date: YYYY-MM-DD

## Context
The forces, constraints and problem statement that led to this decision.

## Decision
What was chosen and why. State it in active voice ("We will ...").

## Alternatives Considered
- **<Option>**: why it was ruled out.

## Consequences
Resulting trade-offs, benefits, and technical debt accepted (positive and negative).
```

Rules:
- Status is one of `Proposed`, `Accepted`, `Deprecated`, `Superseded by ADR-NNNN`. New ADRs are `Proposed`; set `Accepted` only if the user says so.
- Date is today's date (ISO format).
- Be terse: short paragraphs or bullets, no filler.

## 5. Superseding an earlier ADR
If the new ADR replaces an existing one:
- Mention it in the new ADR's Context (e.g. "Supersedes ADR-0003").
- Edit ONLY the old ADR's Status line to `Superseded by ADR-NNNN`. Change nothing else in it.

## 6. Finish
- Only write files. Do not create branches or commits; the user manages ADRs through PRs.
- Report the file path, the status, and any assumptions made or open questions.
