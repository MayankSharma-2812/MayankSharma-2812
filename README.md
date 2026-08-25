<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=28&pause=1000&color=667EEA&center=true&vCenter=true&width=600&lines=Full-Stack+Engineer;Backend+Systems+%26+Open+Source;Building+things+that+actually+work" alt="Typing SVG" />

# Mayank Sharma

<p>
<a href="https://linkedin.com/in/mayank-sharma-7b277b312"><img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="mailto:msharma.dev.in@gmail.com"><img src="https://img.shields.io/badge/Email-Reach%20Out-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
<a href="https://github.com/MayankSharma-2812"><img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
</p>

<p>
<img src="https://img.shields.io/badge/B.Tech_CSE-Kalvium_×_JECRC-667EEA?style=flat-square" />
<img src="https://img.shields.io/badge/Based_in-Jaipur,_India-orange?style=flat-square" />
<img src="https://img.shields.io/badge/Open_to-Internships-brightgreen?style=flat-square" />
</p>

</div>

<br/>

<div align="center">

**[About](#about)** · **[Philosophy](#engineering-philosophy)** · **[Current Projects](#-what-im-building-now)** · **[Open Source](#-open-source)** · **[Stack](#-tech-stack)** · **[Learning](#-currently-learning)**

</div>

<br/>

## About

I'm a full-stack engineer who builds things end-to-end — from FastAPI backends and React dashboards to Docker-based infrastructure and LLM pipelines. My focus is on **developer tooling**, **AI-integrated systems**, and **backend architecture that holds up under real conditions**.

I don't just follow tutorials. I pick problems I actually want solved — a self-hosted AI OS that handles my WhatsApp and Gmail, a hyperlocal emergency-response network for blood and critical medicine, a RAG tool that makes any GitHub repo instantly queryable. Then I build them, break them, and figure out why.

I contribute to open source when I find something genuinely worth fixing — production ML libraries and, more recently, React Native itself. I'm currently going deep on **Rust**, **system design**, and **Linux internals** — not because they're trendy, but because understanding systems at that level makes every other layer of the stack make more sense.

<br/>

## Engineering Philosophy

> *"Understand the system one layer below the one you're working in."*

| Principle | What it means in practice |
|---|---|
| **Correctness before cleverness** | Fixed a loss computation bug in skpro where `log_pdf` was silently used instead of `pdf` — the code ran fine, but every result was wrong |
| **Abstractions earn their complexity** | Build the simplest thing that handles the real constraint, then add abstraction when the problem demands it |
| **Local-first where possible** | METHER OS is self-hosted by design — understanding what it takes to run AI infra on your own hardware, not just call an API |
| **Docs and error messages are code** | Fixing grammar in skpro's validation messages wasn't pedantic — it's what users actually read when things break |
| **Metrics over intuition** | The 65% triage reduction in Dataset Inspector wasn't a guess — it was measured |

<br/>

## 🚀 What I'm Building Now

| Project | What it does | Status |
|---|---|---|
| 🩸 **LifeLine** | Hyperlocal emergency blood/critical-medicine availability network — MERN, OpenRouter-powered AI | ![Active](https://img.shields.io/badge/-Active-brightgreen?style=flat-square) |
| 🔍 **Codebase Q&A** | RAG-based tool answering natural-language questions about any GitHub repo, with file-level citations | ![Active](https://img.shields.io/badge/-Active_%7C_4--person_team-brightgreen?style=flat-square) |
| 🤖 **METHER OS** | Self-hosted AI OS — voice, WhatsApp, Gmail, calendar, local LLM routing | ![Active](https://img.shields.io/badge/-Active-brightgreen?style=flat-square) |

<br/>

### 🩸 LifeLine

> A hyperlocal emergency network connecting people in urgent need of blood or critical medicine with nearby availability — built as my flagship Kalvium end-of-term project, with a heavy system-design emphasis.

**The problem it solves:** Finding blood donors or critical medicine in an emergency is often a frantic, ad-hoc process of phone calls and WhatsApp forwards. LifeLine turns that into a structured, searchable, hyperlocal network.

**Key decisions:**
- **MERN stack**, chosen as a project constraint to keep the stack familiar while the system design does the heavy lifting
- **AI integrated via OpenRouter** rather than locking into a single vendor, keeping model choice flexible
- Built with strong architecture documentation (HLD, LLD, PRD) to hold up under an AI-conducted technical viva

<p>
<a href="https://lifeline-amber-omega.vercel.app/"><img src="https://img.shields.io/badge/Live_Demo-000000?style=flat-square&logo=vercel&logoColor=white" /></a>
<a href="https://github.com/MayankSharma-2812/Lifeline"><img src="https://img.shields.io/badge/Repo-181717?style=flat-square&logo=github&logoColor=white" /></a>
</p>
<p>
<img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/OpenRouter-8A2BE2?style=flat-square" />
</p>

<br/>

### 🔍 Codebase Q&A

> Paste a GitHub repo URL, ask natural-language questions about the codebase, get answers with file-level citations — powered by a RAG pipeline built from scratch.

**The problem it solves:** Getting oriented in an unfamiliar codebase is slow. Codebase Q&A lets you interrogate a repo directly instead of manually spelunking through files.

**Architecture decisions:**
- **Manual RAG pipeline** — deliberately not using LangChain initially, to actually understand the retrieval pipeline rather than abstract it away
- **Supabase Postgres + pgvector** for the vector store, **Ollama** for local LLM + embeddings
- **Tree-sitter** planned for code-aware chunking rather than naive text splitting
- Own session + refresh-token auth implementation rather than reaching for a managed auth provider
- Built with a 4-person team: I own the RAG/embeddings/pgvector pipeline end-to-end, with teammates owning backend infra+auth and frontend

<p>
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white" />
<img src="https://img.shields.io/badge/pgvector-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Ollama-000000?style=flat-square" />
</p>

<br/>

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

<p>
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" />
<img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" />
<img src="https://img.shields.io/badge/Whisper-412991?style=flat-square&logo=openai&logoColor=white" />
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
</p>

<br/>

<details>
<summary><b>📦 Earlier / Foundational Projects</b> — click to expand</summary>

<br/>

**📊 AI Dataset Quality Inspector**
Statistical drift detection and ML fairness auditing platform. KS-test and PSI divergence analysis for feature shift, EEOC 4/5ths-rule fairness auditing, schema validation with type inference. Reduced manual dataset triage time by an estimated 65%; schema preview latency under 5ms with local caching.
`FastAPI` `Pandas` `SciPy` `React` `Python`

**🔍 GitHub Repo Analyzer**
Repository intelligence platform — codebase metrics, dependency graphs, language breakdowns, contributor patterns, AI-assisted summaries for any public GitHub repo.
`React` `TypeScript` `Vite` `GitHub API` `Python` · [Live →](https://github-repo-analyzer-by-mayank.vercel.app/)

**🔗 LifeLink**
Blockchain-based disaster relief fund tracker built under pressure at Smart India Hackathon 2025. Transparent, on-chain tracking of relief fund flow from donor to recipient. Led the team as Team Lead.
`Node.js` `Express` `Solidity` `Ethereum` `Web3.js`

**🔥 AI Profile Roaster**
Brutally honest AI career feedback on resumes and LinkedIn profiles, supporting PDF/DOCX/plain text input.
`Python` `Flask` `Groq AI`

**🎬 Squad 124 Portfolio**
Netflix-inspired team portfolio with dynamic filtering and scroll animations — vanilla HTML/CSS/JS, no frameworks.
`HTML5` `CSS3` `JavaScript`

</details>

<br/>

## 🌱 Open Source

### sktime / skpro

Contributing to production-grade probabilistic machine learning libraries used in production ML pipelines for forecasting, uncertainty quantification, and distributional prediction — currently pulling **134K+ monthly downloads**.

| PR | Type | Description |
|---|---|---|
| [#813](https://github.com/sktime/skpro/pull/813) | Documentation | Fixed typo in docstrings across distribution classes |
| [#833](https://github.com/sktime/skpro/pull/833) | Code quality | Fixed grammar inconsistency in validation error messages across multiple files |
| [#917](https://github.com/sktime/skpro/pull/917) | Refactoring | Eliminated duplicated feature-validation logic in CyclicBoosting |
| [#934](https://github.com/sktime/skpro/pull/934) | Bug fix | Fixed correctness bug where `SquaredDistrLoss` silently used `log_pdf` instead of `pdf` |

6+ total PRs across documentation, testing, maintenance, and logic fixes.

### React Native

- **PR #57487** — fixed a decimal-parsing bug in `transformOrigin`, merged into `react-native:main` and tagged "Shared with Meta"

> Working in production OSS codebases with strict CI, pre-commit hooks, and maintainer review is a different discipline than solo projects. Every PR has to justify itself, pass automated checks, and survive a real code review. The bar for "good enough" is higher, and that's the point.

<br/>

## 🛠 Tech Stack

**Languages**
<p>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
<img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white" />
<img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" />
<img src="https://img.shields.io/badge/Solidity-363636?style=flat-square&logo=solidity&logoColor=white" />
</p>

**Frontend**
<p>
<img src="https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black" />
<img src="https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" />
<img src="https://img.shields.io/badge/Framer_Motion-0055FF?style=flat-square&logo=framer&logoColor=white" />
<img src="https://img.shields.io/badge/Three.js-000000?style=flat-square&logo=threedotjs&logoColor=white" />
</p>

**Backend**
<p>
<img src="https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=nodedotjs&logoColor=white" />
<img src="https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white" />
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" />
<img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white" />
</p>

**Databases & Infra**
<p>
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white" />
<img src="https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" />
</p>

**AI / ML Tooling**
<p>
<img src="https://img.shields.io/badge/Claude_API-D97757?style=flat-square&logo=anthropic&logoColor=white" />
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square" />
<img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square" />
<img src="https://img.shields.io/badge/Ollama-000000?style=flat-square" />
<img src="https://img.shields.io/badge/OpenRouter-8A2BE2?style=flat-square" />
</p>

**Tools & Platforms**
<p>
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white" />
<img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white" />
<img src="https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white" />
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white" />
<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white" />
<img src="https://img.shields.io/badge/Kali_Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white" />
</p>

<br/>

## 📚 Currently Learning

```text
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

<br/>

## 📊 GitHub Stats

<div align="center">

<img src="https://img.shields.io/github/followers/MayankSharma-2812?style=for-the-badge&color=667EEA&labelColor=1a1a1a" />
<img src="https://img.shields.io/github/stars/MayankSharma-2812?style=for-the-badge&color=667EEA&labelColor=1a1a1a" />
<img src="https://img.shields.io/github/last-commit/MayankSharma-2812/mether-core?style=for-the-badge&color=667EEA&labelColor=1a1a1a&label=Last%20Commit" />

</div>

> *Note: badges above pull live from the GitHub API and stay up. If you want the richer visual stats/streak graphics back, those come from a third-party renderer that occasionally goes down (402 errors) — self-hosting a copy of it is the permanent fix if that matters to you.*

<br/>

## 🎓 Background

**Education**
- B.Tech CSE (Software Product Engineering) · Kalvium × JECRC University · Expected 2029
- Focus: full-stack development, backend systems, AI-integrated applications, scalable software engineering

**Achievements**
<p>
<img src="https://img.shields.io/badge/🏆-IT_Wizard_Award-gold?style=flat-square" />
<img src="https://img.shields.io/badge/🥇-Best_Website_Creator_2024-silver?style=flat-square" />
<img src="https://img.shields.io/badge/🥈-2nd_Web_Dev,_IPSC_2025-CD7F32?style=flat-square" />
<img src="https://img.shields.io/badge/🎯-5th_Video_Editing,_IPSC_2025-blue?style=flat-square" />
</p>

**Leadership**
- **Team Lead, Smart India Hackathon 2025** — Led multidisciplinary team through problem definition, technical architecture, frontend/backend split, and evaluation presentation

<br/>

## 🎯 What I'm Looking For

I'm open to **internships** in:
- Backend engineering (Python, Node.js, distributed systems)
- Full-stack development (React + any serious backend)
- Developer tooling or AI infrastructure

I work well in teams that move fast, have high standards for code quality, and aren't afraid to go deep on hard problems. I'm not looking for a place to coast — I want to work on things that are actually difficult.

<br/>

---

<div align="center">

### Let's build something worth building.

<a href="https://linkedin.com/in/mayank-sharma-7b277b312"><img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
<a href="mailto:msharma.dev.in@gmail.com"><img src="https://img.shields.io/badge/Email-Reach%20Out-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
<a href="https://github.com/MayankSharma-2812"><img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white" /></a>

</div>
