# ZASS — CrossAI Companion

**Project:** CrossAI Companion  
**Repository:** `dzuddiyn/CrossAI-Companion`  
**Method:** ZASSIMPLE v0.3.0  
**Status:** DESIGN ACTIVE — bootstrap from LOCKED CrossAI direction  
**Date initialized:** 2026-10-07  
**Owner:** Project Owner  
**Authority:** Project decision/readiness authority for CrossAI Companion. Upstream CrossAI Core / CrossAI Compatible contracts remain governed by `dzuddiyn/AISYNC`.

> **ZASSIMPLE: lightweight di permukaan, tetapi lineage tetap kuat sampai execution.**
>
> **DUMP → DISTILL → DECIDE → DESIGN → DO IT → DELIVERED !!**

---

# 1. SOURCE-OF-TRUTH BOUNDARY

This repository owns the Companion implementation and its project-specific decisions.

It does **not** silently redefine CrossAI Core.

Authority order:

1. Explicit Project Owner decisions recorded here as `D-xxx | LOCKED`.
2. Applicable upstream CrossAI Core / CrossAI Compatible locks in `dzuddiyn/AISYNC`, especially PF-093 and its account-binding refinement.
3. Confirmed Companion `DESIGN.md` when created.
4. Companion `ACTION_PLAN.md` when created.
5. Companion `TASKS.md` when created.
6. Code, tests, deployment evidence, and live verification.

If this project discovers evidence that conflicts with an upstream LOCKED Core contract, do not silently override it. Open an explicit decision/reconciliation gate.

---

# 2. DUMP — PROJECT DEFINITION

## Core principle

> **CrossAI is the home of the idea. The Companion is only one place where the idea can be born.**

CrossAI Companion is an **optional conversational AI add-on** for CrossAI.

It is not CrossAI Core.

Companion may provide:

- conversational AI;
- casual brainstorming;
- general questions;
- light detection of possible ideas while chatting;
- user-confirmed SAVE into CrossAI;
- channel surfaces such as Web Chat, Telegram, and WhatsApp where supported.

CrossAI Core remains responsible for:

- Ideas;
- Decisions;
- Projects;
- lineage;
- canonical SAVE truth;
- handoff / return;
- project tracking;
- CrossAI Intelligence.

---

# 3. DISTILL — WHAT MATTERS

The Companion project must prove a clean separation between:

```text
conversation
        ≠
canonical CrossAI state
```

and:

```text
AI thinks this may be an idea
        ≠
CrossAI has saved an Idea
```

The Companion should remain natural and lightweight while CrossAI Core retains semantic authority.

The minimum useful proof is:

```text
user
→ Companion conversation
→ possible idea
→ explicit user SAVE
→ CrossAI Compatible
→ CrossAI Core
→ factual SAVE receipt
→ visible saved Idea in CrossAI Web
```

---

# 4. GOALS

- Provide an optional conversational AI surface for ordinary CrossAI users.
- Allow natural conversation without turning CrossAI Core into a chatbot.
- Detect or surface possible idea signals without silent semantic promotion.
- Let the user explicitly SAVE meaningful state into CrossAI.
- Preserve strict user isolation across shared channel services.
- Keep Companion runtime/provider/channel failures isolated from CrossAI Core continuity.
- Prove the CrossAI Compatible boundary with the smallest practical vertical slice first.

---

# 5. NON-GOALS — INITIAL MVP

The first MVP does **not** need to prove all of the following simultaneously:

- WhatsApp + Telegram + Web at once;
- multiple conversational AI providers;
- voice;
- image/PDF multimodal conversation;
- group chat;
- cross-channel thread continuation;
- billing;
- FREE/BYO AI/POWER commercial tiers;
- automatic project creation;
- full DECIDE workflow;
- full handoff/return workflow;
- automatic duplicate merging;
- silent idea/project promotion.

These may be added later through explicit design and execution decisions.

---

# 6. LOCKED DECISIONS

## D-001 | LOCKED — Companion is optional, not Core

**Decision:** CrossAI Companion is an optional conversational add-on. CrossAI users may use CrossAI without Companion.  
**Reason:** General conversational AI must not redefine or overload CrossAI Core continuity authority.

## D-002 | LOCKED — Core principle

**Decision:** “CrossAI is the home of the idea. The Companion is only one place where the idea can be born.”  
**Reason:** Idea ownership/continuity belongs to CrossAI Core, not the conversational surface.

## D-003 | LOCKED — Separate runtime/deployment

**Decision:** Companion uses a separate application/runtime/deployment from CrossAI Core. A separate Apps Script deployment is acceptable for early beta.  
**Reason:** Companion traffic, AI quota, provider outage, or webhook failure must not take down Core continuity.

## D-004 | LOCKED — Shared service, many users

**Decision:** Do not create one physical bot/runtime per user. One Telegram bot, one WhatsApp endpoint/account, and one Web Chat service may each serve many users.  
**Reason:** Personal separation comes from identity mapping and scoped state, not duplicated executables.

Required logical isolation:

```text
channel_user_id
      ↓
crossai_user_id
      ↓
private conversation/session scope
      ↓
authorized CrossAI Ideas / Decisions / Projects
```

## D-005 | LOCKED — Strict user isolation

**Decision:** No user may inherit another user's conversation, identity binding, CrossAI context, or authorized project/idea scope.

## D-006 | LOCKED — CrossAI Web is binding authority

**Decision:** CrossAI Web is the account-binding authority for Companion channels. Channel identities become CrossAI-linked only after an explicit user-driven binding step.

Telegram baseline outcome:

```text
telegram_user_id ↔ crossai_user_id
```

WhatsApp must eventually produce the equivalent verified mapping:

```text
whatsapp_user_id ↔ crossai_user_id
```

Binding credentials are short-lived authorization artifacts, not permanent passwords.

## D-007 | LOCKED — CrossAI Compatible is the stable boundary

**Decision:** Companion reaches Core through CrossAI Compatible. Temaya, Kerani AI, and future assistants may also connect through the same boundary without using Companion.

Candidate capability family includes:

- identify/bind authorized user;
- submit idea candidate;
- SAVE confirmed idea;
- submit decision candidate;
- link to project;
- read explicitly scoped context;
- prepare handoff;
- return result;
- read factual SAVE receipt.

Exact endpoint names, schemas, and auth are not yet locked.

## D-008 | LOCKED — Two distinct AI roles

**Decision:** Keep Companion AI and CrossAI Intelligence separate.

**Companion AI:**
- conversation;
- brainstorming;
- general answers;
- conversational multimodal capability where supported;
- light idea-signal surfacing.

**CrossAI Intelligence:**
- semantic screening;
- idea/decision/project candidate detection;
- classification/summarization;
- relation/deduplication;
- retrieval assistance;
- semantic promotion suggestions.

CrossAI Intelligence is not the general chatbot.

## D-009 | LOCKED — Governance

**Decision:**

> **AI interprets. ASC governs. User decides.**

Default promotion path:

```text
AI suggests
   ↓
ASC validates
   ↓
user confirms
   ↓
SAVE
   ↓
factual receipt
```

No silent promotion into canonical Ideas, Decisions, or Projects.

## D-010 | LOCKED — No full ZASS on every message

**Decision:** Normal Companion conversation remains natural. ZASS/CrossAI semantic techniques may run lightly in the background, but full project work happens elsewhere when appropriate.

## D-011 | LOCKED — Companion must not duplicate CrossAI

**Decision:** Companion must not own its own canonical:

- Ideas database;
- Decisions database;
- Project authority;
- SAVE truth;
- semantic master;
- project lineage.

Temporary chat/session state is allowed.

## D-012 | LOCKED — Cost domains stay separate

**Decision:** Keep distinct:

```text
Companion conversational inference
≠ CrossAI Intelligence inference
≠ CrossAI Core runtime
≠ channel/messaging cost
≠ durable storage cost
```

## D-013 | LOCKED — Smallest-boundary MVP

**Decision:** The first MVP proves one end-to-end boundary, not every channel/provider.

Target proof:

```text
conversation
→ possible idea
→ user confirms SAVE
→ CrossAI Compatible
→ CrossAI Core
→ factual receipt
→ visible Idea in CrossAI Web
```

## D-014 | LOCKED — Non-blocking to CrossAI Core critical path

**Decision:** Companion development must remain non-blocking to existing CrossAI production-critical work unless explicitly promoted.

## D-015 | LOCKED — Temaya / Kerani AI are peers, not Companion features

**Decision:** Temaya and Kerani AI sit at the same external integration level as Companion.

```text
CrossAI Companion ─┐
Temaya ─────────────┼→ CrossAI Compatible → CrossAI Core
Kerani AI ──────────┘
```

Companion is not a public version of Temaya, and Temaya is not a Companion feature.

---

# 7. OPEN QUESTIONS

## Q-001 | OPEN — First MVP channel

Which channel should prove the first Companion vertical slice?

- Web Chat
- Telegram
- WhatsApp

Current recommendation from design review: **Web Chat first**, but this is **not LOCKED**.

## Q-002 | OPEN — Exact CrossAI Compatible v1 contract for Companion

Need to define the minimum request/response contract required for:

- authorized identity;
- idea candidate/confirmed SAVE;
- scoped context if needed;
- factual SAVE receipt.

## Q-003 | OPEN — Companion ↔ CrossAI Web/Core auth/session contract

Need the smallest deterministic authorization model that allows Web Companion use without duplicating Core identity authority.

## Q-004 | OPEN — Transient conversation/session retention

Need rules for:

- session lifetime;
- deletion;
- privacy;
- what remains temporary;
- what may be intentionally promoted into CrossAI.

## Q-005 | OPEN — Companion AI provider/model

Provider/commercial selection is intentionally deferred.

## Q-006 | OPEN — Exact idea-detection orchestration

Need to decide how much candidate detection occurs in Companion AI versus a Core-side CrossAI Intelligence call while preserving the locked governance boundary.

## Q-007 | OPEN — Binding mechanics

For external channels, define:

- expiry;
- single-use semantics;
- replay protection;
- revoke;
- rebind;
- recovery.

---

# 8. RISKS

## R-001 | OPEN — Channel complexity hides the real MVP boundary

If Telegram/WhatsApp transport is introduced too early, webhook/binding/provider work may obscure whether Companion → CrossAI Compatible → Core actually works.

## R-002 | OPEN — Accidental second semantic store

Temporary chat/session storage could drift into an unauthorized second Ideas/Projects database.

## R-003 | OPEN — False SAVE confirmation

Companion must never say “Saved to CrossAI” based only on AI intent or transport success. Only a factual Core receipt may authorize that claim.

## R-004 | OPEN — Identity mix-up

Shared bots/services create serious cross-user risk if channel identity resolution or binding is incorrect.

## R-005 | OPEN — Runtime coupling

If Companion shares too much runtime/quota with Core, Companion failure may affect continuity despite the locked separation.

## R-006 | OPEN — Provider/commercial premature coupling

Selecting a provider, quota model, or payment tier too early may hard-code product policy into architecture.

---

# 9. CURRENT SELECTION MATRIX

## Decision topic: first MVP channel

| Option / Candidate | Must-have fit | Strength | Risk / Weakness | Evidence / Unknown | Status |
|---|---|---|---|---|---|
| Web Chat | PASS | Reuses CrossAI Web identity context; isolates the core conversation→SAVE boundary from external webhook/binding complexity | Does not prove external-channel account binding yet | Exact Web Companion auth/session contract still OPEN | **RECOMMENDED — OPEN** |
| Telegram | PASS | Proves real external channel and binding early | Adds bot webhook, binding-code, replay/revoke, and delivery concerns to the first slice | Telegram binding architecture is directionally locked but implementation details remain OPEN | OPEN |
| WhatsApp | PASS | Strong low-friction end-user channel target | Highest early provider/account/platform complexity | Exact WhatsApp API/account mechanism remains OPEN | OPEN / DEFERRED FOR FIRST SLICE |

**Current direction:** Web Chat is the smallest practical first slice, but no owner lock has been recorded yet.

---

# 10. DESIGN — DRAFT 0.1

**Status:** PENDING CONFIRMATION  
**Design Progress:** 4/4 coverage — purpose / main flow / main elements / relevant LOCKED decisions  
**Confirmation blocker:** Q-001 first MVP channel is still OPEN.

## Purpose

Provide optional conversational AI while keeping CrossAI Core as the only canonical semantic continuity authority.

## Main flow

```text
User
  ↓
Companion channel/UI
  ↓
private transient session
  ↓
Companion AI
  ↓
possible idea signal
  ↓
user chooses SAVE IDEA
  ↓
CrossAI Compatible
  ↓
Core identity/auth + ASC governance
  ↓
canonical SAVE
  ↓
factual receipt
  ↓
Companion displays receipt
  ↓
same saved Idea visible in CrossAI Web
```

## Proposed component boundary

```text
┌───────────────────────────────────────────┐
│ CROSSAI WEB / CHANNEL                     │
│ identity entry / conversation surface     │
└──────────────────┬────────────────────────┘
                   ↓
┌───────────────────────────────────────────┐
│ CROSSAI COMPANION RUNTIME                 │
│                                           │
│ channel adapter                           │
│ transient session state                   │
│ conversational AI adapter                 │
│ possible-idea presentation                │
│ CrossAI Compatible client                 │
│ receipt presentation                      │
│                                           │
│ DOES NOT OWN canonical Ideas/Projects     │
└──────────────────┬────────────────────────┘
                   ↓
           CrossAI Compatible
                   ↓
┌───────────────────────────────────────────┐
│ CROSSAI CORE                              │
│ identity / authorization                  │
│ ASC governance                            │
│ canonical SAVE / lineage                  │
│ factual receipt                           │
│ optional CrossAI Intelligence             │
└───────────────────────────────────────────┘
```

## Main elements

1. Channel/UI adapter.
2. Channel/user → CrossAI identity resolver.
3. Private transient conversation/session scope.
4. Companion conversational AI adapter.
5. Possible-idea action surface.
6. CrossAI Compatible client.
7. Core-side authorization/governance.
8. Canonical SAVE + factual receipt.
9. CrossAI Web read/inspection of the same saved state.

## Architecture invariants

```text
Companion changes
≠ Core continuity changes

channel changes
≠ semantic authority changes

AI provider changes
≠ idea ownership changes

bot scaling changes
≠ user identity changes

conversation state
≠ canonical CrossAI state
```

---

# 11. IMPLEMENTATION THOUGHTS — NOT YET EXECUTION AUTHORITY

These are planning inputs only. They do not override LOCKED decisions.

- Start with one reversible vertical slice.
- Prefer text-only first.
- Use one Companion AI provider first.
- Avoid multi-channel abstractions beyond what the first slice requires, while keeping the boundary replaceable.
- Build/consume CrossAI Compatible rather than direct-writing Core storage.
- Require deterministic authorization below/outside LLM reasoning.
- Treat SAVE success as receipt-driven, not model-driven.
- Add external channel binding only after the basic Companion→Core boundary is proven.
- Verify every canonical write by reading the resulting Core state/receipt.

When implementation planning begins, promote these into `ACTION_PLAN.md` with lineage back to the applicable D-xxx decisions.

---

# 12. CURRENT STAGE

```text
DUMP      ✓
DISTILL   ✓
DECIDE    ✓ baseline architecture locks imported
DESIGN    ← CURRENT
DO IT     not started
DELIVERED not started
```

Next design decision:

> **Q-001 — Select and LOCK the first MVP channel.**

No implementation should begin until the relevant design decision is owner-approved.

---

# 13. CHANGE CONTROL

- Do not silently rewrite D-001 through D-015.
- A new finding may refine DESIGN or ACTION_PLAN.
- A finding that conflicts with a LOCKED decision requires a new explicit decision.
- Upstream AISYNC contract changes must be reconciled before Companion implementation claims compatibility.
- Provider/channel implementation details remain replaceable unless explicitly promoted to architecture decisions.

---

# 14. VERSION HISTORY

| Version | Date | Change |
|---|---|---|
| 0.1.0 | 2026-10-07 | Initialized CrossAI Companion project ZASS using ZASSIMPLE v0.3.0; imported owner-provided/PF-093 Companion locks, recorded open MVP/channel/auth questions, risks, selection matrix, and Draft Design 0.1. |

---

# 15. ZASSIMPLE WORKING RULE

Normal discussion may remain conversational.

When the owner explicitly requests `ZASS` or `ZASS!!`, surface the relevant project update and current selection matrix.

Only the Project Owner may LOCK a final decision.

Preferred command surface:

```text
[🔬 ZASS!!] -- [📌 PROCEED/LOCK] -- [📚 SAVE]
```
