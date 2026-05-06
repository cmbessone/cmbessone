# 👋 Hi, I'm Cristian Martín Bessone

I'm a Software Engineer with deep expertise in **AI-first backend systems**, scalable cloud-native architecture, and building real-world **micro-SaaS products powered by autonomous agents** and governance.

I'm passionate about shipping tools that help developers, creators, and small businesses automate complex workflows using modern AI responsibly — with guardrails, observability, and cost control baked in.

## 🚀 My Mission

Solving real problems with cloud-native SaaS that's:
- **Lean & cost-effective** — serverless where it makes sense, and cost-optimized infra elsewhere (Railway, ECS Spot, Lambda).
- **AI-first by design** — governed execution, risk scoring, and auditability
- **Enterprise-minded yet accessible** — clear APIs, dashboards, and UX for diverse users

I'm building a portfolio of AI-driven SaaS tools while also advancing best practices around **AI Governance**, **agent orchestration**, and **cloud backend reliability**.

## 📍 Where I'm Headed
- Ship 5+ micro-SaaS products that are bootstrapped revenue drivers
- Reach 1,000+ users across the suite
- Publish tools and frameworks that shape how teams build with GenAI responsibly

Connect with me:  
🌐 **Website** — https://cristianbessone.com  
🔗 **LinkedIn** — https://linkedin.com/in/cmbessone  
📧 **Email** — cristian@cmbessone.com  
🐦 **X/Twitter** — https://x.com/cmbessone

---

## 📂 📦 Portfolio Monorepo

This repo is the foundation of my SaaS ecosystem — a reusable, scalable codebase that accelerates development and encapsulates best practices.

### Features
- Templates for SaaS engines (FastAPI + Vercel + Stripe + AI)
- Reusable Cloud infra code (Terraform / OpenTofu)
- Agent orchestration scaffolds (CrewAI / LangGraph-ready)
- Observability + cost governance patterns
- CI/CD pipelines for rapid iteration

Whether it's a brand-new AI worker or a marketplace-ready SaaS module, this monorepo gives me a **fast runway to production**.

---

## 🌟 Featured Projects

| Project | Description | Tech Highlights | Status |
|---------|-------------|-----------------|--------|
| 🛡️ **SentinelAI** | Governed agent execution platform with cost and risk audit | FastAPI, CrewAI, Kimi, Postgres, Stripe | ✅ Launched |
| 🤝 **SPO.IA** | AI-powered sponsorship connections platform — matching brands, influencers, events & programs | FastAPI, Next.js, PostgreSQL, AI Matching | 🔨 In Development |
| 📑 **Contract Lite** | Contract risk analysis with LLM summaries & actionable insights | FastAPI, Pinecone/Qdrant, Stripe | In Dev |
| 🕵️ **Fraud Signals** | Low-cost fraud detection for e-commerce | Embeddings, Vector search | Planning |
| 🎙️ **Voice Qualifier** | AI-powered call lead scoring & TTS workflows | Whisper, Vocode, Next.js | Planning |
| 🌐 **Site Auditor** | Automated SEO/Performance audit with PDF reports | Puppeteer/Lighthouse | Planning |

> More products and experimental agents landing soon.

---

## 🤝 SPO.IA — Sponsor Connections Platform

> **Live:** [spo-ia.vercel.app](https://spo-ia.vercel.app)

SPO.IA is an AI-powered platform that connects **brands** (sponsors) with **sponsorable entities** — influencers, events, and programs — through intelligent matching, commercial tracking, and a structured data model built for the sponsorship ecosystem.

### 🎯 What it solves
The sponsorship market is fragmented. Brands struggle to find the right media properties. Influencers, events and programs lack a centralized way to attract and manage sponsors. SPO.IA bridges that gap with a CRM-grade data layer and AI-driven matching.

### 🏗️ Domain Model

The platform is organized around five functional groups:

**A. Sponsoring Entities**
- **Brands** — companies that invest in sponsorships, registered per country with segmentation attributes for matching (industry, target audience, values, investment range).

**B. Sponsorable Entities**
- **Influencers** — content creators with audience metrics, pricing ranges, and content categorization.
- **Events** — one-off or recurring events that need sponsors, with geolocation, capacity, and commercial attributes.
- **Programs** — media programs (TV, digital, podcast) seeking sponsorship, with broadcast schedules and audience profiles.

**C. Intermediary Entities**
- **Representatives** — agencies and managers that represent brands or influencers commercially.
- **Operators** — producers and media companies that manage events and programs.

**D. Internal Operations**
- **Agents** — internal commercial team members with role-based access.
- **Roles** — permission and access control layer for agents.

**E. Transversal**
- **Contacts** — the people layer. Every entity has associated contacts, managed via relational bridge tables (`marca_contacto`, `evento_contacto`, `programa_contacto`, `operadora_contacto`, `representante_contacto`), supporting many-to-many relationships with a principal contact flag.

### 🧩 Key Design Decisions
- **Contacts as a transversal entity** — decoupled from business entities, linked via dedicated relational tables to support many-to-many associations.
- **Logical deletes** — all tables use soft delete (`deleted_time`, `deleted_by`) for full audit trails.
- **Snapshot metrics** — social media stats (followers, engagement per network) are stored as snapshots, not historical time series (planned for v2).
- **Flexible intermediation** — influencers, events, and programs can exist with or without a representative/operator, supporting both direct and mediated commercial flows.
- **AI matching attributes** — every sponsorable and sponsoring entity carries segmentation fields (`industry`, `target_audience`, `values`, `spo_group`, `spo_category`, `spo_subcategory`) designed to feed a future matching engine.

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
- Autonomous agent orchestration (CrewAI / LangGraph / custom)

### Frontend & UI
- Next.js 14
- React, TypeScript
- Tailwind CSS, shadcn/ui, Radix

### DevOps & Infra
- AWS (ECS Fargate + Spot, Lambda, Dynamo, CloudFront)
- Railway, Render, Fly.io for cost-efficient backend hosting
- Terraform / OpenTofu
- Github Actions for CI/CD

### AI/ML
- LLMs (Kimi, OpenAI, Claude)
- Vector DBs (Qdrant, Pinecone)
- Embeddings for semantic search
- Governance & audit patterns

### Payments & Monetization
- Stripe Billing + Checkout + Webhooks
- Multi-tenant usage & metered plans

---

## 📈 Principles I Follow

### 🧠 Responsible AI
Every platform I build incorporates:
- **Governance layers** (input constraints, execution budgets)
- **Output evaluation** (risk scoring, red-flag detectors)
- **Audit trails** (structured logs, traceability)
- **Human review triggers** when thresholds are exceeded

This is how AI can be **safe, accountable, and business-ready.**

### ⚡ Developer Experience First
- Monorepo standards
- Reusable templates
- CLI tools & generators
- AI-assisted scaffolding

### 💸 Cost-aware Design
- Serverless + spot infrastructure
- Budget caps on AI usage
- Transparent metrics for users and maintainers

---

## 🛣️ Current Goals (Q1–Q4 2026)

- ✅ **SentinelAI v1** — Launched with multi-tenant API, dashboard, cost center views, and Stripe integration
- 🔨 **SPO.IA v1** — Completing master data layer, ABM, and contact relational model
- 🧰 Ship **Voice Qualifier MVP**
- 📣 Publish content on AI Governance patterns
- 📊 Reach product-market fit signals across 1+ SaaS

---

*Want to collaborate, learn together, or build something game-changing? Let's talk.* 🚀  
🌐 [cristianbessone.com](https://cristianbessone.com)
