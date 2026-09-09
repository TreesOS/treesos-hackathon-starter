# AGENTS.md — Harness build rules

Read this before you start. It applies to **you and any AI agent/coding assistant you use**
(Claude Code, Cursor, etc.) while building your harness. Point your assistant at this file.

## 1. What you must build

A harness that meets **all six requirements** (this is the gate — miss one and you can't place):

1. **Model-agnostic** — the model is swappable via config; no hard-wiring to one provider.
2. **Interactive** — a human can review and change the output while it runs.
3. **Modular** — separable parts (modules/config), not one monolith.
4. **Connected to a database** — output is persisted and read back, not just printed.
5. **Scales personal → team** — a clear path from single-user to multi-user.
6. **Reports its token cost** — every run prints tokens used (and rough RM).

## 2. Document everything (this is graded)

Keep a **[DEVLOG.md](DEVLOG.md)** and update it as you go. Record:

- **Development strategy** — how you're approaching the build, what you tried, what you dropped.
- **Infrastructure choices** — which model(s), database, hosting, libraries, and **why** you chose them.
- **Key decisions and trade-offs** — anything a judge would otherwise have to guess at.
- **Token notes** — roughly what your harness costs to run, and anything you did to make it leaner.

If you use an AI assistant to build, that's expected — note how you used it in the DEVLOG.

## 3. Infrastructure choices

- **Model:** DeepSeek or ILMU (token budget provided). Because of rule 1, put the model behind a
  small config/adapter so it can be swapped — don't scatter provider-specific calls through the code.
- **Database:** Supabase recommended.
- **Deployment:** Vercel recommended.
- You may borrow from open-source harnesses (Pi Harness, Hermes, OpenClaw). Credit them in your README.

## 4. Branding

Build it under (or close to) the **TreesOS** brand:

- Name your harness clearly; if it has a UI, keep it clean and minimal, in a green/moss, calm spirit.
- Don't impersonate other companies or use their logos.
- Keep it tasteful — this may be shown publicly in the showcase.

## 5. Conventions

- **Keep your fork public** for the whole event — that's how we see and showcase your work.
- Commit meaningfully and often; the history is part of the story.
- Real input over fabricated demos — show it working on real (or anonymised real) data.
- No secrets in the repo. Use a `.env` (see `.env.example`) and keep keys out of git.

## 6. How you're judged

Your public fork is your submission. A fixed evaluation runs on every fork (same benchmark task,
same rubric, same judge) — impartial and comparable. Gate = the six requirements above; then
scored on usefulness, creativity, presentation, token efficiency, and execution & usability.
