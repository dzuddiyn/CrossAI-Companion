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

## D-016 | LOCKED — Delivery / integration order

**Decision:** Execute the current Companion-facing delivery sequence in this order:

```text
1. Web Chat
2. WhatsApp
3. Temaya integration
4. Telegram
```

**Reason:** Web Chat proves the Companion → CrossAI Compatible → Core boundary with the least channel-specific complexity. WhatsApp is the next external consumer channel priority. Temaya then proves a peer assistant can integrate through CrossAI Compatible without becoming part of Companion. Telegram follows after those three stages.

**Consequence:** The existing upstream AISYNC post-Production roadmap currently places Temaya before Companion MVP and Telegram before WhatsApp. That roadmap must be explicitly reconciled before cross-repository execution reaches those affected stages. This Companion decision does not silently rewrite AISYNC.
## D-017 | LOCKED — Web Chat MVP component boundary

**Decision:** The Web Chat MVP is designed as one end-to-end vertical slice containing three Companion-side components:

```text
1. Web Chat Adapter
2. Companion Runtime
3. CrossAI Compatible Client
```

These three components are designed together because all are required to prove the Companion → Core journey, but they do not need to be separate applications or deployments.

Preferred MVP deployment shape:

```text
CrossAI Companion Runtime B
│
├── Web Chat Adapter
├── Companion Runtime logic
└── CrossAI Compatible Client
        ↓
   network/API boundary
        ↓
CrossAI Core Runtime A
```

**Boundary:**

- **Web Chat Adapter** owns the chat UI/channel input-output surface.
- **Companion Runtime** owns transient conversational/session orchestration, Companion AI calls, possible-idea surfacing, and explicit SAVE interaction.
- **CrossAI Compatible Client** is the deterministic Companion-side connector that sends authorized requests to Core and consumes factual receipts.
- **CrossAI Compatible receiver / Core-side contract implementation** remains under AISYNC / CrossAI Core authority and is not owned by the Companion repository.
- None of the three Companion-side components may become canonical Ideas/Decisions/Projects or SAVE authority.

**Build principle:** Design the three components together, then implement them as the thinnest reversible end-to-end slice rather than completing each subsystem independently before integration.

Target slice:

```text
Web Chat
→ Companion Runtime
→ CrossAI Compatible Client
→ CrossAI Core
→ factual receipt
→ Web Chat
```

**Reason:** This proves the actual product boundary with minimum architecture while preserving future replacement of Web Chat by WhatsApp/Telegram adapters without changing Core semantic authority.

## D-018 | LOCKED — Minimum CrossAI Compatible write contract for Web Chat MVP

**Decision:** Web Chat MVP exposes one CrossAI Compatible write capability: `SAVE_CONFIRMED_IDEA`.

The request carries the verified CrossAI user context, separate transport and semantic-save identities, the exact idea payload explicitly confirmed by the user, confirmation evidence, and minimal provenance.

Core validates the request, replay/idempotency state, user authority and ASC governance; performs the canonical SAVE; verifies the resulting state; and returns a factual receipt with external state `SUCCESS`, `FAILED`, or `UNKNOWN`.

Companion may display **Saved to CrossAI** only for a verified `SUCCESS`. `UNKNOWN` must not be presented as success and must not trigger a blind duplicate retry.

**Provider boundary:** This contract is AI-provider-agnostic. Gemini API, OpenRouter API, or another provider belongs behind a separate Companion AI provider adapter and does not change the CrossAI Compatible SAVE contract.

**Out of scope for this MVP contract:** decision SAVE, project creation/linking, scoped project read, handoff/return, channel binding, billing, and provider/commercial policy.
## D-019 | LOCKED — CrossAI Web Companion auth/session UX and default entry

**Decision:** CrossAI Web is the default Web Companion entry surface. The user is not required to choose an external AI app/provider before starting a Web Companion conversation.

### User-first start

```text
User types naturally in the CrossAI Web chat box
        ↓ SEND
authenticated?
  ├─ YES → continue
  └─ NO
        ↓
preserve the draft
        ↓
Sign in with Google
        ↓
CrossAI Core resolves/creates the authorized CrossAI user identity
        ↓
create/load the user's private CrossAI conversation
        ↓
continue the chat in Web Companion
```

Google/CrossAI authentication remains the identity authority. Companion must not create a parallel username/password account system and must not trust a browser-supplied `crossai_user_id` as identity proof.

### Conversation continuity

A real Web Companion conversation is owned by the authenticated CrossAI user and must be persistent/recoverable across normal accidental interruption such as refresh, closing the tab/window, browser restart, or temporary Internet loss. `SAVE IDEA` is not the mechanism for preserving chat continuity.

```text
authenticated CrossAI user
        ↓ owns
private CrossAI conversation
        ↓ optionally promotes
canonical CrossAI Idea after explicit SAVE
```

Conversation persistence does **not** itself promote chat content into canonical Ideas/Decisions/Projects. Exact retention duration, deletion policy, and storage lifecycle remain Q-004.

### No mandatory external AI selection

For the Web Companion MVP, the visible product default is CrossAI Companion. The user does not need to choose Gemini, ChatGPT, or another external AI app before the first SEND.

At the beginning of a new Companion session, the chat must inform the user in plain language that they may move to another AI app at any time, for example:

> **Anda boleh pindah ke aplikasi AI lain pada bila-bila masa. Sebut sahaja “mahu pindah”, dan sistem akan sediakan perpindahan.**

When the user asks to move (including the natural phrase `mahu pindah`), CrossAI prepares the appropriate transfer/handoff. The transfer mechanism must preserve authorized identity/continuity boundaries and must not falsely claim automatic transfer where the target app only supports copy/paste or another fallback.

### Provider boundary

The underlying Companion inference provider (for example Gemini API or OpenRouter) is an implementation detail of Companion Runtime and is not the same thing as the user's optional decision to move the conversation to another AI app.

### Upstream AISYNC reconciliation

This decision intentionally differs from current AISYNC D-020/D-021, which require explicit AI-provider selection before GO/START. D-022 draft-preservation/auth behavior remains compatible. Before the affected CrossAI Web production flow is implemented, AISYNC D-020/D-021 and related DESIGN/ACTION_PLAN/T-020 evidence must be explicitly reconciled. This Companion decision does not silently rewrite AISYNC.

## D-020 | LOCKED — Core-owned private conversation continuity

**Decision:** CrossAI Core owns durable private conversation persistence and continuity. Companion owns conversational inference and channel interaction only, and passes factual conversation events to Core.

Each authenticated conversation receives a stable conversation/thread identity and appears as a resumable entry in the user's DUMP tree. The display title is mutable presentation metadata; the stable conversation/thread ID is the identity.

### Event-driven persistence

Conversation persistence is primarily event-driven per committed turn:

```text
USER_MESSAGE_SUBMITTED
        ↓
Companion → Core
        ↓
Core persists + acknowledges
        ↓
Companion invokes Gemini/OpenRouter/other provider

ASSISTANT_MESSAGE_COMPLETED / INTERRUPTED
        ↓
Companion → Core
        ↓
Core records factual assistant-turn state
```

A submitted user message must be persisted and acknowledged by Core before AI inference begins. Companion does not persist every streamed token as durable conversation state. Time-driven processing may later be used for reliability checkpoints or housekeeping, but it is not the primary conversation-save mechanism.

### Core continuity authority

Core owns:

- transcript persistence;
- conversation title/indexing for the DUMP tree;
- minimum derived continuity context required for retrieval/resume;
- stable identity and revision/recovery mechanics;
- archive/reopen/delete lifecycle;
- retrieval and resumable conversation state.

Companion passes conversation data/events and must not maintain a competing durable conversation authority.

Core may determine the persistence/continuity representation required to resume the conversation, but automatic conversation persistence must not silently promote chat content into canonical Ideas, Decisions, or Projects. Those require the applicable explicit user-controlled SAVE/governance flow.

### Context scope and privacy

Derived conversation context is scoped to its conversation by default. Context from one conversation must not silently become a global user profile or be injected into unrelated conversations. Any future cross-conversation retrieval/memory behavior requires an explicit scoped design.

### Delete / archive boundary

Archive is not privacy deletion. Explicit conversation deletion removes the conversation transcript, continuity context, search/index projection, and related derived caches. A minimal content-free tombstone may remain only to prevent stale resurrection.

Deleting a conversation does not automatically delete any canonical Idea, Decision, or Project that the user previously promoted from that conversation, and deleting a promoted canonical object does not automatically delete the originating conversation.

### Storage direction

Durable user-owned Google Drive remains the locked future default storage direction for ordinary user content. D-020 locks the conversation lifecycle and authority boundary, not the exact physical folder/file/database representation.

## D-021 | LOCKED — Provider freedom with FREE / BYOK / POWER modes

**Decision:** CrossAI Companion uses a replaceable AI Provider Adapter and must preserve user freedom to change AI providers/models without changing CrossAI conversation identity, Core continuity, or SAVE authority.

The provider strategy supports three runtime modes from the same architecture:

```text
FREE
BYOK
POWER
```

These modes are inference/cost/privacy choices, not different continuity systems.

### FREE mode — first implementation target

The first Companion provider experiment uses **OpenRouter free API access** through a CrossAI-controlled router/allowlist.

CrossAI must not rely on an unrestricted/random free-model router as semantic authority. The Companion router selects only from an explicit, replaceable allowlist of approved free model IDs and, where applicable, approved upstream providers. Exact model/provider names are runtime configuration and are not architecture locks.

OpenRouter may provide transport/provider failover inside those approved bounds. CrossAI must preserve factual provider/model execution metadata for each assistant turn when available.

**Gemini Free Tier remains an allowed FREE-mode alternative/fallback**, not a permanent primary architecture dependency. Because free-provider terms and data-use policies can differ and change, the user must receive clear disclosure that FREE inference may be processed under provider terms that are not suitable for every private/sensitive use case. A user who does not accept those terms should not use that FREE provider/mode.

CrossAI itself is not assumed to be a paid product merely because provider-paid options may exist later.

### BYOK mode

The same Provider Adapter must support a future **Bring Your Own Key / user-authorized provider credential** mode without changing Core continuity semantics.

BYOK may use OpenRouter-supported provider credentials or another direct-provider adapter where appropriate. Provider credentials remain protected runtime secrets and must never become conversation content, browser-visible persistence, or Core semantic state.

Where privacy/data-policy controls are available, BYOK/provider routing may apply explicit provider/model allowlists, data-collection restrictions, ZDR requirements, or equivalent controls. Exact credential UX, storage and revocation mechanics remain implementation/security design.

### POWER mode

The same Provider Adapter must support a future **POWER** mode for stronger/paid inference funded by the user, CrossAI credits/plan, or another explicitly selected commercial mechanism.

POWER changes model/provider/cost capability only. It must not receive stronger semantic authority than FREE or BYOK.

### Provider/model independence

Exact model IDs are runtime configuration because model rosters, names, packages, quotas and migration schedules change quickly.

```text
provider/model changes
≠ conversation identity changes
≠ Core continuity changes
≠ canonical SAVE authority changes
```

CrossAI Core remains the authoritative transcript/context store. Companion sends only the minimum scoped context needed for current inference. Provider-hosted chat/session memory must not become CrossAI continuity authority.

### Routing and privacy boundary

CrossAI-controlled routing policy must be explicit and replaceable:

```text
CrossAI approved mode/policy
        ↓
approved model allowlist
        ↓
approved provider allowlist / privacy constraints where supported
        ↓
Provider Adapter
        ↓
inference provider
```

Unrestricted provider/model selection by an external router is not the default Companion behavior.

FREE mode may have lower quotas, changing model availability, weaker privacy terms or temporary unavailability. Those limitations must be surfaced truthfully rather than hidden.

### Execution provenance

Each completed/interrupted assistant turn should retain minimum factual execution metadata when available, such as:

```text
provider
model
mode = FREE | BYOK | POWER
completion status
fallback/routing metadata where relevant
```

This metadata is for factual provenance/debugging and does not make the AI provider a continuity or semantic authority.

---

# 7. OPEN QUESTIONS

## Q-001 | RESOLVED — First MVP channel and delivery sequence

Resolved by **D-016 | LOCKED**.

```text
1. Web Chat
2. WhatsApp
3. Temaya integration
4. Telegram
```

## Q-002 | RESOLVED — Minimum CrossAI Compatible v1 contract for Web Chat MVP

Resolved by **D-018 | LOCKED**.

## Q-003 | RESOLVED — Companion ↔ CrossAI Web/Core auth/session contract

Resolved by **D-019 | LOCKED**: Google/CrossAI auth remains Core identity authority; draft is preserved through auth; authenticated user owns a persistent private conversation; Web Companion is the default entry without mandatory external AI-app selection; external transfer remains user-triggered.

## Q-004 | RESOLVED — Core-owned private conversation continuity

Resolved by **D-020 | LOCKED**: Core owns durable conversation continuity; persistence is event-driven per committed turn; resumable conversations appear in the user's DUMP tree; context is conversation-scoped by default; archive/delete and tombstone behavior remain distinct from canonical SAVE/promotion.

## Q-005 | RESOLVED — Companion AI provider/model strategy

Resolved by **D-021 | LOCKED**: one replaceable Provider Adapter supports FREE / BYOK / POWER. FREE begins with a CrossAI-controlled allowlist over OpenRouter free API access, with Gemini Free as an allowed alternative/fallback; exact models/providers remain runtime configuration and provider privacy/terms must be disclosed truthfully.

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

## Decision topic: delivery / integration order

| Stage | Candidate | Must-have fit | Main purpose | Main risk / dependency | Status |
|---:|---|---|---|---|---|
| 1 | Web Chat | PASS | Prove Companion conversation → explicit SAVE → CrossAI Compatible → Core receipt | Exact Web auth/session + Compatible contract still OPEN | **D-016 LOCKED — FIRST** |
| 2 | WhatsApp | PASS | Prove external consumer channel + verified account binding | WhatsApp API/account/provider mechanics remain OPEN | **D-016 LOCKED — SECOND** |
| 3 | Temaya integration | PASS | Prove a peer assistant can use CrossAI Compatible without Companion | Requires Compatible contract mature enough for external assistant integration | **D-016 LOCKED — THIRD** |
| 4 | Telegram | PASS | Add shared Telegram bot + binding after earlier boundaries are proven | Telegram webhook/binding implementation remains OPEN | **D-016 LOCKED — FOURTH** |

**Current direction:** Sequence is owner-LOCKED. D-017 locks the Web Chat MVP vertical slice, D-018 its minimum SAVE contract, D-019 its Web auth/start UX, D-020 Core-owned event-driven private conversation continuity, and D-021 the replaceable FREE/BYOK/POWER provider strategy. The next unresolved design topic is **Q-006 idea-detection orchestration**.
---

# 10. DESIGN — DRAFT 0.1

**Status:** PENDING CONFIRMATION  
**Design Progress:** 4/4 coverage — purpose / main flow / main elements / relevant LOCKED decisions  
**Confirmation blocker:** Q-006 exact idea-detection orchestration is still OPEN.

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

1. **Web Chat Adapter** — channel/UI input-output surface.
2. **Companion Runtime** — private transient session, conversational AI orchestration, possible-idea surfacing, explicit SAVE interaction.
3. **CrossAI Compatible Client** — deterministic Companion-side connector to Core.
4. Channel/user → CrossAI identity resolution.
5. Core-side CrossAI Compatible receiver.
6. Core-side authorization/governance.
7. Canonical SAVE + factual receipt.
8. CrossAI Web read/inspection of the same saved state.

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

> **Q-006 — Define exact idea-detection orchestration between Companion AI and Core-side CrossAI Intelligence while preserving explicit user-controlled promotion.**

No implementation should begin until this boundary is sufficiently designed and owner-approved.

---

# 13. CHANGE CONTROL

- Do not silently rewrite D-001 through D-021.
- A new finding may refine DESIGN or ACTION_PLAN.
- A finding that conflicts with a LOCKED decision requires a new explicit decision.
- Upstream AISYNC contract changes must be reconciled before Companion implementation claims compatibility.
- Provider/channel implementation details remain replaceable unless explicitly promoted to architecture decisions.

---

# 14. VERSION HISTORY

| Version | Date | Change |
|---|---|---|
| 0.1.6 | 2026-10-07 | LOCKED D-021 provider freedom strategy: replaceable Provider Adapter with FREE/BYOK/POWER modes; FREE starts with CrossAI-controlled OpenRouter free allowlist, Gemini Free remains alternative/fallback, privacy/terms disclosed, and exact models/providers remain runtime configuration. |
| 0.1.5 | 2026-10-07 | LOCKED D-020 Core-owned private conversation continuity: stable resumable conversation identity in DUMP tree, event-driven turn persistence, Core-owned transcript/context/recovery lifecycle, conversation-scoped context, archive/delete+tombstone boundary, and Google Drive as future durable user-owned storage direction. |
| 0.1.4 | 2026-10-07 | LOCKED D-019 CrossAI Web Companion auth/session UX: type-first chat, Google/CrossAI identity authority, draft preservation, persistent private conversation, no mandatory external AI selection, user-triggered `mahu pindah` handoff, and explicit upstream AISYNC D-020/D-021 reconciliation requirement. |
| 0.1.3 | 2026-10-07 | LOCKED D-018 minimum Compatible write contract for Web Chat MVP: SAVE_CONFIRMED_IDEA with verified receipt semantics; provider choice remains separate and provider-agnostic at this boundary. |
| 0.1.2 | 2026-10-07 | LOCKED D-017 Web Chat MVP component boundary: Web Chat Adapter + Companion Runtime + CrossAI Compatible Client as one Companion-side vertical slice; Core-side Compatible receiver remains AISYNC authority. |
| 0.1.1 | 2026-10-07 | LOCKED D-016 delivery/integration sequence: Web Chat → WhatsApp → Temaya integration → Telegram; resolved Q-001, updated selection matrix, and advanced next design gate to Q-002 CrossAI Compatible v1 minimum contract. |
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
