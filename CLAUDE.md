# Zemiful

Zemiful activates live discussion in university lab seminars, where one professor
mentors 15–20 students. Unlike transcription tools that only record, it sends short
**text** prompts to each participant's screen during the seminar — never by voice, so
it never interrupts. It suggests questions, explains jargon, and offers hints when
talk stalls.

## Status

Greenfield. As of this writing the repo contains only this file, the README, and
IntelliJ/Android Studio project metadata (`.idea/`). No application source or
`package.json` exists yet. The chosen stack is **Web / TypeScript** — fill in the
concrete tooling sections below as the first code lands, and delete this Status note
once the scaffold is real.

## Product shape (what the code needs to do)

- **Real-time delivery.** Prompts must reach many participants' screens near-instantly
  and mid-seminar. Assume a persistent transport (WebSocket / SSE) rather than polling.
- **Per-participant targeting.** A prompt can go to one person, a subset, or everyone.
  The data model needs seminar → session → participant identity.
- **Text-only, non-interruptive.** No audio output. Prompts are unobtrusive UI (toast,
  side panel, or card) that a participant can read or dismiss without derailing talk.
- **Prompt sources.** Question suggestions, jargon explanations, and stall hints. Keep
  these as distinct, independently testable prompt types.
- **Facilitator (professor) view vs. participant view.** Two distinct clients likely
  share a component/type layer.

## Stack (Web / TypeScript)

Decided: Web + TypeScript. Concrete choices are open until the first code lands —
record them here as they're made so this file stays the source of truth:

- Framework: _TBD_ (e.g. React + Vite, Next.js)
- Realtime: _TBD_ (e.g. native WebSocket, Socket.IO, SSE)
- Package manager: _TBD_ (npm / pnpm / yarn)
- Test runner: _TBD_ (e.g. Vitest, Jest, Playwright for e2e)
- Lint/format: _TBD_ (e.g. ESLint + Prettier, Biome)

## Build & run

_No toolchain yet._ Once `package.json` exists, document the real commands here so a
fresh session can build, run, and test without guessing. Expected shape:

```
# install
<pkg> install
# dev server
<pkg> run dev
# test
<pkg> test
# lint / typecheck
<pkg> run lint && <pkg> run typecheck
```

## Conventions

- **TypeScript strict.** No `any` in committed code; model prompt types explicitly.
- **Accessibility matters.** Prompts render on participants' screens during live
  discussion — they must be readable, dismissible, and screen-reader friendly.
- **Separate prompt types.** Keep "suggest question", "explain jargon", and "stall
  hint" as distinct, individually testable units rather than one branching function.
- Match the surrounding code's naming, structure, and comment density when editing.

## Git workflow

Never commit directly to `main`. Every change follows: create a branch → commit on it
→ push the branch → merge into `main` (then push `main`). Use a descriptive branch name
(e.g. `feature/…`, `fix/…`, `docs/…`).

## Claude Code setup in this repo

- `.claude/commands/` — project slash commands (see `/scaffold-component`, `/prompt-type`).
- `.claude/agents/` — project subagents (see `frontend-reviewer`).
- These are starters. Extend or replace them as the codebase takes shape.
