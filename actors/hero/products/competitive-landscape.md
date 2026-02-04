# Competitive Landscape — Quest MVP

**Updated:** 2026-01-12

---

## Gamified Todo / Quest Apps

| App | Angle | Strengths | Gaps |
|-----|-------|-----------|------|
| **Habitica** | RPG-style habits | Fun, sticky, dopamine loops. Avatars, XP, parties, boss battles. 4M+ users. | No AI. You define tasks, you track yourself. Game doesn't help you complete anything. |
| **QuestDo** | Tasks as quests | Character building, spells. Game-forward. | No AI assistance. |
| **GoalQuest** | Daily goal coaching | "One daily quest at a time." Personalized program. | Onboarding way too long. No AI — coaching is canned/static. |

## AI-Powered Goal/Coaching Apps

| App | Angle | Strengths | Gaps |
|-----|-------|-----------|------|
| **Serenity** | AI chat planner | Auto-generates routines. Conversational. Adaptive timelines. Nudges. | Unclear how deep the AI goes. Worth testing. |
| **Rocky.ai** | Leadership/growth | Daily reflections, goal tracking, micro-learning. Mindset focus. | Niche (leadership). Not goal-completion focused. |
| **Coachello** | Leadership development | AI + human coaching hybrid. | Enterprise-focused. Not consumer. |

---

## Testing Insights (2026-01-12)

### GoalQuest
- Onboarding was way too long — front-loaded setup instead of action
- No AI — "coaching" is static, canned content
- **Takeaway:** Don't gate action behind forms. Onboarding IS the first quest.

### Habitica
- Fun experience — RPG mechanics are engaging and sticky
- Game-forward: avatars, XP, boss battles, parties work
- No AI assistance — you set tasks, you check them off, game doesn't help you complete them
- **Takeaway:** Engagement mechanics proven. Missing the intelligence layer.

---

## The Gap

| Category | What they do | What's missing |
|----------|--------------|----------------|
| Gamified apps | Fun mechanics, dopamine | AI is dumb or absent |
| AI coaching apps | Smart guidance | Feels like work, no engagement |

**The wedge:** Goal-first, AI-powered, with daimon architecture making the AI actually good (context, memory, scaffolding). Gamification at the edges, not the core.

---

## Design Principles (captured so far)

1. **Onboarding is the first quest, not a form.** User enters → "What do you want to accomplish?" → that's the start. Profile builds from quests, not before them.

2. **Guidance first, gamification at edges.** Nail the core loop (enter goal → AI breaks it down → daily check-ins → complete). Add engagement polish later.

3. **The core loop is the product. Everything else is retention.**

---

## Sequence

| Phase | Focus |
|-------|-------|
| **V1** | Nail the core loop: goal → breakdown → check-ins → complete |
| **V2** | Add engagement edges: streaks, XP, levels, celebrations |
| **V3** | Full game layer (if warranted): avatar, quests, boss battles, parties |

---

## Infrastructure / Potential Partners

| Tool | What it does | Relationship |
|------|--------------|--------------|
| **clawdbot** | Open-source personal agent framework. Handles credentials, tool invocation, skill accumulation. Users build capabilities through conversation. | Potential execution layer. Pandaimon = meaning layer (quests, guidance). Clawdbot = capability layer (skills, integrations). |

**The pattern:** Clawdbot handles "order things from Amazon." Pandaimon handles "why are you ordering, and does it serve your quest?"

Source: https://github.com/clawdbot (open source)

---

## Open Questions

- Test Serenity — closest AI competitor?
- What's the first quest type to validate?
- SMS vs app for V1?
