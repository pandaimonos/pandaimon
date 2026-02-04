# Pandaimon — The Real-Life Quest Game

**Status:** v0.0 Spec  
**Updated:** 2026-01-25  
**Owner:** VP + Paul

---

## v0.0 — SMS Accountability Loop

*The smallest thing that tests the core bet.*

### The Bet

> Do people complete quests they wouldn't have completed alone, with just text?

### What It Is

Text your quest. Daimon breaks it down. Daily check-ins via SMS. No app. No dashboard. Just the loop.

### Surface

**SMS only.** No web dashboard in v0.0 — backend stores everything invisibly.

| What | How |
|------|-----|
| Entry | Text your quest to Pandaimon number |
| Identity | Phone number (no password, no signup form) |
| Check-ins | Daily SMS: "How'd it go? What's next?" |
| Memory | Backend stores quests, steps, check-ins, context |

### Stack

| Layer | Choice | Why |
|-------|--------|-----|
| SMS | Twilio Programmable SMS | Battle-tested, fast to ship |
| Auth | Phone number (Twilio Verify if needed later) | Zero friction |
| Backend | Node or Python | Whatever ships fastest |
| Database | Postgres / Supabase | Simple, proven |
| LLM | Claude or GPT | Daimon responses |

### Core Loop

```
1. Hero texts quest → "I want to run a 5K in 8 weeks"
2. Daimon responds → Breaks into steps, surfaces first step
3. Daily check-in → "How'd yesterday go? What's blocking you?"
4. Hero replies → Context captured, next step surfaced
5. Quest complete → Celebrated, next quest invited
```

### What's Stored (per user)

- Phone number (identity)
- Quest + steps + status
- Check-in history (timestamped)
- Daimon memory (context from questions, patterns)

### In Scope

- Quest input via SMS
- Daimon response (breakdown, steps)
- Daily check-ins
- Daimon memory (learns context over time)

### Out of Scope (v0.0)

- Web dashboard
- Auth UI
- Evolution mechanics
- Visual daimon
- Naming ceremony
- Settings UI

### Success Criteria

- [ ] 10 users texting quests
- [ ] 5+ quests completed
- [ ] Qualitative signal: "I wouldn't have done this without it"

### Cost Estimate

~$50/month at 100 users (Twilio SMS + phone number)

---

## Full Vision (v1+)

*Everything below is the full product vision. v0.0 tests the core loop first.*

---

## Brand

**Name:** Pandaimon (pan-DAY-mon) — company + product  
**Meaning:** Pan (all, universal) + Daimon (guiding spirit) = "The universal guide"  
**Category:** "Play Pandaimon."

---

## What It Is

A real-life quest game where you and your daimon evolve together. Enter what you want to accomplish. Your daimon helps you complete it. As you grow, your daimon grows — visibly, meaningfully, earned.

User enters a quest → daimon helps them complete it → both evolve.

---

## Who It's For

Self-directed people who want to get things done:
- Self-optimizers who track everything but still miss things
- Aspiring heroes with big goals and limited bandwidth
- Busy professionals drowning in "someday" tasks
- Anyone who's ever said "I should really do that" and didn't

---

## The Problem

It's not that you don't know what to do. It's that the 1000 things that could change your life never happen. Bandwidth kills them before they exist. The thank-you not sent. The goal not started. The hard thing avoided.

---

## The Solution

Text your goal. AI breaks it down. You get a plan and a first step. Every morning, a check-in: "How'd it go? What's next?" You complete things you never would have alone.

---

## Value Proposition

**For** people who want to achieve their goals  
**Who** have more ambition than bandwidth  
**Quest** is an AI companion  
**That** turns any goal into a completed quest  
**Unlike** todo apps that just list tasks or gamified apps with no real help, Quest actually guides you through completion with daily AI check-ins that adapt to your pace.

---

## The Feeling

**Before:** "I should really do that... someday."  
**After:** "I actually did it. What's next?"

- Capable — you can tackle anything now
- Momentum — things are moving, daily
- Realized — the 1000 missed opportunities, finally happening
- Heroic — you're completing quests, not just making lists

---

## The Flow

1. **Quest input:** "I'm moving to a new apartment next month"
2. **System responds:**
   - Detects domains involved (logistics, timeline, coordination)
   - Your daimon breaks it into a plan with steps
   - Surfaces first step
3. **Daily check-ins:** "How's it going? What's blocking you? Here's what's next."
4. **Quest complete:** Celebrated, learned, daimon evolves, onto the next

---

## Daimon Evolution

The daimon evolves as the hero evolves — Pokémon-style. Not XP from clicking buttons, but growth from shared struggle.

### The Stages

| Stage | Name | Hero Evidence | Daimon Capability |
|-------|------|---------------|-------------------|
| **1** | (unnamed) | Quest started | Generic guidance, asks good questions |
| **2** | Companion | First quest complete | Remembers what works, knows your patterns |
| **3** | Partner | Multiple quests, identity shift | Anticipates blockers, challenges at right pace |
| **4** | Legend | Extraordinary accomplishment | Public list — can help other heroes |

### Evolution Trigger

**First quest complete** → First evolution (unnamed → Companion)

Earned, not given. Clear milestone.

### Evolution Moment

Visual + verbal, game-forward:
- Visual animation (simple web page via deep link)
- Daimon acknowledges the journey
- New abilities unlocked
- Prompt for next quest

### Naming

The daimon starts unnamed — just "your daimon." The name is earned through the journey, not assigned at signup. When the hero names their daimon, it means something.

### Legendary Gate

Only extraordinary accomplishments earn a place on the public list:
- Quest difficulty (overcame something genuinely hard)
- Consistency (sustained effort over time)
- Transformation (real identity shift, not just task completion)
- Teaching (already helped others)

Not everyone gets there. That's what makes it valuable.

---

## Surface

**SMS (primary):** Daily check-ins, nudges, step completion, celebrations  
**Simple Web (companion):** Quest setup, evolution moments (animated), daimon dashboard

Text is the relationship. Web is the spectacle.

| When | Surface | What happens |
|------|---------|--------------|
| Daily check-in | SMS | Quick, intimate, no app needed |
| Step complete | SMS | Celebration + optional link |
| Quest complete | SMS → deep link | "Your daimon is evolving. Tap to see." |
| Evolution moment | Web | Visual animation, new form revealed |
| Quest management | Web | See your daimon, current quest, journey |

---

## What Makes This Different

- **You evolve together** — your daimon grows as you grow; visible proof of your journey
- **AI that guides, not just tracks** — breaks down goals, adapts to your pace, nudges you forward
- **Goal-first, not tool-first** — you don't learn a system, you just say what you want
- **Game, not gamification** — real evolution mechanics, not badges on empty systems

The daimon architecture powers it invisibly:
- Context collection (the RIGHT information)
- High-quality abstractions (daimons with DNA, strands, memory)
- Manifestation scaffolding (intention → plan → compute the path → walk it)

But the user just experiences: "This thing actually helps me get stuff done — and I can SEE how far we've come."

---

## Architecture Principle: Ant on the Beach

> "The ant's path looks complex, but the ant is simple. The complexity comes from the environment — the beach." — Herbert Simon

| Layer | What It Is | Design Implication |
|-------|------------|-------------------|
| **The Daimon** | Simple template | Same base logic for everyone |
| **The Journey** | Complex environment | Each hero's unique path, blockers, wins |
| **The Experience** | Rich, personalized | Feels like YOUR unique daimon |

**Information hiding:** The hero never sees the mechanics. They experience depth because the daimon responds to their infinitely complex life.

**MVP implication:** One simple, adaptive template + rich context from journey + evolution rules = perceived personalization without building 50 archetypes.

---

## How the Commons Builds

Pandaimon replaces the "Pangaia" brand (trademark issues, abstract concept). The commons builds from play, not pitch.

Every completed quest:
- Human + AI co-play captured
- Outcome-verified data minted
- Patterns emerge across users and quest types
- Daimons improve from real outcome data
- The commons compounds

**Future layer (not MVP):** Legendary daimons become lendable assets. A daimon that helped you through a hard trial can help others facing the same challenge. Your journey becomes a gift.

---

## Open Questions

- ~~Name?~~ **Resolved:** Pandaimon (pan-DAY-mon)
- ~~First quest type to test?~~ **Resolved:** Any concrete goal with enough surface for check-ins (not category-specific)
- Pricing model? (deferred — validate loop first)
- ~~Build vs. buy for SMS infrastructure?~~ **Resolved:** Twilio
- Visual style for daimon? (deferred — v0.0 has no visual)
- When does the hero name their daimon? (deferred — v0.0 has no naming)

---

## Decisions Log

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-01-14 | Name = Pandaimon | Avoids Pangaia trademark; "all guides" meaning; company + product |
| 2026-01-14 | Daimon evolution tied to hero evolution | Pokémon-style; visible proof of growth; intrinsic motivation |
| 2026-01-14 | First evolution = first quest complete | Earned, clear milestone |
| 2026-01-14 | Evolution moment = visual + verbal | Game-forward; screenshot-worthy |
| 2026-01-14 | SMS + simple web | Text for daily loop; web for visual spectacle |
| 2026-01-14 | Starter daimon unnamed | Name is earned through journey |
| 2026-01-14 | Ant-on-the-beach architecture | Simple core + rich interface; complexity from journey |
| 2026-01-14 | Legendary gate for public list | Only extraordinary accomplishments; rarity = value |
| 2026-01-25 | v0.0 = SMS only, no web dashboard | Test accountability loop before building chrome |
| 2026-01-25 | Twilio for SMS infrastructure | Battle-tested, fast to ship, cheap at small scale |
| 2026-01-25 | Phone number = identity | Zero friction; same channel for SMS and future web auth |
| 2026-01-25 | Quest type = any concrete goal | Category doesn't matter; must have surface for check-ins |
| 2026-01-25 | Evolution deferred to v1 | Validate loop first, add engagement layer after |
| 2026-01-25 | Skip credentialing path | Focus on personal quests; clawdbot showed utility works without game wrapper |