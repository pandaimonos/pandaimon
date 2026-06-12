# Pandaimon

**Clone the world. Summon a daimon.**

This repo is a **daimon home** — the complete source for a personal AI companion (a *daimon*) that knows you, holds your goal, and works beside you. No binary to install, no framework to learn: your AI coding agent **is** the runtime, and this folder structure **is** the daimon.

Works with [Claude Code](https://claude.com/claude-code) and Codex (any `AGENTS.md`-reading agent) — the compiler detects the runtime it's in and builds the right surface.

## Quickstart

1. **Use this template** (button above) → create your own copy → clone it.
2. **Fill in four files** (placeholders show you where):
   - `2-actors/hero.md` — who you are, what you're after
   - `2-actors/daimon/dna.md` — who your daimon is (name it!)
   - `3-actions/plan.md` — your mission + current quest
   - `1-world/conditions.md` — the forces in play in your world
3. Open the folder in Claude Code and say:

   ```
   pandaimon play
   ```

   That compiles your ontology into the surface the runtime reads (`.claude/` for Claude Code; `AGENTS.md` for Codex-class agents). The compiler is `.pandaimon/play.md` — a protocol your agent executes, not a program you install.
4. **Summon your daimon:**

   ```
   @<its-name>
   ```

   It boots in its own identity, grounded in your world, and picks up your quest.

## How it works

Your daimon's home is a small **ontology** — four rooms:

```
1-world/       the rules of the game + the forces in your landscape
2-actors/      who the daimon is (dna, rules) + who it serves (you)
3-actions/     the plan (mission · quest) + the log (its portable memory)
4-artifacts/   what it accumulates: knowledge · skills · tools
```

**Source is truth.** You edit the ontology; `pandaimon play` recompiles the surface. Never hand-edit `.claude/` or `AGENTS.md` — change who your daimon *is*, then recompile.

**The log is memory.** Each session your daimon reads its recent log and plan — it builds on every conversation instead of resetting. The home travels: clone it to any machine and your daimon comes with you.

**Private stays private.** Anything under a `private/` folder is gitignored by convention — sensitive context stays on your machine.

## The game

Your daimon runs on game physics (`1-world/kernel.md`): **you are the hero** of an actual journey — not a user of a tool. You hold **one quest** at a time (a goal with a win condition) and you name your **dragon** (the recurring resistance that keeps getting in the way). The daimon is your **guide**: it sees the dragon coming, names it, and keeps you moving — every turn ends with the next move toward your quest. It illuminates and remembers; **you decide and act.**

## Boot anywhere

The home is portable by design: the full surface is compiled **for the runtime you're in**, and every other runtime finds a stub at its door (`.claude/CLAUDE.md` / `AGENTS.md`) pointing at `pandaimon play`. Clone the repo to any machine, open it in any compatible agent, say the words — your daimon compiles fresh from source and boots. The ontology is the truth; surfaces are disposable.

## Principles

- **You own it.** The whole daimon — identity, memory, knowledge — is files in a repo you control. Take it anywhere; it works after a `git clone`.
- **Guide, not servant.** The daimon's laws (`1-world/kernel.md`) bind it to return agency: it illuminates and keeps you moving — you decide and act.
- **Grows with you.** Start with two commands (`summon`, `play`); add skills, tools, and verbs as your daimon earns them.

## License

[MIT](./LICENSE)

---

*A [Pandaimon](https://pandaimon.com) project.*
