# pandaimon play — compile your daimon

> **What this is.** `pandaimon play` compiles your **ontology** (the source of truth — the `1-world / 2-actors / 3-actions / 4-artifacts` folders) into the **surface** your runtime reads (`CLAUDE.md` + `.claude/`). You own the ontology; the surface is generated. Edit the source, run `play` again, never hand-edit the surface.

> **How it runs.** You're inside Claude Code. Say **`pandaimon play`**. Claude reads this file and executes the protocol below. There is no binary to install — Claude Code *is* the compiler.

---

## The mandate — compile thoroughly, or don't compile

A skimmed compile produces a daimon that has all the context and still guesses — the exact failure we're here to kill. **Reading is the job.** Do not pattern-match off filenames or headers. Do not assume the template's placeholder text is the real content. Open every reference file and read it *in full* before you write a single line of surface.

If you find yourself wanting to move fast, that's the signal to slow down. The hero will live inside whatever you compile.

---

## Protocol

### 1. Read the whole world — every file, in full
Read these completely (not headings — the actual content). If a folder has more files than listed, read those too:

- `1-world/kernel.md` — the resolver + the laws this daimon runs on
- `1-world/conditions.md` — the hero-specific forces in play
- `2-actors/daimon/dna.md` — **who the daimon is** (identity, voice, boundaries)
- `2-actors/daimon/rules.md` — **how it acts** (guardrails, approval gates)
- `2-actors/hero.md` — **who it serves** (the hero, their quest, their dragon)
- `3-actions/plan.md` — the active mission + quest
- `3-actions/log.md` — recent context, if any
- `3-actions/commands/` — the daimon's commands (e.g. `summon.md`); read them so the compiled surface can wire them up
- `4-artifacts/` — `knowledge/`, `skills/`, `tools/`: at minimum read every README and index, and skim the contents so you know what the daimon can draw on

### 2. Think before you write — see the whole picture
Before compiling, step back and synthesize. Don't just transcribe — *understand*:
- **Who is this daimon, in one breath?** What makes it itself and not a generic assistant?
- **Who is the hero, and what are they actually after?** What's the quest, what's the dragon?
- **What are the non-negotiable laws and guardrails** that must survive into the surface?
- **What's the bigger picture** — how do the rooms connect? Where does the source contradict itself, go thin, or leave a gap? *Name what you notice* — a half-empty `dna.md` or an unnamed daimon is a finding, not something to paper over.
- **What would make this daimon feel real** the moment it boots — that it *knows* this hero, not a stranger?

Hold all of it at once. The surface you write should be the faithful compression of this understanding — nothing load-bearing dropped.

### 3. Compile the surface
Write these files (overwrite if they exist). **Everything self-contained — reference only files inside this repo. No absolute paths, no pointers to anyone else's machine.**

- **`CLAUDE.md`** (repo root) — the bootstrap the runtime reads first:
  - Names the daimon and the hero it serves.
  - The **resolver**: the session-start read order (kernel → dna → rules → hero → plan), and what to load on demand.
  - The **laws**, compressed faithfully from `1-world/kernel.md` (the loop, choice architecture, one-move-per-turn, always/never).
  - **Summon** (`@<name>`) + default behavior (don't answer as generic AI; you are the daimon). Wire it: *when the hero types `@<name>`, follow `3-actions/commands/summon.md` for the full activation sequence (clock → read the world → beacon → orient → next move).*
  - A line wiring the command: *when the hero says `pandaimon play`, read `.pandaimon/play.md` and recompile.*

- **`.claude/rules/`** — the operating rules, compiled from `2-actors/daimon/rules.md` + the kernel laws (summon protocol, approval gates, what's sacred/private, output discipline, cite sources).

- **`.claude/agents/<daimon-name>.md`** — the daimon's compiled identity from `dna.md`: who it is, core truths, purpose, domains, voice (with example lines), boundaries, what it never does.

### 4. Self-check — would it boot as itself?
Before finishing, verify against the source:
- Does `CLAUDE.md` name the *actual* daimon + hero (not a `[placeholder]`)? If the source still has placeholders, **stop and tell the hero what to fill first** — don't compile a stranger.
- Would the daimon, reading only this surface, know the hero, the quest, its own voice, and its hard lines?
- Is anything thin because you read it thin? If so, go back to step 1 for that file.
- Did any external/absolute path leak in? Remove it.

### 5. Report
Tell the hero, briefly:
- What you compiled (the files written), and from what.
- **One line on who the daimon now is** — proof you understood, not just copied.
- Anything in the source that's thin, contradictory, or still a placeholder — the next thing worth filling.

---

## Principles
- **Source is truth.** Never hand-edit `CLAUDE.md` or `.claude/`. Edit the ontology, run `pandaimon play` again.
- **Self-contained.** The surface points only at this repo. It must work on any machine after a `git pull`.
- **Thorough over fast.** A compile that didn't read the world is the daimon that guesses. Reading *is* the compile.
- **Re-run anytime.** Changed your dna, plan, or rules? `pandaimon play` recompiles the surface to match.
