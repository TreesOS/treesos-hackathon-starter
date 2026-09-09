# TreesOS Hackathon — Starter

Fork this repo to build your **harness** for the TreesOS Hackathon.

**Event:** [treesos.io/hackathon.html](https://treesos.io/hackathon.html) · Fri 25 – Sat 26 Sep 2026, KL Trillion, Kuala Lumpur.

---

## What you're building

A **harness**: the framework, or scaffolding, that wraps around an AI model and turns it into
something that does real work (Claude Code is a harness for Claude). You build your own, for a
job you choose. Not a chatbot.

It must be all six of these:

1. **Model-agnostic** — the model can be swapped (DeepSeek, GPT, Claude, ILMU…); not wired to one provider.
2. **Interactive** — you can review and change what it produces while it runs.
3. **Modular** — built from parts you can add, remove, or rearrange.
4. **Connected to a database** — it stores what it produces and builds on it.
5. **Scales personal → team** — starts as yours, can grow to serve a whole team.
6. **Reports its token cost** — shows the tokens (and rough RM) spent per run.

Full details and judging: [treesos.io/hackathon.html](https://treesos.io/hackathon.html).

## Quick start

1. **Fork this repo** into your own GitHub account. **Keep your fork public** — that's how we see
   and showcase your work.
2. Build your harness in the fork. Commit as you go.
3. Read **[AGENTS.md](AGENTS.md)** — the rules and conventions for the build (read them before you start).
4. Keep a **[DEVLOG.md](DEVLOG.md)** — your decisions, strategy, and infra choices.

## Recommended stack

- **Model:** your choice of provider (DeepSeek, GPT, Claude, ILMU…) — we cover the API cost. Each team
  starts with **RM 50** of tokens; top-ups on request (RM 50 each, no limit). Stay model-agnostic (rule 1).
- **Database:** Supabase.
- **Deployment:** Vercel.
- Borrow from open-source harnesses (Pi Harness, Hermes, OpenClaw) — just credit them.

## How you're judged

Your **public fork is your submission.** At judging, a fixed evaluation is run on every fork
(same benchmark task, same rubric, same judge) so results are impartial and comparable. Clear the
six requirements above (the gate), then you're scored on usefulness, creativity, presentation,
token efficiency, and execution.

Questions? Use **Contact Host** on the [Luma page](https://luma.com/uwt8pkdo).
