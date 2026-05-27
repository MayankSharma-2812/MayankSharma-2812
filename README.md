<div align="center">

# Mayank Sharma

**Full-Stack Engineer · Backend Systems · Open Source**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/mayank-sharma-7b277b312)
[![Email](https://img.shields.io/badge/Email-msharma.dev.in@gmail.com-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:msharma.dev.in@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-MayankSharma--2812-100000?style=flat-square&logo=github&logoColor=white)](https://github.com/MayankSharma-2812)
[![Portfolio](https://img.shields.io/badge/Portfolio-Live-667eea?style=flat-square)](https://github.com/MayankSharma-2812)

B.Tech CSE (Kalvium × JECRC) · Jaipur, India · Open to internships in backend / full-stack engineering

</div>

---

## About

I'm a full-stack engineer who builds things end-to-end — from FastAPI backends and React dashboards to Docker-based infrastructure and LLM pipelines. My focus is on **developer tooling**, **AI-integrated systems**, and **backend architecture that holds up under real conditions**.

I don't just follow tutorials. I pick problems I actually want solved — a self-hosted AI OS that handles my WhatsApp and Gmail, an ML dataset validator that catches bias before deployment, a GitHub intelligence platform that makes codebases readable at a glance. Then I build them, break them, and figure out why.

I contribute to open source when I find something genuinely worth fixing. I'm currently going deep on **Rust**, **system design**, and **Linux internals** — not because they're trendy, but because understanding systems at that level makes every other layer of the stack make more sense.

---

## Engineering Philosophy

> *"Understand the system one layer below the one you're working in."*

A few things I actually believe after building real projects:

- **Correctness before cleverness.** A system that does the right thing slowly is better than a fast one that's subtly wrong. I learned this fixing a loss computation bug in skpro where `log_pdf` was silently used instead of `pdf` — the code ran fine, but every result was wrong.
- **Abstractions should earn their complexity.** Every layer of indirection has a cost. I build the simplest thing that handles the real constraint, then add abstraction when the problem demands it.
- **Local-first where possible.** METHER OS is self-hosted by design — I wanted to understand what it actually takes to run AI infrastructure on your own hardware, not just call an API.
- **Docs and error messages are code.** A confusing error message is a bug. Fixing grammar in skpro's validation messages wasn't pedantic — it's what users actually read when things break.
- **Metrics over intuition.** The 65% triage reduction in Dataset Inspector wasn't a guess. I measured it. If you can't measure it, you don't know if it worked.

---

## What I'm Building Now

| Project | What it does | Status |
|---|---|---|
| **METHER OS** | Self-hosted AI OS — voice, WhatsApp, Gmail, calendar, local LLM routing | 🟢 Active |
| **AI Dataset Quality Inspector** | Statistical drift detection and ML fairness auditing platform | 🟢 Active |
| **GitHub Repo Analyzer** | Repository intelligence — metrics, dependency analysis, AI summaries | 🟡 Maintaining |

---

## Projects

### 🤖 METHER OS
> A self-hosted personal AI operating system. Not a wrapper around ChatGPT — a real orchestration platform running on local hardware with 14 integrated tools.

**The problem it solves:** Managing async life (messages, emails, meetings, reminders) across 5+ apps is cognitively expensive. METHER OS routes all of it through a single orchestration layer with persistent context.

**Architecture decisions:**
- **Monorepo structure** — 14 agent tools, FastAPI core, React dashboard, voice sidecar, WhatsApp bridge, all sharing typed interfaces. Made it painful to set up, but made cross-service orchestration trivial.
- **Local LLM routing** — Routes queries to the right model based on task type (fast local model for quick lookups, larger model for complex reasoning). Avoids unnecessary API costs.
- **SQLite for persistent memory** — Chose SQLite over Redis for memory persistence because the access pattern is mostly read-heavy and the simplicity of a single file backup matters for self-hosted reliability.
- **Async orchestration across Python + Node.js runtimes** — Python handles ML/AI workloads (Whisper STT, Piper TTS, LLM inference), Node.js handles real-time event streams (WhatsApp bridge, WebSocket server). FastAPI acts as the coordination layer.

**What I actually built:**
- Voice interaction pipeline: Whisper STT → LLM → Piper TTS, under 2s end-to-end on local hardware
- WhatsApp automation: reads, categorizes, and drafts responses with context from memory
- Gmail workflows: automated triage, reply drafting, label management via Google Workspace APIs
- Calendar scheduling: natural language → Google Calendar event creation
- Terminal execution and filesystem operations as agent tools

`FastAPI` `React` `TypeScript` `Docker` `Linux` `SQLite` `WebSockets` `Whisper` `Python`

---

### 📊 AI Dataset Quality Inspector
> A dataset validation platform that catches problems before they reach model training.

**The problem it solves:** ML engineers waste hours manually checking datasets for drift, bias, and schema inconsistencies. This platform automates that triage with research-backed statistical methods.

**Architecture decisions:**
- **FastAPI backend with async validation workers** — each statistical check runs as an independent async task, so a slow KS-test doesn't block the schema preview
- **Local caching layer** — caches schema previews and validation results per dataset hash, reducing repeated validation runs on unchanged data
- **Modular check pipeline** — each validator (drift, fairness, missing values, schema, distribution) is a pluggable module. Adding a new check doesn't touch existing validation logic.

**Statistical methods implemented:**
- KS-test for distribution drift detection between train/test splits
- PSI (Population Stability Index) divergence analysis for feature shift
- EEOC 4/5ths-rule validation for fairness auditing across demographic groups
- Schema validation with type inference and null pattern detection

**Results:**
- Reduced manual dataset triage time by an estimated **65%**
- Expanded automated checks from 2 → **5 statistical validators**
- Schema preview latency: **< 5ms** with local caching

`FastAPI` `Pandas` `SciPy` `React` `Python`

---

### 🔍 GitHub Repo Analyzer
> Repository intelligence platform. Makes unfamiliar codebases readable in seconds.

**What it does:** Takes any public GitHub repo and generates codebase metrics, dependency graphs, language breakdowns, contributor patterns, and AI-assisted summaries. Built for the moment you're dropped into an unknown codebase and need orientation fast.

**Technical decisions:**
- Local caching of repository metadata to avoid GitHub API rate limits on repeated analysis
- History restoration workflows so interrupted analysis sessions resume without re-fetching
- AI summary pipeline that synthesizes README, file structure, and dependency manifest into a plain-English project summary

`React` `TypeScript` `Vite` `GitHub API` `Python`

[**Live →**](https://github-repo-analyzer-by-mayank.vercel.app/)

---

### 🔗 LifeLink
> Blockchain-based disaster relief fund tracker. Built under pressure at Smart India Hackathon 2025.

Transparent, tamper-proof tracking of disaster relief fund flow from donor to recipient using Ethereum smart contracts. Every allocation is on-chain — no black boxes, no manual reconciliation.

- Smart contract integration for immutable fund tracking
- Real-time monitoring dashboard for relief coordinators
- Led the team as Team Lead: coordinated frontend/backend split, task distribution, and evaluation presentation

`Node.js` `Express` `Solidity` `Ethereum` `Web3.js`

---

### 🔥 AI Profile Roaster
> Brutally honest career feedback from AI. Analyzes resumes and LinkedIn profiles.

Built with Python, Flask, and Groq AI. Supports PDF, DOCX, and plain text input. Generates specific, actionable feedback rather than generic praise.

`Python` `Flask` `Groq AI`

---

### 🎬 Squad 124 Portfolio
> Netflix-inspired team portfolio with dynamic filtering and scroll animations.

Built purely with HTML, CSS, and vanilla JavaScript — no frameworks. An exercise in understanding what React actually saves you from.

`HTML5` `CSS3` `JavaScript`

---

## Open Source — sktime / skpro

> Contributing to production-grade probabilistic machine learning libraries used by researchers and engineers worldwide.

### What skpro is
skpro is part of the sktime ecosystem — a Python framework for probabilistic supervised regression and distribution models. It's used in production ML pipelines for forecasting, uncertainty quantification, and distributional prediction.

### My contributions

**Merged PRs:**

| PR | Type | Description |
|---|---|---|
| [#813](https://github.com/sktime/skpro/pull/813) | Documentation | Fixed typo in docstrings across distribution classes: `"logartihms"` → `"logarithms"` |
| [#833](https://github.com/sktime/skpro/pull/833) | Code quality | Fixed grammar inconsistency in validation error messages: `"needs to be"` → `"must be"` across multiple files |
| [#917](https://github.com/sktime/skpro/pull/917) | Refactoring | Eliminated duplicated feature-validation logic in CyclicBoosting — single source of truth for validation rules |
| [#934](https://github.com/sktime/skpro/pull/934) | Bug fix | Identified and fixed correctness bug: `SquaredDistrLoss` was using `log_pdf` instead of `pdf` in loss computation — values were computed without error but were mathematically incorrect |

**Additional contributions:**
- Improved typing and documentation consistency in utility functions
- Reported additional bugs during code review with reproduction steps
- 6+ total PRs across documentation, testing, maintenance, and logic fixes

### What I learned
Working in a production OSS codebase with strict CI, pre-commit hooks, and maintainer review is a different discipline than solo projects. Every PR has to justify itself, pass automated checks, and survive a real code review. The bar for "good enough" is higher, and that's the point.

---

## Tech Stack

### Languages
| Language | Level | Where I use it |
|---|---|---|
| JavaScript / TypeScript | Strong | Full-stack: React frontends, Node.js services, type-safe APIs |
| Python | Strong | Backend services, ML tooling, data pipelines, automation |
| C / C++ | Comfortable | DSA, systems-level understanding, competitive context |
| Rust | Learning | Systems programming, memory safety — currently working through ownership model |
| Solidity | Familiar | Smart contracts (LifeLink, exploratory blockchain projects) |

### Frontend
`React` `Next.js` `TypeScript` `Tailwind CSS` `Framer Motion` `GSAP` `Three.js` `HTML5` `CSS3`

Comfortable building production UIs. Not just styling — state management, performance optimization, accessibility, component architecture.

### Backend
`Node.js` `Express` `FastAPI` `Flask` `REST APIs` `WebSockets` `Microservices`

Most of my serious work lives here. I care about API design, async patterns, error handling, and building backends that other systems can rely on.

### Databases & Infrastructure
`MongoDB` `PostgreSQL` `Redis` `SQLite` `Docker` `Linux`

I understand the tradeoffs between these. SQLite when you want reliability and simplicity. PostgreSQL when you need relational guarantees. Redis when you need sub-millisecond reads. MongoDB when your data is genuinely document-shaped.

### Tools & Platforms
`Git` `GitHub` `Linux` `Docker` `Vercel` `AWS` `Kubernetes` `Postman` `Kali Linux`

### Security & Systems
Basic penetration testing and WiFi security analysis using Kali Linux. Not a security engineer — but I know enough to not build obviously exploitable systems.

---

## Currently Learning

```
Rust
├── Ownership & borrowing model (in progress)
├── Systems programming patterns
└── Goal: write a small CLI tool from scratch in Rust

System Design
├── Distributed systems fundamentals (CAP theorem, consistency models)
├── Database internals (indexing, query planning, storage engines)
└── Goal: be able to design and critique any system at an interview level

Linux Internals
├── Process management, file descriptors, signals
├── Networking stack (how TCP/IP actually works beneath the socket API)
└── Goal: understand what Docker is actually doing under the hood

AWS Architecture
├── EC2, S3, Lambda, RDS — practical usage
├── VPC networking and IAM patterns
└── Goal: deploy METHER OS to a cloud instance with proper infra
```

**Why these four:** Rust and Linux internals are about understanding the layer below what I work in every day. System design is about being able to reason about scale before I build the thing that needs to scale. AWS is just practical — self-hosting is great for learning, but real products live in the cloud.

---

## GitHub Activity

<div align="center">

<img src="https://github-readme-streak-stats.herokuapp.com/?user=MayankSharma-2812&theme=tokyonight&hide_border=true&border_radius=8" width="48%" />
<img src="https://github-readme-stats.vercel.app/api?username=MayankSharma-2812&show_icons=true&theme=tokyonight&hide_border=true&border_radius=8&count_private=true" width="48%" />

<br/><br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=MayankSharma-2812&theme=tokyo-night&hide_border=true" width="95%"/>

</div>

---

## Background

**Education**
- B.Tech CSE (Software Product Engineering) · Kalvium × JECRC University · Expected 2029
- Focus: full-stack development, backend systems, AI-integrated applications, scalable software engineering

**Achievements**
- 🏆 **IT Wizard Award** — Annual Day 2025, Vidya Niketan Birla Public School — for excellence in computer science
- 🥇 **Best Website Creator** — 2024, school recognition for web development and design projects
- 🥈 **2nd rank in Web Development** — IPSC IT Fest 2025
- 🎯 **5th rank in Video Editing** — IPSC IT Fest 2025

**Leadership**
- **Team Lead, Smart India Hackathon 2025** — Led multidisciplinary team through problem definition, technical architecture, frontend/backend split, and evaluation presentation

---

## What I'm Looking For

I'm open to **internships** in:
- Backend engineering (Python, Node.js, distributed systems)
- Full-stack development (React + any serious backend)
- Developer tooling or AI infrastructure

I work well in teams that move fast, have high standards for code quality, and aren't afraid to go deep on hard problems. I'm not looking for a place to coast — I want to work on things that are actually difficult.

---

<div align="center">

**Let's build something worth building.**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/mayank-sharma-7b277b312)
[![Email](https://img.shields.io/badge/Email-Reach%20out-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:msharma.dev.in@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-100000?style=flat-square&logo=github&logoColor=white)](https://github.com/MayankSharma-2812)

</div>
