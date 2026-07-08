---
description: Add a new seminar prompt type (question / jargon / stall-hint family)
argument-hint: <prompt-type-name> [when it should fire]
---

Add a new Zemiful prompt type: `$1`

Details / trigger condition: $ARGUMENTS

Zemiful sends short **text** prompts to participants' screens during a live seminar —
never audio, never interrupting. Prompt types (e.g. "suggest question", "explain
jargon", "stall hint") are kept as distinct, independently testable units.

Steps:

1. Read the existing prompt-type definitions and their tests to match the established
   shape (type, payload, trigger, rendering). If none exist yet, propose a minimal
   shared interface first and confirm it before implementing.
2. Define the new prompt type with an explicit TypeScript type — no `any`.
3. Wire its trigger condition and its participant-targeting (one / subset / all).
4. Ensure it renders unobtrusively and accessibly on the participant view.
5. Add a focused test for the trigger logic and the rendered output.

Do not fold this into an existing prompt type's branching logic — keep it separate.
Report the files changed and how to test just this prompt type.
