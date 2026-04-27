# GTM Automation Engine

AI-powered GTM automation for lead enrichment, outreach, and reply handling in n8n.

Built as a real deliverable for an AI marketing SaaS after a single discovery call. 
Designed to activate an 8–10k contact database with zero human involvement 
until a call is booked.

---

## What This Does

A six-phase autonomous GTM engine that takes a raw contact database and turns 
it into a self-running outbound machine.

| Phase | What Happens |
|-------|-------------|
| 1 — Email Validation | HubSpot contacts pulled, deduplicated, validated via ZeroBounce |
| 2 — Enrichment | Valid contacts enriched through Clay waterfall — company size, industry, location |
| 3 — AI Outbound | Claude API writes hyper-personalized emails per contact. HubSpot sends and tracks |
| 4 — Lead Scoring | Behavioral webhooks update scores in real time — opens, clicks, replies |
| 5 — AI Reply Agent | Inbound replies classified by intent. Claude drafts contextual responses autonomously |
| 6 — Sales Handoff | Calendly booking triggers deal creation, sales briefing packet, post-call routing |

---

## Tech Stack

| Tool | Role |
|------|------|
| n8n | Orchestration layer — all logic, triggers, routing |
| Clay | Contact enrichment via 75+ data providers |
| Claude API | Email generation + reply intent classification + response drafting |
| HubSpot | CRM, email send, behavioral tracking, deal management |
| ZeroBounce | Email validation before any send |
| Calendly | Call booking, deal creation trigger |
| Slack | Sales briefing delivery + human approval gate |

---

## How Claude Sits In This System

Claude is used in exactly two places:

**Phase 3 — Email Generation**
n8n sends enriched contact profile to Claude API.
Claude returns personalized subject line + email body as JSON.
n8n sends via HubSpot Single Send API.

**Phase 5 — Reply Handling**
Call 1: Claude Haiku classifies reply intent — Interested, Objection, Not Now, Unsubscribe.
Call 2: Claude Sonnet drafts a contextual response with full thread memory.
n8n sends reply in the same email thread via HubSpot.

---

## Architecture

Full interactive architecture document in `https://69e9ba4b22f4b111473bd764--cute-rabanadas-60e838.netlify.app/`

Open in browser to explore each phase and node configuration.

---

## Three Principles That Make This Stable

1. **Claude outputs are always JSON** — enforced in the prompt. n8n parses predictably every time.
2. **HubSpot is always the master record** — nothing lives in n8n memory between executions. System survives restarts without data loss.
3. **Human gate only on ambiguous replies** — high confidence INTERESTED replies auto-send. Edge cases surface to a human via Slack.

---

## How To Use

1. Import `GTM Automation Engine.json` into your n8n instance
2. Configure credentials — HubSpot, Clay, Claude API, ZeroBounce, Calendly, Slack
3. Run Phase 1 once on your full database
4. Schedule Phase 3 weekly trigger
5. Phases 4, 5, and 6 run on webhooks automatically

---

## Demo vs Production

| | Demo | Production |
|--|------|------------|
| CRM | Google Sheets | HubSpot API |
| Email | Gmail | HubSpot Single Send API |
| Tunnel | ngrok | Cloud n8n instance |
| AI | OpenAI | Claude API |

---

## Built By

**Aakash Sethi**
Growth operator specializing in GTM systems and AI automation.

[LinkedIn](your-linkedin-url) | [Portfolio](your-portfolio-url)

