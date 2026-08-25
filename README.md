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

I don't just follow tutorials. I pick problems I actually want solved — a self-hosted AI OS that handles my WhatsApp and Gmail, a hyperlocal emergency-response network for blood and critical medicine, a RAG tool that makes any GitHub repo instantly queryable. Then I build them, break them, and figure out why.

I contribute to open source when I find something genuinely worth fixing — production ML libraries and, more recently, React Native itself. I'm currently going deep on **Rust**, **system design**, and **Linux internals** — not because they're trendy, but because understanding systems at that level makes every other layer of the stack make more sense.

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
| **LifeLine** | Hyperlocal emergency blood/critical-medicine availability network — MERN, OpenRouter-powered AI | 🟢 Active |
| **Codebase Q&A** | RAG-based tool that answers natural-language questions about any GitHub repo, with file-level citations | 🟢 Active (4-person team) |
| **METHER OS** | Self-hosted AI OS — voice, WhatsApp, Gmail, calendar, local LLM routing | 🟢 Active |

---

## Projects

### 🩸 LifeLine
> A hyperlocal emergency network connecting people in urgent need of blood or critical medicine with nearby availability — built as my flagship Kalvium end-of-term project, with a heavy system-design emphasis.

**The problem it solves:** Finding blood donors or critical medicine in an emergency is often a frantic, ad-hoc process of phone calls and WhatsApp forwards. LifeLine turns that into a structured, searchable, hyperlocal network.

**Key decisions:**
- **MERN stack**, chosen as a project constraint to keep the stack familiar while the system design does the heavy lifting
- **AI integrated via OpenRouter** rather than locking into a single vendor, keeping model choice flexible
- Built with strong architecture documentation (HLD, LLD, PRD) to hold up under an AI-conducted technical viva

[**Live →**](https://lifeline-amber-omega.vercel.app/) · [**Repo →**](https://github.com/MayankSharma-2812/Lifeline.git)

`React` `Node.js` `Express` `MongoDB` `OpenRouter`

---

### 🔍 Codebase Q&A
> Paste a GitHub repo URL, ask natural-language questions about the codebase, get answers with file-level citations — powered by a RAG pipeline built from scratch.

**The problem it solves:** Getting oriented in an unfamiliar codebase is slow. Codebase Q&A lets you interrogate a repo directly instead of manually spelunking through files.

**Architecture decisions:**
- **Manual RAG pipeline** — deliberately not using LangChain initially, to actually understand the retrieval pipeline rather than abstract it away
- **Supabase Postgres + pgvector** for the vector store, **Ollama** for local LLM + embeddings
- **Tree-sitter** planned for code-aware chunking rather than naive text splitting
- Own session + refresh-token auth implementation rather than reaching for a managed auth provider

Built with a 4-person team as a resume project: I own the RAG/embeddings/pgvector pipeline end-to-end, with teammates owning backend infra+auth and frontend.

`Next.js` `TypeScript` `Node.js` `Express` `Supabase` `pgvector` `Ollama`

---

### 🤖 METHER OS
> A self-hosted personal AI operating system. Not a wrapper around ChatGPT — a real orchestration platform running on local hardware with 14 integrated tools.

**The problem it solves:** Managing async life (messages, emails, meetings, reminders) across 5+ apps is cognitively expensive. METHER OS routes all of it through a single orchestration layer with persistent context.

**Architecture decisions:**
- **FastAPI + React 19 + asyncio + EventBus** — an event-driven core so tools can react to state changes without tight coupling
- **SecurityLevel 0/1/2 system** — tiered permissions so higher-risk agent actions (filesystem writes, sending messages) require an explicit trust level
- **Local LLM routing** — routes queries to the right model based on task type, avoiding unnecessary API costs
- **SQLite for persistent memory** — chosen over Redis because the access pattern is read-heavy and single-file backup simplicity matters for self-hosted reliability
- **Async orchestration across Python + Node.js runtimes** — Python handles ML/AI workloads (Whisper STT, Piper TTS, LLM inference), Node.js handles real-time event streams (WhatsApp bridge, WebSocket server)
- Open-sourced under `mether-os/mether-core`

**What I actually built:**
- Voice interaction pipeline: Whisper STT → LLM → Piper TTS, under 2s end-to-end on local hardware
- WhatsApp automation: reads, categorizes, and drafts responses with context from memory
- Gmail workflows: automated triage, reply drafting, label management via Google Workspace APIs
- Calendar scheduling: natural language → Google Calendar event creation
- Terminal execution and filesystem operations as agent tools

**Roadmap (v2):** replacing the current voice orb with an Iron Man-style holographic wireframe figure (cyan wireframe aesthetic).

`FastAPI` `React` `TypeScript` `Docker` `Linux` `SQLite` `WebSockets` `Whisper` `Python`

---

## Earlier / Foundational Projects

Projects from earlier in my building journey — still functional, no longer my primary focus.

### 📊 AI Dataset Quality Inspector
Statistical drift detection and ML fairness auditing platform. KS-test and PSI divergence analysis for feature shift, EEOC 4/5ths-rule fairness auditing, schema validation with type inference. Reduced manual dataset triage time by an estimated 65%; schema preview latency under 5ms with local caching.

`FastAPI` `Pandas` `SciPy` `React` `Python`

### 🔍 GitHub Repo Analyzer
Repository intelligence platform — codebase metrics, dependency graphs, language breakdowns, contributor patterns, AI-assisted summaries for any public GitHub repo.

`React` `TypeScript` `Vite` `GitHub API` `Python` · [**Live →**](https://github-repo-analyzer-by-mayank.vercel.app/)

### 🔗 LifeLink
Blockchain-based disaster relief fund tracker built under pressure at Smart India Hackathon 2025. Transparent, on-chain tracking of relief fund flow from donor to recipient. Led the team as Team Lead.

`Node.js` `Express` `Solidity` `Ethereum` `Web3.js`

### 🔥 AI Profile Roaster
Brutally honest AI career feedback on resumes and LinkedIn profiles, supporting PDF/DOCX/plain text input.

`Python` `Flask` `Groq AI`

### 🎬 Squad 124 Portfolio
Netflix-inspired team portfolio with dynamic filtering and scroll animations — vanilla HTML/CSS/JS, no frameworks.

`HTML5` `CSS3` `JavaScript`

---

## Open Source

### sktime / skpro
Contributing to production-grade probabilistic machine learning libraries used in production ML pipelines for forecasting, uncertainty quantification, and distributional prediction — currently pulling **134K+ monthly downloads**.

**Merged PRs:**

| PR | Type | Description |
|---|---|---|
| [#813](https://github.com/sktime/skpro/pull/813) | Documentation | Fixed typo in docstrings across distribution classes |
| [#833](https://github.com/sktime/skpro/pull/833) | Code quality | Fixed grammar inconsistency in validation error messages across multiple files |
| [#917](https://github.com/sktime/skpro/pull/917) | Refactoring | Eliminated duplicated feature-validation logic in CyclicBoosting |
| [#934](https://github.com/sktime/skpro/pull/934) | Bug fix | Fixed correctness bug where `SquaredDistrLoss` silently used `log_pdf` instead of `pdf` |

6+ total PRs across documentation, testing, maintenance, and logic fixes.

### React Native
- [**PR #57487**](https://github.com/facebook/react-native) — fixed a decimal-parsing bug in `transformOrigin`, merged into `react-native:main` and tagged "Shared with Meta"

### What I learned
Working in production OSS codebases with strict CI, pre-commit hooks, and maintainer review is a different discipline than solo projects. Every PR has to justify itself, pass automated checks, and survive a real code review. The bar for "good enough" is higher, and that's the point.

---

## Tech Stack

### Languages
| Language | Level | Where I use it |
|---|---|---|
| JavaScript / TypeScript | Strong | Full-stack: React frontends, Node.js services, type-safe APIs |
| Python | Strong | Backend services, ML tooling, data pipelines, automation |
| C / C++ | Comfortable | DSA, systems-level understanding, competitive context |
| Rust | Learning | Systems programming, memory safety — currently working through the ownership model |
| Solidity | Familiar | Smart contracts (LifeLink, exploratory blockchain projects) |

### Frontend
`React` `Next.js` `TypeScript` `Tailwind CSS` `Framer Motion` `GSAP` `Three.js` `HTML5` `CSS3`

### Backend
`Node.js` `Express` `FastAPI` `Flask` `REST APIs` `WebSockets` `Microservices`

### Databases & Infrastructure
`MongoDB` `PostgreSQL` `Supabase` `Redis` `SQLite` `pgvector` `Docker` `Linux`

### AI / ML Tooling
`Claude API` `LangChain` `LangGraph` `MCP` `Ollama` `OpenRouter`

### Tools & Platforms
`Git` `GitHub` `Linux` `Docker` `Vercel` `AWS` `Kubernetes` `Postman` `Kali Linux`

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
