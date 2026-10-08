# CrossAI Companion Provider Router — Future Work

**Status:** AGREED FUTURE-WORK CANDIDATE — NOT IMPLEMENTATION LOCK  
**Date:** 2026-10-08  
**Owner:** Project Owner  
**Repository ownership:** CrossAI Companion  
**Scope:** Future model/provider selection inside Companion conversational inference only.  
**MVP effect:** NONE — this document does not change DESIGN DRAFT 0.2 or the current MVP scope.

## Candidate

CrossAI Companion should later support a **Companion Provider Router** that can select an approved conversational AI model/provider according to task needs, current availability, user mode, privacy policy, quota/cost constraints, and configured FREE/BYOK/POWER policy.

The router exists to take advantage of free/provider capacity while preserving the CrossAI principle that AI intelligence is replaceable beneath user-owned continuity.

Conceptual boundary:

```text
Companion request
      ↓
Companion Provider Router
      ↓
approved routing policy
      ↓
approved model/provider candidate
      ↓
AI Provider Adapter
      ↓
inference provider
```

Potential future routing examples:

```text
casual conversation     → suitable fast/free model
Malay conversation      → model proven suitable for Malay
coding assistance       → coding-capable model
heavy reasoning         → stronger reasoning-capable model
summarization           → economical/fast model
structured extraction   → model proven reliable for structured output
```

These examples are illustrative only. No provider/model ID is locked by this candidate.

## Authority boundary

The Provider Router is **not** semantic authority.

```text
Provider Router
≠ conversation identity authority
≠ Core continuity authority
≠ intent/lifecycle authority
≠ canonical SAVE authority
≠ CrossAI Intelligence authority
```

CrossAI Core remains responsible for identity, authorization, continuity, routing state, governance, canonical state, and factual receipts.

CrossAI Intelligence remains a separate narrow Core-side semantic screening/retrieval/governance role.

The Provider Router belongs entirely on the Companion inference side.

## Relationship to existing FREE / BYOK / POWER architecture

This candidate extends the existing locked Companion provider freedom direction without changing it.

```text
FREE
BYOK
POWER
  ↓
Companion Provider Router
  ↓
approved provider/model selection
```

The routing policy may differ by mode:

- **FREE** — prefer approved free/free-tier options within truthful quota/availability/privacy constraints;
- **BYOK** — route only through providers/models authorized by the user's supplied credential and selected policy;
- **POWER** — allow stronger/paid inference when explicitly funded/authorized.

Changing mode/provider/model must not change Core conversation identity or continuity semantics.

## FREE-first principle

The future router should deliberately exploit available free capacity where useful, but must not promise free unlimited service.

Required principles:

- use an explicit CrossAI-approved model/provider allowlist;
- do not blindly delegate authority to an unrestricted/random free-model router;
- treat model/provider availability and quota as runtime facts;
- expose degraded/unavailable states truthfully;
- support safe fallback only within approved policy;
- preserve factual provider/model execution metadata when available;
- keep routing replaceable so provider churn does not require Core redesign.

## Candidate routing inputs

Future routing policy may consider:

- task class;
- language;
- required reasoning depth;
- coding capability;
- structured-output reliability;
- multimodal requirement;
- latency target;
- context-window need;
- provider/model availability;
- quota/rate-limit state;
- FREE/BYOK/POWER mode;
- privacy/data-use constraints;
- user-approved provider restrictions;
- prior measured model quality.

No single routing signal should silently redefine the user's semantic state.

## Candidate output

A routing decision should be factual and inspectable enough for debugging/provenance, for example:

```text
mode
selected_provider
selected_model
routing_reason / policy rule
fallback_used
availability/quota state
completion status
```

Exact schema remains future DESIGN.

## Failure behavior

If the preferred model/provider is unavailable:

```text
preferred candidate unavailable
        ↓
approved fallback exists?
   ├─ YES → route within policy and record fallback
   └─ NO  → truthful unavailable/degraded state
```

The router must not:

- silently fall back to a provider outside allowed privacy/policy constraints;
- claim successful inference when the provider call failed;
- mutate Core continuity because of provider failure;
- make canonical SAVE/promote decisions.

## Testing / future experiment

Before implementation lock, run a small bake-off using representative Companion workloads.

Suggested evaluation dimensions:

- Malay conversational quality;
- ordinary chat quality;
- coding usefulness;
- reasoning quality;
- structured-output reliability;
- latency;
- context handling;
- quota/free availability stability;
- provider-policy/privacy compatibility;
- fallback correctness;
- operational complexity.

The goal is not to find one permanent best model. The goal is to prove that routing can change models/providers without changing CrossAI continuity.

## Non-goals

This candidate does **not** authorize:

- changing DESIGN DRAFT 0.2;
- expanding current MVP scope;
- moving routing ownership into CrossAI Core;
- building a monolithic Intent Engine;
- making OpenRouter or any provider permanent architecture authority;
- locking current model IDs or pricing;
- creating a paid CrossAI subscription requirement;
- starting implementation.

## Review state

```text
Companion Provider Router
Status: AGREED FUTURE-WORK CANDIDATE
Implementation: NOT STARTED
Architecture lock: NO
MVP scope change: NO
DESIGN DRAFT 0.2 change: NO
```
