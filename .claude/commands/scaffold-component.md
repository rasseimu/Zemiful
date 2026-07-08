---
description: Scaffold a new TypeScript UI component with a colocated test
argument-hint: <ComponentName> [short description of what it does]
---

Create a new Web/TypeScript UI component named `$1` for the Zemiful app.

Context: $ARGUMENTS

Before writing anything:

1. Look at the existing project structure and an existing component (if any) to match
   the real framework, file layout, styling approach, and test setup. Do NOT assume a
   framework — read the code first. If no components exist yet, check `CLAUDE.md` for
   the chosen stack and ask which framework to scaffold for if it's still `TBD`.
2. Follow the repo's naming and directory conventions exactly.

Then:

- Create the component in TypeScript with explicit prop types (no `any`).
- Make it accessible: proper roles/labels, keyboard-operable, dismissible if it's a
  prompt/overlay. Zemiful prompts render on participants' screens during a live seminar.
- Colocate a test that covers the primary render and the main interaction.
- Keep it small and focused; one component, one responsibility.

Report the files you created and the command to run the new test.