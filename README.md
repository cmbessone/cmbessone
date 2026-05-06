# 👋 Hi, I'm Cristian Martín Bessone

**AI Architect & Software Engineer** — I design and build scalable systems at the intersection of software architecture and artificial intelligence. My focus is on production-ready AI systems with governance, observability, and real business value baked in from the start.

I work with engineering teams and technical founders who want to move beyond AI experimentation and ship systems that are auditable, commercially defensible, and built to last.

## 🚀 What I Do

- **AI Systems Architecture** — designing governed, observable, and cost-controlled AI pipelines for production
- **Cloud-Native Engineering** — scalable backends, serverless infra, and lean SaaS products
- **AI Governance** — creator of the **GDA framework** and author of *Governed Decision Architecture* (2026)
- **Product Building** — bootstrapped micro-SaaS that solves real problems for developers, creators, and businesses

## 📍 Where I'm Headed
- 📖 Publish **Governed Decision Architecture** — my book and framework for governing AI agents in production
- Ship 5+ micro-SaaS products as bootstrapped revenue drivers
- Reach 1,000+ users across the product suite
- Establish GDA as a reference framework for teams building responsible AI systems

Connect with me:  
🌐 **Website** — https://cristianbessone.com  
🔗 **LinkedIn** — https://linkedin.com/in/cmbessone  
📧 **Email** — cristian@cmbessone.com  
🐦 **X/Twitter** — https://x.com/cmbessone

---

## 📖 Governed Decision Architecture (GDA)

> *"The most expensive thing an engineering team can do is retrofit governance into an AI system that was built without it."*

**Governed Decision Architecture** is my original framework — and upcoming book — for governing AI agents in production. It addresses one of the hardest structural problems in applied AI: how to deploy autonomous agents that are safe, auditable, cost-controlled, and policy-compliant **by design**, not as an afterthought.

### The Problem GDA Solves

Across fintech, legal, healthcare, and insurance, I kept seeing the same pattern repeat: teams prove a model works in a controlled environment, deploy it with minimal surrounding infrastructure, and then can't explain what happened when something goes wrong. The gap is never in the model. The gap is in the architecture around it.

Existing approaches — dashboards, prompt engineering, post-hoc audits — treat governance as something you layer on top of a system. GDA treats governance as an **architectural constraint** enforced at the point of decision, in real time.

### The Four-Layer Pipeline

Every AI decision that affects a user or a regulated outcome passes through a governance pipeline before it is delivered:

```
User Input
     │
     ▼
┌─────────────────┐
│  Policy Engine  │  ◄── Pre-execution validation (token limits, quotas, domain rules)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   LLM Client    │  ◄── Model abstraction layer (model-agnostic, swappable)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Risk Evaluator  │  ◄── Output scoring before delivery (domain-specific thresholds)
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Audit Service  │  ◄── Immutable record of every execution, blocked or completed
└────────┬────────┘
         │
         ▼
    Decision Output
```

Each layer has a single non-negotiable responsibility. A failure at any layer stops the pipeline. Every execution — whether it completes or is blocked — produces an audit record.

### Who the Book Is For

- The **CTO** who needs to justify AI deployment to a board that asks about liability
- The **Head of AI** who knows the model works but suspects the surrounding system is fragile
- The **Software Architect** who wants a replicable pattern they can implement from scratch
- The **Founder** building an AI product who wants to design governance in from day one — not retrofit it later

> 🛡️ **SentinelAI** is the reference implementation of GDA — a production platform built ground-up on these principles.  
> Live at: [sentinelai.cristianbessone.com](https://sentinelai.cristianbessone.com)

---

## 📂 Portfolio Monorepo

This repo is the foundation of my product ecosystem — a reusable, scalable codebase that accelerates development and encapsulates best practices.

### Features
- Templates for SaaS engines (FastAPI + Vercel + Stripe + AI)
- Reusable cloud infra (Terraform / OpenTofu)
- Agent orchestration scaffolds (CrewAI / LangGraph-ready)
- Observability + governance patterns
- CI/CD pipelines for rapid iteration

---

## 🌟 Featured Projects

| Project | Description | Tech Highlights | Status |
|---------|-------------|-----------------|--------|
| 🛡️ **SentinelAI** | Reference implementation of GDA — governed agent execution with cost and risk audit | FastAPI, Next.js, PostgreSQL, Stripe | ✅ Launched |
| 🤝 **SPO.IA** | AI-powered sponsorship connections platform — matching brands, influencers, events & programs | FastAPI, Next.js, PostgreSQL, AI Matching | 🔨 In Development |
| 📑 **Contract Lite** | Contract risk analysis with LLM summaries & actionable insights | FastAPI, Pinecone/Qdrant, Stripe | In Dev |
| 🕵️ **Fraud Signals** | Low-cost fraud detection for e-commerce | Embeddings, Vector search | Planning |
| 🎙️ **Voice Qualifier** | AI-powered call lead scoring & TTS workflows | Whisper, Vocode, Next.js | Planning |
| 🌐 **Site Auditor** | Automated SEO/Performance audit with PDF reports | Puppeteer/Lighthouse | Planning |

---

## 🤝 SPO.IA — Sponsor Connections Platform

> **Live:** [spo-ia.vercel.app](https://spo-ia.vercel.app)

SPO.IA is a platform that connects **brands** (sponsors) with **sponsorable entities** — influencers, events, and programs — through intelligent matching, commercial tracking, and a structured data model built for the sponsorship ecosystem.

### 🎯 What it solves
The sponsorship market is fragmented. Brands struggle to find the right media properties. Influencers, events and programs lack a centralized way to attract and manage sponsors. SPO.IA bridges that gap with a CRM-grade data layer and AI-driven matching.

### 🏗️ Domain Model

The platform is organized around five functional groups:

**A. Sponsoring Entities** — Brands registered per country with segmentation attributes for matching (industry, target audience, values, investment range).

**B. Sponsorable Entities** — Influencers (with audience metrics and pricing), Events (geolocation, capacity, commercial attributes), and Programs (broadcast schedules, audience profiles).

**C. Intermediary Entities** — Representatives (agencies/managers) and Operators (producers, media companies).

**D. Internal Operations** — Agents (commercial team) with role-based access control.

**E. Transversal** — Contacts as the people layer, linked to all entities via dedicated many-to-many bridge tables (`marca_contacto`, `evento_contacto`, `programa_contacto`, `operadora_contacto`, `representante_contacto`).

### 🧩 Key Design Decisions
- **Contacts as a transversal entity** — decoupled from business entities, linked via relational tables with a principal contact flag
- **Logical deletes** — all tables use soft delete (`deleted_time`, `deleted_by`) for full audit trails
- **Snapshot metrics** — social media stats stored as snapshots, historical time series planned for v2
- **Flexible intermediation** — entities can exist with or without representatives/operators
- **AI matching attributes** — every entity carries segmentation fields designed to feed a future matching engine

### 🛠️ Tech Highlights
- **Backend:** FastAPI + SQLAlchemy + PostgreSQL
- **Frontend:** Next.js 14 + TypeScript + Tailwind CSS + shadcn/ui
- **Auth:** JWT + RBAC
- **Infra:** Vercel (frontend) + Railway (backend)
- **AI Layer:** LLM-powered matching (in progress)

### 🗺️ Current Phase
Phase 1 — Master data & ABM (CRUD for all base entities). Pipeline, opportunities, campaigns, and AI matching are scoped for subsequent phases.

---

## 🛠️ Skills & Tools

### Backend & API
- Python, FastAPI, SQLAlchemy
- JWT, OAuth, RBAC
- Agent orchestration (CrewAI / LangGraph / custom)

### Frontend & UI
- Next.js 14, React, TypeScript
- Tailwind CSS, shadcn/ui, Radix

### DevOps & Infra
- AWS (ECS Fargate + Spot, Lambda, DynamoDB, CloudFront)
- Railway, Render, Fly.io
- Terraform / OpenTofu
- GitHub Actions for CI/CD

### AI/ML & Governance
- LLMs (OpenAI, Claude, Kimi)
- Vector DBs (Qdrant, Pinecone)
- Embeddings for semantic search
- GDA governance pipeline (Policy Engine, Risk Evaluator, Audit Service)

### Payments & Monetization
- Stripe Billing + Checkout + Webhooks
- Multi-tenant usage & metered plans

---

## 🛣️ Current Goals (Q1–Q4 2026)

- ✅ **SentinelAI v1** — Launched. Multi-tenant API, GDA governance pipeline, dashboard, Stripe integration
- 📖 **Governed Decision Architecture** — Book & framework. Coming 2026
- 🔨 **SPO.IA v1** — Completing master data layer, ABM, and contact relational model
- 🧰 **Voice Qualifier MVP** — In planning
- 📊 Reach product-market fit signals across 1+ SaaS

---

*Want to collaborate, discuss AI architecture, or implement GDA in your stack? Let's talk.* 🚀  
🌐 [cristianbessone.com](https://cristianbessone.com)
