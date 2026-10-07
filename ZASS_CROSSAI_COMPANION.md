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

## D-022 | LOCKED — Routed conversation domains before canonical promotion

**Decision:** CrossAI Companion and Core recognize three structured conversation signals/domains in addition to ordinary chat:

```text
IDEA
DECIDE
DESIGN
```

These route a conversation into an appropriate Core-owned continuity tree without automatically creating canonical Decisions or full Projects.

### Visible tree model

The user-facing conversation trees are:

```text
CHAT
├── ordinary conversations
└── [IDEA] <short title>

DECISION
└── [DECIDE] <short title>

DESIGN
└── [DESIGN] <short title>
```

`DESIGN` is the visible tree name rather than `PROJECT`. Core understands it as the design/project-development domain, but entering the DESIGN tree does not itself create a full Project.

Each entry remains a normal stable Core-owned conversation/thread with a durable conversation identity. Prefixes such as `[IDEA]`, `[DECIDE]`, and `[DESIGN]` are route/title presentation metadata, not identity.

### Detection and explicit intent

Companion AI may emit lightweight `IDEA`, `DECIDE`, or `DESIGN` signals as part of normal conversation inference. CrossAI Intelligence is not required on every turn.

For inferred/non-explicit signals:

```text
Companion signal
      ↓
CrossAI Intelligence screening
      ↓
candidate route / title / relevant relation
      ↓
user confirms the proposed route/promotion where needed
      ↓
Core creates or branches the routed conversation
```

CrossAI Intelligence receives only minimum authorized scoped context and may classify, normalize, relate, or detect likely duplicates/relationships. Its result remains advisory.

When the user expresses explicit intent, probabilistic detection is unnecessary. Examples:

```text
"saya nak pilih antara..."
→ DECIDE

"saya nak reka..."
→ DESIGN

"save idea ini..."
→ IDEA / SAVE IDEA flow
```

Core may route/create the corresponding private conversation directly from that explicit intent while preserving authorization and factual continuity.

### IDEA — MVP canonical promotion supported

IDEA is the only routed domain in the first MVP with a complete canonical promotion write contract.

On explicit user confirmation:

```text
source conversation
      ↓
freeze displayed confirmed idea candidate
      ↓
SAVE_CONFIRMED_IDEA
      ↓
ASC/Core canonical SAVE + verification
      ↓
factual receipt
      ↓
create/link [IDEA] <title> conversation under CHAT tree
```

The canonical Idea and the `[IDEA]` conversation are linked but have separate lifecycles/identities. Deleting one does not silently delete the other.

### DECIDE — routed conversation in MVP, canonical decision SAVE deferred

A DECIDE signal or explicit selection intent creates/branches a private conversation such as:

```text
[DECIDE] Laptop 💻
```

under the `DECISION` tree.

The MVP may continue the comparison/selection discussion there. Creating the DECIDE conversation is not the same as saving a canonical Decision. The full canonical Decision SAVE contract is deferred to a later explicit design.

### DESIGN — routed conversation in MVP, full Project creation deferred

A DESIGN signal or explicit design/build intent creates/branches a private conversation such as:

```text
[DESIGN] Offline IoT
```

under the visible `DESIGN` tree.

This does **not** automatically create a full Project.

Project promotion requires explicit user intent, for example:

```text
[DESIGN] Offline IoT
      ↓
"jadikan ini project"
      ↓
CREATE PROJECT
      ↓
user-owned Google Drive project space
      ↓
GitHub optional:
[ CREATE NEW ] / [ LINK EXISTING ] / [ NOT NOW ]
```

The exact Project-creation contract is deferred and remains governed by the upstream Drive-first CrossAI direction. GitHub must remain optional, not a prerequisite.

### Channel independence

The routed conversation/tree state is Core-owned and channel-independent. Web, WhatsApp, Telegram, or future Companion adapters may continue the same authorized conversation IDs after identity binding/resolution.

```text
Web ──────┐
WhatsApp ─┼→ Companion → Core-owned routed conversation
Telegram ─┘
```

A messaging channel does not need to host the CrossAI tree UI to continue a routed conversation. CrossAI Web remains the richer browse/manage surface, while external channels can resolve, create, and continue authorized Core conversations through the same continuity authority.

### Governance invariant

```text
route/tag conversation
≠ canonical SAVE

[DECIDE] conversation
≠ saved Decision

[DESIGN] conversation
≠ Project

AI signal
≠ user decision
```

Canonical promotion remains subject to the applicable explicit user-controlled flow and factual Core receipt.

## D-023 | LOCKED — PROJECT is the visible tree; [DESIGN] remains the conversation/domain label

**Decision:** The user-facing tree previously described in D-022 as `DESIGN` is renamed to **PROJECT**.

This decision supersedes only the visible-tree naming portion of D-022. The underlying routed domain remains `DESIGN`, and child conversations remain human-readable design threads such as:

```text
PROJECT
├── [DESIGN] Offline IoT
├── [DESIGN] Kerani AI
└── [DESIGN] Farm dashboard
```

Core therefore distinguishes:

```text
visible tree = PROJECT
conversation/domain route = DESIGN
canonical Project = not yet created
```

Entering or creating a `[DESIGN]` conversation under PROJECT does **not** create a full Project.

Full Project promotion requires explicit user intent:

```text
[DESIGN] Offline IoT
      ↓
"jadikan ini project"
      ↓
CREATE PROJECT
      ↓
user-owned Google Drive project space
      ↓
GitHub?
[ CREATE NEW ] / [ LINK EXISTING ] / [ NOT NOW ]
```

GitHub must be offered at promotion time but remains optional. CrossAI must not silently create a GitHub repository and must not require GitHub merely to create the Drive-first Project.

**Reason:** `PROJECT` is the clearer human-facing destination, while `[DESIGN]` preserves the meaning that the child thread is still design work until the user explicitly promotes it into a durable Project.

## D-024 | LOCKED — Persistent external-channel binding, shared Telegram, and BYOC WhatsApp

**Decision:** External channels use a persistent Core-owned binding model. The short-lived timeout applies only to the initial pairing credential/request; once verification succeeds, the resulting channel binding remains `ACTIVE` until explicitly revoked, replaced, invalidated by the platform/credential state, or otherwise terminated by an authorized lifecycle action.

```text
initial pairing request
(short-lived, single-use)
        ↓
verified
        ↓
ACTIVE persistent binding
        ↓
normal chat does NOT require re-binding
```

### Two-layer channel model

CrossAI distinguishes:

```text
A. CHANNEL CONNECTION
   who owns/configures the bot/channel installation?

B. USER BINDING
   which CrossAI user is the verified human/channel identity?
```

Channel connection and user binding are separate authorities.

### Generic user-binding lifecycle

CrossAI Web/Core remains the account-binding authority. An authenticated CrossAI user initiates a short-lived, single-use binding request. The default pairing expiry is **10 minutes**, runtime-configurable.

The external channel must prove control using:

- a platform-derived `channel_user_id`;
- the pending one-time binding credential/deep-link/QR flow;
- the expected channel/installation scope.

Companion must never trust a user-typed phone number, username, or arbitrary channel identifier as identity proof.

Core validates and atomically consumes the pending request while creating the persistent binding.

```text
ISSUED / PENDING
   ├──→ EXPIRED
   ├──→ CANCELLED
   └──→ CONSUMED → ACTIVE → REVOKED
```

Consumed, expired, cancelled, or revoked pairing credentials cannot be replayed or silently reactivated.

Each external `channel_user_id` may belong to at most one CrossAI user at a time. One CrossAI user may hold multiple verified external-channel bindings.

An existing external identity must never be silently transferred to another CrossAI account. Transfer requires explicit revoke/unlink plus a new verified binding.

### Revoke, rebind, and recovery

Authenticated CrossAI Web must allow the user to inspect and revoke connected channels.

Loss of an external channel does not imply loss of Core continuity:

```text
old channel → revoked
new channel → newly verified binding
                ↓
same crossai_user_id
                ↓
same authorized Core continuity
```

A user who can still authenticate to CrossAI may revoke a lost external channel without needing access to that old channel.

Loss of the Google/CrossAI account follows the CrossAI/Google account-recovery path. Possession of a Telegram/WhatsApp identity is **not** sufficient to recover or take ownership of a CrossAI account.

Binding resolves identity only; Core authorization still governs conversation, Idea, Decision, Project, and SAVE access.

### Telegram — CrossAI-owned shared bot

Telegram uses a **single CrossAI-owned shared bot/service** for many users.

```text
CrossAI shared Telegram bot
          ↓
many telegram_user_id values
          ↓
persistent verified bindings
          ↓
crossai_user_id
```

Each user completes the one-time binding flow, after which normal Telegram chat does not require re-binding. Exact webhook/runtime/rate-limit implementation remains replaceable channel implementation work.

### WhatsApp — BYOC (Bring Your Own Channel)

WhatsApp uses a **BYOC — Bring Your Own Channel** model rather than requiring CrossAI to fund and operate one shared WhatsApp Business/Cloud API account for all users.

The user connects their own Meta/WhatsApp channel installation through CrossAI Web and supplies the required installation/account identifiers and protected credentials according to the final Meta/WhatsApp API capability.

Conceptually:

```text
USER-001
   ↓
CrossAI Web → Connect WhatsApp
   ↓
user-owned Meta / WhatsApp Cloud API installation
   ↓
CrossAI verifies channel connection
   ↓
CHANNEL CONNECTION ACTIVE
```

A separate one-time user-binding proof then establishes the human/channel identity that is allowed to act as that CrossAI user:

```text
platform-derived WhatsApp user identity
        ↓
verified one-time binding
        ↓
persistent whatsapp_user_id ↔ crossai_user_id
```

Connecting a WhatsApp installation does not by itself authorize every person who can message that number.

Meta/WhatsApp quotas, billing, account standing, template/message rules, and paid usage belong to the user's own Meta/WhatsApp account. CrossAI must not hard-code a fixed free-message quota because provider limits/pricing may change. CrossAI should surface those external dependencies truthfully and leave payment for continued Meta/WhatsApp usage between the user and the external provider.

WhatsApp credentials are protected runtime secrets; they must not become ordinary conversation content or semantic Core state. Exact credential storage, rotation, revocation, webhook verification, and platform-specific setup UX remain implementation/security design.

### Free product + BYOC + BYOK principle

Current product direction is:

> **CrossAI is free as-is; users may bring their own channel (BYOC) and bring their own AI/provider key (BYOK) when they want capabilities, quotas, privacy tiers, or paid usage beyond the free path.**

```text
CrossAI continuity/orchestration
        = free product direction

external channel cost
        = user ↔ channel provider

external AI inference cost
        = FREE provider quota or user BYOK/provider account
```

This refines D-021: the existing FREE / BYOK / POWER architecture remains valid, but **POWER does not imply that CrossAI itself must become a paid subscription product**. Under the current direction, stronger paid capability should preferentially be user-funded through BYOK/external-provider mechanisms. Any future CrossAI-paid plan/credits model requires a new explicit owner decision.

### Channel interchangeability

Web, shared Telegram, and BYOC WhatsApp converge on the same Core-owned continuity:

```text
Web Companion ───────────────┐
CrossAI shared Telegram ─────┼→ Companion → Core
User-owned WhatsApp (BYOC) ──┘
```

No channel owns semantic memory. Once identity is resolved, all authorized channels may create/continue the same Core-owned conversation identities according to Core scope and routing rules.

CrossAI Web remains the richer account/browse/manage surface; Telegram or WhatsApp may become the user's normal conversational surface without needing to reproduce the full CrossAI Web tree UI.

## D-025 | LOCKED — Normalize user-facing trees vs internal semantic routes

**Decision:** CrossAI separates the user-facing navigation/tree labels from the internal semantic/method routing domains.

User-facing tree/navigation labels are:

```text
CHAT
DECISION
PROJECT
```

Internal semantic/method routing domains are:

```text
DUMP
DECIDE
DESIGN
```

The mapping is:

```text
CHAT      ↔ DUMP
DECISION  ↔ DECIDE
PROJECT   ↔ DESIGN
```

This decision normalizes and supersedes older user-facing wording such as `DUMP tree` or visible `DESIGN tree` where those labels referred to ordinary-user navigation. The internal method/domain names remain valid for routing, lineage, diagnostics, advanced views, and method execution.

Examples:

```text
CHAT
├── ordinary conversation
└── [IDEA] Offline IoT

DECISION
└── [DECIDE] Laptop

PROJECT
└── [DESIGN] Offline IoT
```

The prefixes `[IDEA]`, `[DECIDE]`, and `[DESIGN]` remain human-readable conversation labels. They do not change the underlying stable conversation identity or automatically create canonical Ideas, Decisions, or Projects.

Core therefore understands:

```text
visible tree label
≠ internal semantic route
≠ canonical promoted object
```

This is a presentation/routing normalization only. It does not change the locked explicit-promotion, continuity, SAVE, provider, or channel-binding semantics.

## D-026 | LOCKED — Graceful fallback when CrossAI Intelligence is unavailable

**Decision:** CrossAI Intelligence is an optional semantic-screening dependency, not a hard availability dependency for ordinary Companion conversation, Core continuity, explicit routing, or already-authorized deterministic SAVE operations.

```text
CrossAI Intelligence unavailable
≠ Companion unavailable
≠ Core continuity unavailable
```

### Explicit intent remains deterministic

When the user expresses clear intent, CrossAI does not require probabilistic semantic screening before routing.

Examples:

```text
"saya nak pilih antara..."
→ DECIDE route

"saya nak reka..."
→ DESIGN route

"save idea ini"
→ explicit IDEA / SAVE flow
```

If identity, authorization, required payload, and Core governance checks are otherwise satisfied, explicit routing and the applicable deterministic Core operation may continue even when CrossAI Intelligence is unavailable.

### Inferred signals degrade safely

For non-explicit signals:

```text
Companion detects possible IDEA / DECIDE / DESIGN signal
        ↓
CrossAI Intelligence available?
   ├─ YES → screen / normalize / relate / dedupe
   │        → candidate route/promotion
   │
   └─ NO  → no silent auto-route
            no silent semantic promotion
            continue conversation or surface a tentative candidate
```

If Companion surfaces a tentative candidate while Intelligence is unavailable, the user may explicitly confirm the route. That confirmation becomes explicit user intent and Core may then route the conversation deterministically.

### What is lost during degradation

While CrossAI Intelligence is unavailable, CrossAI may temporarily lose or defer advisory features such as:

- inferred semantic screening;
- normalization assistance;
- duplicate/relationship suggestions;
- related-project suggestions;
- richer semantic retrieval assistance.

Those missing advisory capabilities must not be represented as successfully completed.

### Availability boundary

Companion AI, CrossAI Intelligence, and Core continuity remain separate failure domains:

```text
Companion AI
= conversation inference

CrossAI Intelligence
= narrow semantic screening/advice

CrossAI Core
= identity + continuity + governance + factual SAVE truth
```

A failure or quota exhaustion in CrossAI Intelligence must not erase submitted messages, prevent access to existing authorized conversations, or convert factual Core state into UNKNOWN unless the Core operation itself is genuinely uncertain.

This decision does not require a specific CrossAI Intelligence provider/model. Its provider, model, queueing, retry, and later recovery behavior remain implementation/runtime design.

## D-027 | LOCKED — AISYNC reconciliation is a hard gate before DO IT

**Decision:** CrossAI Companion must not enter implementation of the affected Web start/auth/provider-routing flow while the authoritative AISYNC `main` branch still contains conflicting LOCKED behavior.

The confirmed conflict is:

```text
AISYNC D-020 / D-021
User MUST choose AI provider before GO / START
        ≠
Companion D-019
Web Companion starts naturally without mandatory provider selection
```

This decision strengthens the reconciliation note already recorded in D-019.

### Hard gate

Before Companion moves into **DO IT** for any flow that depends on Web start, authentication continuation, provider selection, intent routing, or handoff:

1. refresh authoritative AISYNC `main`;
2. identify the still-applicable conflicting decisions/design/action-plan/task/proof wording;
3. create an explicit owner-approved AISYNC refinement/superseding decision;
4. update the affected AISYNC confirmed design/action-plan/task or proof surfaces consistently;
5. merge that reconciliation into AISYNC `main`;
6. verify the live merged state before claiming CrossAI Companion compatibility.

Until those conditions are satisfied:

```text
Companion DESIGN / ACTION planning may continue
but
affected Companion DO IT = BLOCKED
```

### No silent precedence

Neither repository may silently override the other.

- Companion D-019 remains the locked Companion product direction.
- Existing AISYNC D-020/D-021 remain historically authoritative inside AISYNC until explicitly refined/superseded there.
- A Companion implementation must not simply ignore AISYNC.
- AISYNC must not silently rewrite Companion D-019.
- Compatibility may be claimed only after both repositories express a reconciled boundary.

### Reconciliation target

The intended reconciliation must preserve at minimum:

- user-first natural-language entry;
- Google/CrossAI identity authority;
- draft preservation through authentication;
- Core-owned private conversation continuity;
- internal DUMP / DECIDE / DESIGN routing behind human-facing CHAT / DECISION / PROJECT surfaces;
- provider freedom without making provider choice a mandatory first-click requirement for Web Companion;
- explicit external handoff when the user chooses another AI app/provider.

The exact AISYNC decision number, patch version, task/proof changes, and implementation sequence are determined when the reconciliation is executed against the then-current AISYNC `main`.

### Scope

This gate blocks implementation of the **affected cross-repository front-door contract**, not ordinary documentation review or further DESIGN/ACTION_PLAN refinement. No code, deployment, or production compatibility claim for the affected path should proceed ahead of the upstream reconciliation.

## D-028 | LOCKED — Routed conversations branch by lineage, not transcript duplication

**Decision:** When ordinary conversation work is promoted or routed into a dedicated `[IDEA]`, `[DECIDE]`, or `[DESIGN]` conversation, CrossAI creates a new stable Core-owned conversation identity linked to its source rather than copying/moving the entire source transcript.

Canonical branching model:

```text
source conversation
CONV-100
   │
   │ source lineage / triggering event(s)
   ↓
routed conversation
CONV-101
[IDEA] / [DECIDE] / [DESIGN]
```

The source conversation remains intact and independently resumable.

### No transcript cloning

CrossAI must not duplicate the full source transcript into the routed conversation merely to create continuity.

Instead, the new routed conversation receives only the minimum seed context required to continue the routed work, such as:

- source conversation identity;
- relevant source event/message references;
- route/promotion trigger;
- user-confirmed candidate where applicable;
- concise relevant context/open questions needed to resume.

The exact storage representation remains implementation detail, but the semantic rule is:

```text
lineage + minimum seed context
≠ full transcript copy
```

### Independent evolution after branching

After the branch is created:

```text
CONV-100 continues independently
CONV-101 continues independently
```

Later messages in one conversation do not silently propagate into the other. Cross-conversation context may be brought across only through an explicit/scoped Core retrieval or user action governed by the applicable context rules.

This prevents two editable transcript copies from drifting while preserving traceable origin.

### Route-specific behavior

For an inferred signal, the routed conversation is created only after the applicable user confirmation required by D-022/D-026.

For explicit user intent, Core may create the routed conversation directly:

```text
"saya nak pilih antara A dan B"
→ new [DECIDE] conversation

"saya nak reka offline IoT"
→ new [DESIGN] conversation
```

For confirmed Idea promotion:

```text
source conversation
      ↓
SAVE_CONFIRMED_IDEA
      ↓
canonical Idea
      ↕ linked
new [IDEA] conversation
```

The canonical Idea, source conversation, and routed `[IDEA]` conversation remain distinct identities connected by lineage.

### Avoid unnecessary re-branching

If the user is already inside a conversation whose active route/domain matches the requested work, CrossAI should continue that same conversation rather than create another equivalent child conversation.

A new routed conversation is warranted when the user intentionally branches/promotes work into a distinct route/domain or explicitly requests a separate thread.

### Identity invariant

```text
source CONV identity
≠ routed CONV identity
≠ canonical promoted object identity
```

Titles and prefixes remain presentation metadata. Stable Core conversation IDs and canonical artifact IDs remain the actual identities.

This decision refines D-020/D-022 without changing their Core-owned continuity or explicit-promotion authority.

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

## Q-006 | RESOLVED — Routed IDEA / DECIDE / DESIGN orchestration

Resolved by **D-022 + D-023 | LOCKED**: Companion may signal IDEA/DECIDE/DESIGN; inferred signals are screened by CrossAI Intelligence using minimum scoped context, while explicit user intent may route directly. Core owns stable routed conversations in CHAT / DECISION / PROJECT trees; PROJECT contains `[DESIGN]` conversations while Core retains the DESIGN domain internally. IDEA has the complete MVP canonical SAVE path; canonical Decision SAVE and full Project creation are deferred. `[DESIGN]` becomes a full Project only after explicit promotion, creating a Google Drive project space and then offering GitHub CREATE / LINK / NOT NOW.

## Q-007 | RESOLVED — Persistent binding + shared Telegram + BYOC WhatsApp

Resolved by **D-024 | LOCKED**: the pairing credential is short-lived/single-use, but successful channel binding is persistent; Core owns revoke/rebind/recovery semantics. Telegram uses one CrossAI-owned shared bot for many users. WhatsApp uses BYOC: each user connects their own Meta/WhatsApp installation and bears its external quota/billing/account obligations. Channel connection and human user binding are separate authorities. CrossAI remains free as-is, with BYOC/BYOK as the preferred mechanism for user-controlled external capability and cost.

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

## R-005 | MITIGATED BY D-026 — Runtime / intelligence coupling

Companion, CrossAI Intelligence, and Core continuity must remain separate failure domains. D-026 locks that CrossAI Intelligence unavailability cannot by itself make ordinary Companion/Core continuity unavailable.

## R-006 | OPEN — Provider/commercial premature coupling

Selecting a provider, quota model, or payment tier too early may hard-code product policy into architecture.

## R-007 | MITIGATED BY D-027 — Cross-repository authority conflict

Companion D-019 and current AISYNC D-020/D-021 encode conflicting Web-start provider-selection behavior. D-027 makes explicit AISYNC reconciliation and live merged verification a hard gate before affected Companion DO IT.

## R-008 | MITIGATED BY D-028 — Routed-thread transcript drift

Creating `[IDEA]`, `[DECIDE]`, or `[DESIGN]` threads by cloning full source transcripts would create competing editable histories. D-028 locks lineage-linked branching with minimum seed context and independent stable conversation identities.

---

# 9. CURRENT SELECTION MATRIX

## Decision topic: delivery / integration order

| Stage | Candidate | Must-have fit | Main purpose | Main risk / dependency | Status |
|---:|---|---|---|---|---|
| 1 | Web Chat | PASS | Prove Companion conversation → explicit SAVE → CrossAI Compatible → Core receipt | Exact Web auth/session + Compatible contract still OPEN | **D-016 LOCKED — FIRST** |
| 2 | WhatsApp | PASS | Prove BYOC external consumer channel + persistent verified user binding | BYOC ownership/binding model LOCKED; exact Meta API credential/webhook setup remains implementation work | **D-016 + D-024 LOCKED — SECOND** |
| 3 | Temaya integration | PASS | Prove a peer assistant can use CrossAI Compatible without Companion | Requires Compatible contract mature enough for external assistant integration | **D-016 LOCKED — THIRD** |
| 4 | Telegram | PASS | Add CrossAI-owned shared Telegram bot + persistent user binding after earlier boundaries are proven | Shared-bot/binding model LOCKED; exact webhook/runtime details remain implementation work | **D-016 + D-024 LOCKED — FOURTH** |

**Current direction:** Sequence is owner-LOCKED. D-017 through D-024 now cover the Web Companion vertical slice, minimum SAVE contract, Web auth/start UX, Core-owned event-driven conversation continuity, FREE/BYOK/POWER provider freedom, routed CHAT/DECISION/PROJECT conversations, PROJECT/[DESIGN] naming, and persistent external-channel access through shared Telegram + BYOC WhatsApp. **Q-001 through Q-007 are resolved.**
---

# 10. DESIGN — DRAFT 0.2

**Status:** READY FOR OWNER DESIGN CONFIRMATION  
**Design Progress:** 4/4 coverage — purpose / main flow / main elements / relevant LOCKED decisions  
**Design confirmation blocker:** none identified in the Companion design itself.  
**Pre-DO-IT gate:** D-027 remains mandatory — the affected Web start/auth/provider-routing flow cannot enter implementation until the conflicting AISYNC provider-selection behavior is explicitly reconciled, merged to AISYNC `main`, and verified.

## Purpose

Provide an optional conversational AI surface for CrossAI while keeping CrossAI Core as the sole continuity, identity, governance, lineage, and factual SAVE authority.

CrossAI Companion is replaceable. Channels and AI providers may change without changing the user's Core-owned conversation identity or canonical CrossAI state.

Core principle:

> **CrossAI is the home of the idea. The Companion is only one place where the idea can be born.**

## Product and routing model

Ordinary users see human-facing navigation:

```text
CHAT
DECISION
PROJECT
```

Core/internal method routing remains:

```text
DUMP
DECIDE
DESIGN
```

Mapping:

```text
CHAT      ↔ DUMP
DECISION  ↔ DECIDE
PROJECT   ↔ DESIGN
```

Conversation labels remain human-readable:

```text
CHAT
├── ordinary conversation
└── [IDEA] <title>

DECISION
└── [DECIDE] <title>

PROJECT
└── [DESIGN] <title>
```

A visible tree label, internal semantic route, stable conversation identity, and canonical promoted object are separate concepts.

## Locked delivery sequence

```text
1. Web Chat
2. WhatsApp
3. Temaya integration
4. Telegram
```

The sequence controls delivery priority only. It does not change the common Core continuity or CrossAI Compatible boundaries.

## Main architecture

```text
                          CROSSAI CORE
                ┌──────────────────────────┐
                │ identity / authorization │
                │ Core-owned conversations │
                │ CHAT / DECISION / PROJECT│
                │ lineage / routing        │
                │ ASC governance           │
                │ canonical SAVE truth     │
                │ factual receipts         │
                │ CrossAI Intelligence     │
                └────────────▲─────────────┘
                             │
                    CrossAI Compatible
                             │
                ┌────────────┴─────────────┐
                │ CROSSAI COMPANION        │
                │                          │
                │ Companion orchestration  │
                │ AI Provider Adapter      │
                │ route-signal handling    │
                │ Compatible client        │
                │ receipt presentation     │
                └────────────▲─────────────┘
                             │
                 ┌───────────┼───────────┐
                 │           │           │
                 ↓           ↓           ↓
              Web Chat   BYOC WhatsApp  Telegram
                                      shared bot
```

Temaya, Kerani AI, and future compatible assistants may bypass Companion and use the CrossAI Compatible boundary directly.

## Web Companion start flow

The Web Companion default is user-first:

```text
user types naturally
        ↓
SEND
        ↓
authenticated?
  ├─ YES → continue
  └─ NO
        ↓
preserve draft
        ↓
Google sign-in / CrossAI identity resolution
        ↓
return to authenticated Companion flow
        ↓
create/load private Core-owned conversation
        ↓
continue
```

The user is not required to select an external AI app/provider before beginning the normal Web Companion flow.

The user may later request an external handoff, such as `mahu pindah`. CrossAI must use the available handoff mechanism truthfully and must not claim automatic transfer where only copy/paste or another fallback is possible.

## Core-owned conversation persistence

Conversation continuity is durable and belongs to Core, not Companion and not the inference provider.

Primary event flow:

```text
USER_MESSAGE_SUBMITTED
        ↓
Companion → Core
        ↓
Core persists + ACK
        ↓
Companion invokes AI provider
        ↓
assistant streams/responds
        ↓
ASSISTANT_MESSAGE_COMPLETED / INTERRUPTED
        ↓
Companion → Core
        ↓
Core records factual assistant-turn state
```

A submitted user message must be persisted/acknowledged before the provider call begins.

Companion may keep only the transient runtime state required to serve the active interaction. It must not become a competing durable transcript or semantic authority.

Conversation continuity is scoped to the active conversation by default. Cross-conversation context requires explicit/scoped Core retrieval or user action.

## Routed conversation branching

When work moves into a dedicated IDEA / DECIDE / DESIGN conversation, CrossAI branches by lineage rather than cloning the entire transcript.

```text
source conversation
CONV-100
   │
   │ source lineage / triggering event(s)
   ↓
routed conversation
CONV-101
[IDEA] / [DECIDE] / [DESIGN]
```

The new routed conversation receives only the minimum seed context required to continue:

- source conversation identity;
- relevant source event/message references;
- route/promotion trigger;
- confirmed candidate where applicable;
- concise relevant context/open questions.

```text
lineage + minimum seed context
≠ full transcript copy
```

Source and routed conversations then evolve independently. If the current conversation already matches the requested route/domain, CrossAI continues it instead of creating an unnecessary equivalent child thread.

## IDEA / DECIDE / DESIGN orchestration

Companion may notice possible `IDEA`, `DECIDE`, or `DESIGN` signals during normal conversation.

### Explicit intent

Clear user intent routes deterministically without requiring CrossAI Intelligence screening.

```text
"saya nak pilih antara..."
→ DECIDE

"saya nak reka..."
→ DESIGN

"save idea ini..."
→ IDEA / SAVE flow
```

### Inferred intent

```text
Companion detects possible signal
        ↓
CrossAI Intelligence available?
  ├─ YES → screen / normalize / relate / dedupe
  │        → advisory candidate
  └─ NO  → no silent auto-route
           no silent promotion
           continue chat or surface tentative candidate
```

If the user explicitly confirms a tentative candidate, that confirmation becomes explicit user intent and Core may route deterministically.

CrossAI Intelligence is therefore an advisory semantic dependency, not a hard availability dependency.

```text
CrossAI Intelligence unavailable
≠ Companion unavailable
≠ Core continuity unavailable
```

## Canonical promotion model

Routing a conversation and creating a canonical object are separate actions.

```text
route/tag conversation
≠ canonical SAVE

[DECIDE] conversation
≠ saved Decision

[DESIGN] conversation
≠ Project
```

### IDEA — MVP canonical write path

IDEA has the first complete canonical write contract:

```text
source conversation
      ↓
user confirms displayed Idea candidate
      ↓
SAVE_CONFIRMED_IDEA
      ↓
Core authorization + ASC governance
      ↓
canonical SAVE
      ↓
independent verification
      ↓
SUCCESS | FAILED | UNKNOWN receipt
      ↓
on verified SUCCESS:
create/link [IDEA] conversation
```

Companion may display **Saved to CrossAI** only after verified `SUCCESS`.

The canonical Idea, source conversation, and linked `[IDEA]` conversation remain separate identities connected by lineage.

### DECIDE — conversation support first

The MVP supports routed `[DECIDE]` conversations. A full canonical Decision SAVE contract is deferred to a later explicit contract.

### PROJECT / DESIGN — conversation first, Project only after promotion

A `[DESIGN]` conversation lives under the visible PROJECT tree but is not itself a full Project.

```text
[DESIGN] Offline IoT
      ↓
"jadikan ini project"
      ↓
CREATE PROJECT
      ↓
user-owned Google Drive project space
      ↓
GitHub?
[ CREATE NEW ] / [ LINK EXISTING ] / [ NOT NOW ]
```

GitHub is offered but optional. CrossAI must not silently create a repository or require GitHub merely to create the Drive-first Project.

## AI provider strategy

Companion uses one replaceable AI Provider Adapter.

```text
FREE
BYOK
POWER
```

These are inference/cost/privacy modes, not different continuity systems.

### FREE

First implementation target:

```text
CrossAI-controlled approved free model/provider policy
        ↓
OpenRouter free API experiment
        ↓
replaceable provider/model
```

Gemini Free remains an allowed alternative/fallback. Exact model/provider IDs remain runtime configuration.

FREE limitations, quotas, availability, and privacy/data-use conditions must be surfaced truthfully.

### BYOK

Users may supply/authorize their own AI provider credential without changing Core continuity. Credentials remain protected runtime secrets and must not become browser-persisted conversation content or Core semantic state.

### POWER

POWER allows stronger/paid inference without granting stronger semantic authority. Current direction prefers user-funded external-provider/BYOK mechanisms rather than requiring CrossAI itself to become a paid subscription product.

```text
provider/model changes
≠ conversation identity changes
≠ Core continuity changes
≠ canonical SAVE authority changes
```

## External-channel model

CrossAI separates:

```text
A. CHANNEL CONNECTION
   who owns/configures the channel installation?

B. USER BINDING
   which verified channel identity maps to the CrossAI user?
```

The pairing credential is short-lived and single-use, but a successful binding is persistent.

```text
PENDING pairing
(short-lived)
      ↓
verified
      ↓
ACTIVE persistent binding
      ↓
normal chat does not require re-binding
```

Binding resolves identity only. Core authorization still governs access to conversations, Ideas, Decisions, Projects, and SAVE operations.

### Telegram

Telegram uses one CrossAI-owned shared bot/service for many users.

```text
CrossAI shared Telegram bot
        ↓
telegram_user_id
        ↓
persistent verified binding
        ↓
crossai_user_id
```

### WhatsApp — BYOC

WhatsApp uses **BYOC — Bring Your Own Channel**.

```text
CrossAI user
      ↓
connect own Meta / WhatsApp installation
      ↓
verify channel connection
      ↓
verify platform-derived WhatsApp user identity
      ↓
persistent user binding
```

The user's Meta/WhatsApp account owns its external quota, billing, account standing, and platform obligations. CrossAI must not hard-code a fixed free-message allowance.

Current product principle:

> **CrossAI is free as-is; users may BYOC and BYOK for user-controlled external capability, quota, privacy, or paid usage.**

## Failure-domain separation

The system must preserve these boundaries:

```text
Companion Runtime failure
≠ Core continuity failure

CrossAI Intelligence failure
≠ Companion failure

AI provider failure
≠ conversation identity loss

channel failure
≠ semantic memory loss

channel/provider cost change
≠ continuity-model change
```

Rate limits, quota exhaustion, provider outage, or external-channel failure must be represented truthfully rather than converted into false SAVE success or silent data loss.

## Main elements

1. **Web Chat Adapter** — first delivery surface and default Web Companion UI.
2. **External Channel Adapters** — BYOC WhatsApp and shared Telegram transport adapters.
3. **Companion Runtime** — conversational orchestration, route-signal handling, provider invocation, and receipt presentation.
4. **AI Provider Adapter** — replaceable FREE / BYOK / POWER inference boundary.
5. **CrossAI Compatible Client** — deterministic Companion-side connector to Core.
6. **CrossAI Compatible Core receiver** — authenticated/authorized stable integration boundary.
7. **Core Conversation Continuity** — stable conversation IDs, transcript events, routing/tree state, archive/delete/recovery.
8. **CrossAI Intelligence** — optional low-volume semantic screening/advisory service.
9. **ASC/Core Governance** — authorization, explicit promotion, idempotency, canonical SAVE, verification, factual receipt.
10. **User-owned Google Drive** — durable default project/content direction where applicable.
11. **Optional GitHub integration** — create/link only after explicit Project promotion or later user choice.

## Architecture invariants

```text
Companion changes
≠ Core continuity changes

channel changes
≠ semantic authority changes

AI provider changes
≠ conversation identity changes

CrossAI Intelligence outage
≠ Companion/Core continuity outage

route/tag conversation
≠ canonical promoted object

source CONV identity
≠ routed CONV identity
≠ canonical artifact identity

visible CHAT / DECISION / PROJECT
≠ internal DUMP / DECIDE / DESIGN

binding
≠ bypass Core authorization
```

## Locked-decision lineage

This draft is derived from the current owner-LOCKED Companion decision set:

```text
D-016  delivery/integration order
D-017  Web MVP component boundary
D-018  SAVE_CONFIRMED_IDEA contract
D-019  Web auth/start UX
D-020  Core-owned conversation continuity
D-021  FREE / BYOK / POWER provider freedom
D-022  IDEA / DECIDE / DESIGN routed conversations
D-023  PROJECT visible tree + [DESIGN] child threads
D-024  persistent binding + shared Telegram + BYOC WhatsApp
D-025  visible vs internal routing normalization
D-026  graceful CrossAI Intelligence fallback
D-027  mandatory AISYNC reconciliation gate before affected DO IT
D-028  lineage-based routed-conversation branching
```

## Open implementation boundaries — not design blockers

The following remain implementation/runtime work and do not silently alter this design:

- exact AI model IDs/provider roster;
- exact CrossAI Intelligence provider/model;
- exact physical conversation/Drive storage schema;
- exact WhatsApp Meta credential/webhook setup and secret lifecycle;
- exact Telegram webhook/runtime deployment;
- exact queue/backpressure implementation;
- exact routed-thread seed-context representation;
- canonical Decision SAVE contract;
- full CREATE PROJECT contract;
- future cross-conversation retrieval policy beyond explicit/scoped retrieval.

## Confirmation state

The design has complete coverage of:

```text
Purpose                  ✓
Main flow                ✓
Main elements            ✓
LOCKED decision lineage  ✓
```

No unresolved Companion design question from Q-001 through Q-007 blocks owner confirmation.

However:

```text
DESIGN confirmation
≠ authorization to start affected DO IT
```

D-027 remains a hard cross-repository implementation gate until AISYNC reconciliation is completed and verified.

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

> **No remaining Q-001–Q-007 design blocker is open.**

The current Companion architecture decision set is ready for owner-controlled DESIGN confirmation / action-plan slicing. This statement does not authorize implementation or merge by itself.

---

# 13. CHANGE CONTROL

- Do not silently rewrite D-001 through D-028.
- A new finding may refine DESIGN or ACTION_PLAN.
- A finding that conflicts with a LOCKED decision requires a new explicit decision.
- Upstream AISYNC contract changes must be reconciled before Companion implementation claims compatibility.
- Provider/channel implementation details remain replaceable unless explicitly promoted to architecture decisions.

---

# 14. VERSION HISTORY

| Version | Date | Change |
|---|---|---|
| 0.1.14 | 2026-10-07 | Rewrote DESIGN DRAFT 0.2 from the current LOCKED D-016–D-028 set: persistent Core-owned conversations, CHAT/DECISION/PROJECT vs DUMP/DECIDE/DESIGN normalization, lineage-based branching, graceful Intelligence fallback, FREE/BYOK/POWER, persistent binding, shared Telegram, BYOC WhatsApp, explicit promotion, and the D-027 pre-DO-IT AISYNC reconciliation gate. No new architecture decision was introduced. |
| 0.1.13 | 2026-10-07 | LOCKED D-028 routed-conversation branching: new IDEA/DECIDE/DESIGN threads use distinct Core conversation IDs linked by lineage and minimum seed context rather than full transcript cloning; source and child evolve independently and matching-route conversations avoid unnecessary re-branching. |
| 0.1.12 | 2026-10-07 | LOCKED D-027 AISYNC reconciliation gate: current AISYNC mandatory provider-selection behavior conflicts with Companion D-019; affected Web start/auth/provider-routing DO IT is blocked until an explicit owner-approved AISYNC refinement is merged and verified on AISYNC main. |
| 0.1.11 | 2026-10-07 | LOCKED D-026 graceful Intelligence fallback: CrossAI Intelligence is optional for inferred semantic screening, explicit routing remains deterministic, inferred signals never silently auto-route when Intelligence is unavailable, and Companion/Core continuity remain usable. |
| 0.1.10 | 2026-10-07 | LOCKED D-025 routing normalization: user-facing navigation is CHAT / DECISION / PROJECT while internal semantic/method routing remains DUMP / DECIDE / DESIGN; older visible DUMP/DESIGN wording is superseded without changing canonical promotion or conversation identity. |
| 0.1.9 | 2026-10-07 | LOCKED D-024 external-channel model: first-time pairing is short-lived/single-use but successful binding persists; Telegram uses one CrossAI-owned shared bot, WhatsApp uses BYOC user-owned Meta/Cloud API connection, channel connection and human binding are separate, and CrossAI remains free-as-is with BYOC/BYOK for external capability/cost. |
| 0.1.8 | 2026-10-07 | LOCKED D-023 visible-tree refinement: PROJECT replaces visible DESIGN tree while child threads remain `[DESIGN]`; full Project exists only after explicit promotion to a Drive-first project space, followed by optional GitHub CREATE/LINK/NOT NOW. |
| 0.1.7 | 2026-10-07 | LOCKED D-022 routed conversation orchestration: CHAT carries ordinary/[IDEA] conversations, DECISION carries [DECIDE], DESIGN remains the routed domain for [DESIGN] threads; explicit intent can route directly, IDEA canonical SAVE is MVP-complete, and canonical Decision SAVE/full Project creation are deferred. |
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
