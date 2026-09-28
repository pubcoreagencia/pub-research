# PUB Research — Instagram Research → Autonomous Intelligence Master Context

**Status:** Canonical product/architecture context  
**Date:** 2026-09-28  
**Repository:** `pubcoreagencia/pub-research`

## 1. Vision

PUB Research is the research ingestion and intelligence layer for the PUB ecosystem.

The immediate human workflow is intentionally simple:

1. Matheus researches content on Instagram.
2. When a post is worth preserving, he shares/sends that post to a dedicated Instagram group.
3. A connected, logged-in browser session monitors that group.
4. The system identifies the shared Instagram post URL and opens it using the authenticated browser session.
5. The system extracts the maximum amount of accessible information from the post.
6. The complete research artifact is persisted in PUB Research.
7. PUB Research becomes upstream intelligence for PUB Neural.
8. PUB Neural can feed PP and PDL.
9. Research findings can eventually produce qualified suggestions, analysis, implementation candidates, and autonomous development work.

The key UX principle is:

> **Research should require almost no manual work beyond sharing the interesting post.**

## 2. Why an authenticated browser is part of the design

Instagram's web experience can impose login walls and other access restrictions. Current research confirms that logged-out access to public Instagram content is limited and inconsistent; direct public post URLs may sometimes expose a limited view, but a logged-in browser is the reliable baseline for the intended workflow.

The architecture therefore assumes:

- a real Instagram account;
- an authenticated browser profile/session;
- the browser is the access layer for Instagram;
- the research system does not assume that an unauthenticated HTTP request can retrieve the complete post;
- the browser must only access content that the connected account is legitimately able to view.

Meta describes scraping as automated collection of data from its websites/interfaces and distinguishes authorized from unauthorized scraping. Instagram's Community Guidelines also require respect for applicable law and intellectual-property rights. The implementation must therefore preserve account/session security, respect access boundaries and platform constraints, and avoid bypassing authentication or access controls.

## 3. Extraction principle: treat every Instagram post as multimodal

A shared URL is not merely a text page.

The extractor must classify the post and attempt to capture every accessible layer.

### Post-level metadata

- canonical Instagram URL
- post/reel identifier when available
- username / author
- profile URL
- timestamp/date when accessible
- post type
- caption
- hashtags
- mentions
- visible engagement metadata when accessible
- external links present in the accessible content
- source/account context

### Media

Support all accessible post formats:

- single image
- multiple-image carousel
- single video
- video/reel
- mixed/compound media when encountered
- thumbnails/previews
- accessible media URLs
- media ordering
- media dimensions/duration when available

### Image intelligence

For every accessible image:

- preserve original/accessible media
- OCR
- text blocks
- visual description
- objects/products
- people/entities only as non-sensitive contextual description
- screenshots and UI text
- charts/diagrams
- offers/prices visible in the image
- CTA
- branding
- design patterns
- layout/copy structure

### Video intelligence

For every accessible video:

- preserve accessible source/media reference
- duration
- audio track when accessible
- speech transcription
- on-screen text OCR
- scene/segment descriptions
- hooks
- CTA
- product/service information
- notable visual and audio events

### Carousel intelligence

A carousel is a first-class research object.

The system must:

- enumerate all slides;
- preserve their order;
- extract OCR independently from each slide;
- analyze each slide visually;
- identify the narrative progression;
- produce a combined carousel summary;
- identify the hook, development, proof, offer and CTA when present.

## 4. Research artifact model

A research item should preserve both **raw evidence** and **derived intelligence**.

Conceptually:

```
Research Item
├── source
├── access/session metadata
├── original URL
├── raw post metadata
├── raw media references
├── extracted text
├── OCR
├── transcription
├── visual analysis
├── semantic analysis
├── entities
├── topics
├── products
├── brands
├── claims
├── offers
├── hooks
├── CTAs
├── provenance
├── qualification
├── suggestions
├── implementation candidates
└── downstream events
```

Raw evidence must remain distinguishable from AI-generated interpretation.

## 5. Provenance and auditability

Every derived insight must be traceable to its source material.

Minimum provenance chain:

```
Instagram URL
   ↓
Browser capture
   ↓
Captured media/text
   ↓
OCR/transcription
   ↓
AI analysis
   ↓
Research qualification
   ↓
Suggestion
   ↓
Potential implementation
   ↓
PUB Neural / PP / PDL
```

The system should preserve:

- source URL;
- capture timestamp;
- extraction method;
- browser/session context identifier without storing credentials;
- media references;
- extraction status;
- analysis model/provider;
- analysis timestamp;
- confidence/quality indicators where useful;
- links between source evidence and derived conclusions.

Credentials, cookies, session tokens and other secrets must never be stored in the research artifact.

## 6. Ecosystem-wide intelligence

PUB Research is not downstream only to PP or PDL.

Its intended role is to provide research intelligence to the **entire PUB ecosystem**.

Research may generate useful knowledge, opportunities, decisions, patterns, references, product ideas, operational improvements, competitive intelligence, technical discoveries and implementation candidates for any relevant PUB initiative, including but not limited to:

- PUB Neural
- PP / Prototype
- PDL / Dev Loop
- PUB Ecom
- PUB Leads
- PUB IA / AI infrastructure
- PUB ACP
- PUB 9Router
- PUB Machine
- PUB Records / audio initiatives
- holding brands and future businesses
- shared infrastructure and governance
- new products, brands and ventures created by the holding

The relationship is therefore:

```
                         PUB RESEARCH
                              │
              ┌───────────────┼────────────────┐
              │               │                │
              ▼               ▼                ▼
          PUB Neural      Ecosystem       Holding
              │               │            Intelligence
              │               │
       ┌──────┴──────┐   ┌────┴────────────────────────────┐
       ▼             ▼   ▼             ▼          ▼         ▼
      PP            PDL  Ecom         Leads      IA       ACP
       │             │
       └─────────────┴─────────── ... ────────────┐
                                                   ▼
                                           New PUB ventures
```

PUB Research is therefore an **ecosystem intelligence layer**, not merely a feed for product development.

## 7. Human research → autonomous research

The initial product is human-triggered:

```
Human finds something interesting
        ↓
Share to Instagram group
        ↓
Automatic ingestion
```

The long-term system expands this into autonomous research:

```
                    ┌──────────────────────┐
                    │ Human Research       │
                    │ Instagram Group      │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │ PUB Research         │
                    │ Ingestion + Analysis │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │ PUB Neural           │
                    │ Institutional memory │
                    └──────────┬───────────┘
                               │
               ┌───────────────┼────────────────┐
               │               │                │
        ┌──────▼─────┐  ┌──────▼─────┐  ┌──────▼─────┐
        │ PP         │  │ PDL        │  │ Future     │
        │ Prototype  │  │ Development│  │ Research   │
        └────────────┘  └────────────┘  └────────────┘
```

Future autonomous research should operate continuously across topics relevant to the holding:

- products;
- brands;
- competitors;
- technologies;
- markets;
- customer problems;
- content patterns;
- business models;
- opportunities;
- emerging tools;
- product ideas;
- operational improvements;
- research questions generated by previous research.

The target is an eventual **24/7 research capability**, not merely a scraper.

## 7. Research qualification pipeline

The intelligence layer should progressively qualify discoveries.

Suggested conceptual stages:

```
DISCOVER
   ↓
CAPTURE
   ↓
EXTRACT
   ↓
ANALYZE
   ↓
QUALIFY
   ↓
SUGGEST
   ↓
VALIDATE
   ↓
IMPLEMENTATION CANDIDATE
   ↓
AUTHORIZE
   ↓
IMPLEMENT
   ↓
OBSERVE RESULT
   ↓
LEARN
```

Important distinction:

**Research does not automatically become code.**

Research produces evidence and candidates. Downstream governance decides what is eligible for implementation.

## 8. Feedback loop

Implemented results should eventually feed back into research.

```
Research
   ↓
Suggestion
   ↓
Implementation
   ↓
Production result
   ↓
Observed outcome
   ↓
New research signal
   ↓
Research
```

This creates a learning loop in which PUB Research is not a static archive.

## 9. Relationship with PUB Neural

PUB Research is the ingestion/research intelligence layer.

PUB Neural is the institutional memory/knowledge layer.

A useful conceptual separation is:

- **PUB Research:** discovers, captures, extracts, analyzes and qualifies external/internal research.
- **PUB Neural:** persists authoritative institutional knowledge, provenance, decisions and reusable context.
- **PP:** prototypes ideas/products.
- **PDL:** executes governed product-development work.

Research should not silently mutate institutional truth. Derived knowledge should enter PUB Neural through explicit, traceable events/decisions.

## 10. Relationship with ACP

ACP is infrastructure for agent communication/execution and remains separate from the PUB product pipeline.

ACP may eventually be used by autonomous research agents to execute browser-based research or coordinate tools, but:

> **ACP is not PUB Research and PUB Research is not PDL.**

The separation must remain explicit.

## 11. Browser architecture

The first implementation should use a persistent authenticated browser profile.

Conceptually:

```
Instagram account
      ↓
Persistent browser profile
      ↓
Instagram web session
      ↓
Group monitoring
      ↓
Shared post URL detected
      ↓
Open URL in same authenticated browser
      ↓
Extract accessible DOM/media
      ↓
Capture media
      ↓
OCR/transcription/multimodal analysis
```

The browser is the access boundary. Do not copy authentication cookies or credentials into application storage.

A browser worker should expose a narrow research interface rather than exposing the entire authenticated session to arbitrary agents.

## 12. Group ingestion

The dedicated Instagram group is the human-to-machine intake channel.

The system should eventually recognize:

- newly shared post URLs;
- sender;
- timestamp;
- message context;
- duplicate URLs;
- retry state;
- extraction state;
- analysis state.

A future enhancement can classify why the human shared an item based on the accompanying message, while keeping that interpretation separate from the source evidence.

## 13. Idempotency

The same Instagram post may be shared multiple times.

The ingestion system should deduplicate by stable source identifiers where available, with URL normalization as a fallback.

Expected behavior:

```
same source
   ↓
existing research item
   ↓
update provenance / new observation
   ↓
do not create uncontrolled duplicates
```

## 14. Failure handling

Instagram changes frequently. Extraction must be observable and resumable.

A research item should be able to report states such as:

- RECEIVED
- OPENING
- CAPTURED
- EXTRACTING
- ANALYZING
- QUALIFYING
- COMPLETED
- PARTIAL
- BLOCKED
- FAILED
- RETRYING

A partial result is preferable to silently losing the research.

## 15. Security boundaries

The system must never persist:

- Instagram password;
- browser cookies;
- session tokens;
- authentication headers;
- private account credentials;
- unrelated private messages.

It should persist only the minimum session reference necessary to identify the browser worker/profile responsible for a capture.

The research system must respect the permissions of the connected account. It is not intended to bypass private-account restrictions, CAPTCHAs, login challenges, rate limits, or other access controls.

## 16. Product principle

The product should feel like:

> **"I found something interesting. I share it. PUB Research takes care of the rest."**

Not:

> "I found something interesting and now I have to manually download, transcribe, categorize, summarize and document it."

That simplicity is the core UX requirement.

## 17. Long-term autonomous research

The future 24/7 system should maintain research missions.

Example conceptual mission:

```
MISSION
"Monitor AI agent infrastructure relevant to PUB."

SOURCES
Instagram
Web
GitHub
YouTube
Communities
Product launches
Research papers
Other approved sources

SCHEDULE
Continuous / periodic

PIPELINE
discover → capture → extract → analyze → qualify

OUTPUT
new knowledge
patterns
opportunities
candidate features
candidate products
questions for human review
```

Research agents should be able to spawn follow-up research questions from previous findings, while preserving provenance and governance.

## 18. Governance principle

Autonomy increases execution capacity; it does not remove sovereignty.

The intended hierarchy is:

```
Evidence
  ↓
Research
  ↓
Qualification
  ↓
Suggestion
  ↓
Human / governed authorization
  ↓
Implementation
  ↓
Validation
```

Over time, specific classes of low-risk work may receive pre-authorized autonomous execution policies, but those policies must be explicit and auditable.

## 19. Immediate MVP

The smallest useful version is:

1. authenticated Instagram browser profile;
2. dedicated Instagram research group;
3. group monitor;
4. URL detector;
5. authenticated post opener;
6. media/DOM extractor;
7. image/video/carousel classifier;
8. OCR;
9. video transcription;
10. multimodal analysis;
11. research record persistence;
12. provenance;
13. simple research dashboard/API.

Do not start with the 24/7 autonomous system.

First prove:

```
share post
   ↓
automatic capture
   ↓
complete multimodal extraction
   ↓
persistent research record
```

Then build the autonomous layer on top of a proven ingestion foundation.

## 20. Research repository role

`pubcoreagencia/pub-research` is the canonical repository for the architecture, decisions, research extraction patterns, evaluations, benchmarks and implementation context of this capability.

This document is the master context for the Instagram Research → PUB Research → PUB Neural → PP/PDL concept discussed on 2026-09-28.

Future implementation work must update this context when architecture, constraints, extraction strategy, governance or downstream contracts materially change.

---

## Sources checked for the login/access premise

- Meta's public documentation describes scraping as automated collection of website/interface data and notes that unauthorized scraping can violate platform terms. 
- Current web research indicates that logged-out Instagram access to public content is limited/inconsistent and that authenticated browser access is the practical baseline when the goal is reliable access to the content visible to a logged-in account.
- This architecture therefore treats the authenticated browser as a first-class access layer rather than assuming anonymous HTTP access.

**Important:** This document describes the intended architecture and does not assert that every Instagram post or every media URL will always be technically extractable. Extraction capability must be validated against real Instagram behavior during implementation.
