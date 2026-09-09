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

- **Model: your choice.** Pick any provider you like (DeepSeek, GPT, Claude, ILMU, whatever fits).
  We cover the API cost. Rule 1 says your harness must be *model-agnostic*, meaning the model can be
  swapped without a rewrite. The simple way: route **every** model call through **one small file** (an
  "adapter") that reads the provider and API key from config. Then switching providers is a one-line
  config change, not a hundred edits. Do **not** sprinkle provider-specific API calls throughout your
  code. At judging we run your harness on two different models to check the swap actually works, so
  this is a requirement, not a nicety.
- **Tokens & cost:** each team starts with **RM 50** of API tokens (on us). Need more? Ask an
  organiser: top-ups are **RM 50 at a time, no limit** (we'll just ask what you're spending it on).
  Requirement 6 means your harness reports its own token cost, so keep an eye on it.
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

Your public fork is your submission. After the build, a fixed evaluation is run on every fork:
Claude runs your harness **on the job you built it for**, then scores it — same rubric, same judge
for everyone, so it's impartial. Gate = the six requirements above; then scored on usefulness (30),
creativity (25), presentation (15), token efficiency (25), and execution & usability (5).

## 7. Make your harness runnable (so we can judge it)

We can only score what we can run. Before the deadline, make sure your fork has:

- A **"Run it" section** in your README with the exact commands to run the harness on a sample input.
- A **sample input** in the repo that represents your job (real or anonymised real data — not fabricated to look good).
- The **model behind a config/adapter** (rule 1), so we can swap the provider and re-run without editing your code.

If we can't run it, we can only score what we can read, and you can't pass the gate.
