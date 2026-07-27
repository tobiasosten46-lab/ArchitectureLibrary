<div align="center">

# Condrox AI Coder

### Deterministic Cognitive Conversational AI — Mother AI Architecture

**Version 5.0.0** · **Python 3.11+** · **FastAPI + React 19 + Electron**

[![Tests](https://img.shields.io/badge/tests-984%20passing-brightgreen)](tests/)
[![Pipeline](https://img.shields.io/badge/pipeline-21%20stages-blue)](core/pipeline/)
[![Profiles](https://img.shields.io/badge/agent%20profiles-8%20builtin-blueviolet)](core/brain_profiles/)
[![Tools](https://img.shields.io/badge/tools-7%20instruments-orange)](core/brain_tools/)
[![License](https://img.shields.io/badge/license-Proprietary-red)](LICENSE)

</div>

---

## What is Condrox AI Coder?

Condrox AI Coder is a **deterministic, rule-based cognitive AI system** —
not an LLM. There are no neural networks for text generation, no
transformer architectures, and no probabilistic output. Every response
can be traced to exact algorithmic decisions, and every code path is
deterministic and reproducible.

The system is built around a single central intelligence — the
**Mother AI** (BrainController) — that processes user input through a
21-stage cognitive pipeline using symbolic reasoning, BM25 knowledge
retrieval, neural-embedding search, and deterministic algorithms.

> **Copyright © 2026 Tobias Østen. All rights reserved.**
> Proprietary, pre-revenue. See [LICENSE](LICENSE).

---

## The Mother AI Architecture

### One Intelligence, Not Many

The core principle of Condrox AI Coder is simple:

> **BrainController IS Mother AI. Agents are configuration, not
> intelligence.**

There is no "Code Agent AI" that thinks independently. There is no
"Analyze Agent AI" with its own reasoning. There is only Mother AI —
configured to focus on code, or analysis, or explanation, or
conversation.

### What Mother AI Owns

| What | Count | Description |
|---|---|---|
| Subsystems | 53 | Memory, knowledge, reasoning, personality, security, ethics, etc. |
| Pipeline stages | 21 | The cognitive pipeline from input to response |
| Conversational intelligence components | 26 | Empathy, humor, listening, social awareness, etc. |
| Agent profiles | 8 | Configuration shapes (not separate intelligences) |
| Tools | 7 | Instruments that return structured evidence |
| AI-OS kernel | 1 | Service management, event bus, self-repair |
| Autonomous learning | 1 | Background threads that learn after each turn |
| SQLite persistence | 1 | Memory, knowledge, user profiles saved to disk |

### What an Agent Is — and Isn't

An **agent** is a **profile** — configuration that shapes how Mother AI
uses its existing pipeline, tools, and engines. A profile defines:

- **Objectives** — what Mother AI should prioritize
- **Allowed tools** — which instruments are available
- **Tone modifiers** — how the response is styled
- **Policy overrides** — extra rules for quality checks
- **Features** — which conversational components are active

An agent does **NOT** have:

- Its own pipeline (Mother AI's 21-stage pipeline always runs)
- Its own reasoning (ReasoningEngine does reasoning)
- Its own output generation (Stage09 Synthesis writes the response)
- Its own memory (MemoryManager owns all memory)
- Its own identity (PersonalityEngine owns identity)

### The Analogy

Think of Mother AI as a skilled professional. An agent profile is like
a **role they step into**:

- **Code Engineer role** — "Focus on code, be precise, use code tools"
- **Analyst role** — "Focus on analysis, be structured, cite evidence"
- **Companion role** — "Focus on empathy, listen, no tools needed"

The professional doesn't change — their skills, memory, and
intelligence stay the same. Only their focus and tools change.

---

## The 21-Stage Cognitive Pipeline

```
User Input
    │
    ▼
Stage 01: Preprocessor — normalize input, expand contractions
Stage 02: Intent classification — Word Identity Engine + Emotion Detector
Stage 02b: Intent enrichment — IntentExpander
Stage 03: Mode selector — maps intent to mode + syncs agent profile
Stage 04: Domain router — KnowledgeRouterV2
Stage 05: Context builder — ContextManager
Stage 05b: Context enrichment — MultiTurn, Goals, Temporal
Stage 06: Knowledge fetch — KnowledgeRouter + Wikipedia
Stage 07: Memory fetch — MemoryManager + MemoryGraph
Stage 07b: Memory store — persist new memories
Stage 08: Reasoning core — ReasoningEngine + DeepReasoning
Stage 08b: Agent execution — runs tools for active profile
Stage 08c: Emotion update — Artificial Emotional System (Phase 19)
Stage 09: Synthesis — Mother AI writes the response
Stage 09b: Response quality — consistency, repair, contradictions
Stage 09c: Pattern learning — user patterns
Stage 09d: Metacognition — self-assessment
Stage 10: Personality — tone and style
Stage 11: Ethics — content policy
Stage 12: Security — PII, secrets, injection
Stage 13: Output builder — final rendering
Stage 14: Delivery — return to user
    │
    ▼
Final Output → User
```

### Key Observation

The agent (profile) doesn't write the response. It only selects which
tools to run and provides tone modifiers. **Mother AI (Stage09
Synthesis) writes every response** using the evidence from the tools
and the tone from the profile.

---

## The 8 Builtin Agent Profiles

| Profile | Name | Focus | Tools | Tone |
|---|---|---|---|---|
| `default` | Condrox | General-purpose assistant | All tools | warm, conversational, concise |
| `code` | Code Engineer | Code implementation, debugging, review | code_analysis, code_generation, file_ops, shell, git | precise, technical, structured |
| `analyze` | Analyst | Performance, security, architecture analysis | code_analysis, wiki, knowledge | analytical, structured, objective |
| `architect` | Architect | System design, phase-based planning | architecture, code_analysis, wiki, knowledge | structured, constraint-first, comprehensive |
| `explain` | Educator | Clear explanations, adaptive depth | explain, wiki, knowledge | clear, educational, patient |
| `social` | Companion | Empathetic conversation, listening | None (pure conversation) | empathetic, warm, validating |
| `personal` | Personal Assistant | Warm, memory-heavy, personal context | knowledge, memory, wiki | warm, personal, proactive |
| `developer` | Developer | Terse, technical, code-first | All tools | terse, technical, code-first |

### Hot-Swap: O(1) Agent Switching

Switching agents is an O(1) operation. It takes effect on the next
request. No state migrates. No pipeline restart. No memory transfer.

```python
bc.use_profile("code")       # switch to Code Engineer
bc.active_profile_id()       # → "code"
bc.use_profile("analyze")    # switch to Analyst
```

---

## The 7 Tools

Tools are the instruments agents use. Each tool returns structured
evidence. Mother AI writes the final response from that evidence.
**Tools never produce prose.**

| Tool | What It Does |
|---|---|
| `code_analysis` | Analyzes code for performance, security, architecture, trade-offs |
| `code_generation` | Generates real working code for 34 common programming tasks |
| `wiki` | Searches Wikipedia for knowledge |
| `explain` | Structures explanations (6 types: step-by-step, definition, mechanism, rationale, examples, comparison) |
| `architecture` | Structures system architecture plans (6 types: REST API, microservices, database, realtime, web app, generic) |
| `knowledge` | Queries the knowledge base via KnowledgeRouter |
| `memory` | Queries the memory store via MemoryManager |

Tool execution is **sequential** (`max_parallel_tools = 1`) —
predictable and debuggable.

---

## Artificial Emotional System (Phase 19 — Designed)

Condrox AI Coder includes a designed (not yet implemented) artificial
emotional system — a layered internal state system that modulates how
Mother AI evaluates and responds to situations.

### The Core Principle

> Artificial emotion is not about pretending the AI has human feelings.
> It is about designing system states that influence behavior, memory,
> priority, warning signals, and decision-making in ways that mimic the
> function of emotions.

An AI does not feel happiness, stress, fear, or curiosity in the
biological sense. It has no dopamine, adrenaline, cortisol, or nervous
system. But that does not mean an artificial emotional system is
impossible — it means the system must be understood differently.

### The 10-Layer Architecture

| Layer | Purpose |
|---|---|
| 1. Trigger Layer | Detects events (task success, failure, user correction, ethical risk, etc.) |
| 2. Evaluation Layer | Assigns meaning (polarity, intensity, cause, state deltas) |
| 3. State Layer | Stores 16 numeric values (confidence, uncertainty, caution, pressure, satisfaction, urgency, stability, overload, trust, frustration, curiosity, reward_level, risk_level, system_comfort, system_stress, warning_level) |
| 4. Effect Layer | Applies state to behavior (tone modifiers, verification triggers) |
| 5. Reward/Punishment Layer | Reinforces successful behaviors, weakens unsuccessful ones |
| 6. Warning System | Emits internal warnings (low confidence, overload, ethical risk) |
| 7. Memory Tagging Layer | Tags memories with emotional metadata |
| 8. Personality/Expression Layer | Sets tone based on emotional state |
| 9. Agent Integration Layer | Hot-swaps profiles based on emotional state |
| 10. Regulation Layer | Caps, floors, decay, cooldowns, reset |

### Four Artificial Emotions

| Emotion | Trigger | Effect |
|---|---|---|
| **Happiness** | task_success, user_satisfaction | reward_level +, confidence +, warmer tone, continue strategy |
| **Stress** | repeated_failure, high_uncertainty | caution +, verification +, slower execution, fallback to safe mode |
| **Fear** | destructive_action, ethical_risk | risk_level +, stop execution, require confirmation, activate safety |
| **Curiosity** | knowledge_gap, unresolved_contradiction | curiosity +, gather more data, ask targeted questions |

### Fake Emotion vs Artificial Emotion

**Fake emotion** is when an AI says "I am happy" without any system
behind it. **Artificial emotion** means the system has triggers,
evaluation, state changes, behavioral effects, memory weighting,
warning signals, reward logic, regulation, and long-term adaptation.
That is not fake — that is a technical emotional architecture.

---

## Key Capabilities

| Capability | Description |
|---|---|
| **21-stage cognitive pipeline** | Deterministic, traceable processing from intent detection to response delivery |
| **26 conversational intelligence components** | Intent expansion, multi-turn reasoning, goal tracking, memory graph, consistency engine, contradiction detection, semantic repair, and more |
| **8 agent profiles** | Default, Code, Analyze, Architect, Explain, Social, Personal, Developer — O(1) hot-swap |
| **7 tools** | Code analysis, code generation, wiki, explain, architecture, knowledge, memory |
| **Artificial Emotional System** | 10-layer internal state system (Phase 19 — designed) |
| **Creative stack** | Emotion → Palette → Music Prompt pipeline with QualityGuardrail |
| **AI Operating System** | 8 OS components: EventBus, ServiceManager, BootManager, MonitorLoop, StateManager, TaskQueue, SelfRepairManager, AIOSKernel |
| **Semantic memory graph v2** | PageRank relevance ranking, neural embedding search, SQLite persistence |
| **Word Identity System** | O(1) semantic word lookup across 5 modular JSON stores |
| **Autonomous learning** | Post-turn learning: knowledge extraction, pattern recognition, behavior analysis, meta-learning |
| **Enterprise admin dashboard** | React 19 + TypeScript + Vite + TailwindCSS + D3.js + Electron (28 pages) |
| **Knowledge backend** | 21,917+ items across 14 domains, BM25 retrieval, vector embeddings |
| **Production deployment** | Docker (multi-stage, gunicorn), Kubernetes (HPA 2–10 replicas), Cloudflare Tunnel |

---

## Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     MOTHER AI (BrainController)              │
│                                                              │
│  ┌──────────────────────────────────────────────────────┐   │
│  │              21-STAGE COGNITIVE PIPELINE              │   │
│  │                                                       │   │
│  │  Stage01 → Stage02 → ... → Stage08b → Stage09 → ...  │   │
│  │                              │                        │   │
│  │                              ▼                        │   │
│  │  ┌──────────────────────────────────────────────┐    │   │
│  │  │           STAGE 08b: AGENT EXECUTION          │    │   │
│  │  │                                               │    │   │
│  │  │  Active Profile ──→ Tools ──→ Evidence        │    │   │
│  │  │       │                        │              │    │   │
│  │  │       │                        ▼              │    │   │
│  │  │       │              Stage09 Synthesis        │    │   │
│  │  │       │              (writes response)        │    │   │
│  │  │       │                        │              │    │   │
│  │  │       │                        ▼              │    │   │
│  │  │       │              Stage10 Personality      │    │   │
│  │  │       │              (applies tone)           │    │   │
│  │  └───────┴───────────────────────────────────────┘    │   │
│  └───────────────────────────────────────────────────────┘   │
│                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌──────────────┐ │
│  │ ProfileConnector│  │  ToolRegistry   │  │ MemoryManager│ │
│  │  (O(1) hot-swap)│  │  (O(1) lookup)  │  │  (all memory)│ │
│  └─────────────────┘  └─────────────────┘  └──────────────┘ │
│                                                              │
│  ┌─────────────────┐  ┌─────────────────┐  ┌──────────────┐ │
│  │ EmotionEngine   │  │  KnowledgeRouter│  │ ReasoningEng │ │
│  │  (Phase 19)     │  │  (BM25 + vector)│  │  + DeepReas  │ │
│  └─────────────────┘  └─────────────────┘  └──────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

---

## Quick Start

### Prerequisites

- Python 3.11+
- Node.js 18+ (for dashboard)
- SQLite (bundled with Python)

### Backend

```powershell
# Install Python dependencies
pip install -r requirements.txt

# Run the test suite
python -m pytest tests/ -v

# Start the REST API
python -m uvicorn api.main:app --reload --port 8002

# Smoke check
python -c "from core import BrainController; bc = BrainController(); print(bc.boot_system().success)"
```

### Admin Dashboard (Web)

```powershell
cd dashboard
npm install
npm run dev          # http://localhost:5173
```

### Admin Dashboard (Electron Desktop)

```powershell
cd dashboard
npm run electron:dev      # Dev mode
npm run electron:build    # Build Windows NSIS installer
```

### Using Agent Profiles

```python
from core.brain.brain_controller import BrainController

bc = BrainController()
bc.boot_system()

# Switch to Code Engineer
bc.use_profile("code")
state = bc.process_request("write a python function to sort a list")

# Switch to Analyst
bc.use_profile("analyze")
state = bc.process_request("analyze this code for performance issues")

# Switch to Companion (no tools — pure conversation)
bc.use_profile("social")
state = bc.process_request("I'm having a rough day")

# Check active profile
print(bc.active_profile_id())     # → "social"
print(bc.active_profile().name)   # → "Companion"
```

### Environment Variables

Copy `.env.example` to `.env` and fill in real values. **Never commit `.env`.**

| Variable | Purpose | Required |
|---|---|---|
| `CONDROX_ADMIN_USER` | Admin username (default: `Dovakina`) | No |
| `CONDROX_ADMIN_PASSWORD` | Admin password (auto-generated if unset) | Recommended |
| `CONDROX_API_KEY` | API key for protected endpoints | Yes (production) |
| `CONDROX_SKIP_KNOWLEDGE_LOAD` | Set to `1` to skip knowledge loading at boot | No |
| `KNOWLEDGE_DATA_PATH` | Path to knowledge store | Yes (production) |

---

## Project Structure

```
Condrox AI Coder/
├── core/                          # Core Intelligence Layer
│   ├── brain/                     # Mother AI (BrainController, BrainState, BrainConfig)
│   ├── brain_profiles/            # Agent profiles (8 builtin, O(1) hot-swap)
│   ├── brain_tools/               # Agent tools (7 instruments)
│   ├── brain_stability/           # Stability layer (input validation, session store, metrics)
│   ├── brain_emotion/             # Artificial Emotional System (Phase 19 — designed)
│   ├── pipeline/                  # 21-stage cognitive pipeline
│   ├── memory/                    # Semantic memory + vector retrieval
│   ├── knowledge/                 # Knowledge backend + loader (21,917+ items)
│   ├── cognition/                 # Reasoning, context, strategy, meta-learning
│   ├── conversational/            # 26 CI components
│   ├── creative/                  # Emotion → Music stack
│   ├── storage/                   # SQLite persistence
│   ├── word_identity/             # Word Identity System (O(1) lookup, 5 JSON stores)
│   ├── os/                        # AI Operating System (8 components)
│   ├── autonomous/                # Autonomous Learning System
│   ├── engines/                   # HWA, PBE, DCL, Heartbeat
│   ├── personality/               # Profile-based response styling
│   ├── security/                  # Input/output security
│   ├── ethics/                    # Content policy checks
│   └── boot/                      # Boot orchestration
├── api/                           # FastAPI REST service
│   ├── main.py                    # Public + authenticated endpoints
│   ├── admin_routes.py            # Admin API (44+ endpoints)
│   └── user_db.py                 # SQLite user database
├── dashboard/                     # React 19 + TypeScript + Vite + Electron
│   ├── src/pages/                 # 28 pages
│   ├── electron/                  # Electron main process
│   └── package.json
├── AppMang/                       # Enterprise admin panel
├── Frontendweb/                   # Public-facing web frontend
├── tests/                         # pytest suite (984+ tests)
├── config/                        # YAML + JSON configuration
├── Docs/                          # All project documentation
│   ├── 14-NovaAgent/              # Agent system documentation
│   ├── 30-ArtificialEmotion/      # Artificial Emotional System documentation
│   ├── 29-Dashboard/              # Enterprise dashboard docs
│   ├── 30-Contributors/           # Contributor docs + access governance
│   └── 31-AppMang/                # AppMang enterprise panel docs
├── scripts/                       # Utility scripts
├── k8s/                           # Kubernetes manifests
├── monitoring/                    # Prometheus config
├── Report/                        # Professional report system
├── Archive/                       # Archived/dead systems
├── informationcenter/             # Reference docs the AI reads as guidelines
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── LICENSE
├── AGENTS.md
└── README.md
```

---

## Testing

```powershell
# Full suite
python -m pytest tests/ -v

# Specific module
python -m pytest tests/test_brain_profiles_tools.py -v

# With coverage
python -m pytest tests/ --cov=core --cov-report=html
```

**Current status:** 984+ tests passing, 0 failures.

Tests are held to the highest academic, corporate, and laboratory
standards. See `Report/rules/testing_standards.md` for the 12
acceptance criteria (A1–A12).

---

## Deployment

### Docker

```powershell
docker build -t condrox-ai .
docker-compose up -d
```

### Kubernetes

```powershell
kubectl apply -f k8s/
```

### Production

- **Public API:** `https://chat.novaspireai.one`
- **Deployment:** Cloudflare Tunnel → Uvicorn (4 workers)
- **Monitoring:** Prometheus `/metrics` endpoint + Grafana dashboards

---

## Documentation

| Document | Description |
|---|---|
| [Docs/14-NovaAgent/agent_system_overview.md](Docs/14-NovaAgent/agent_system_overview.md) | **Complete agent system guide — read this first** |
| [Docs/14-NovaAgent/mother_ai_agent_system_design.md](Docs/14-NovaAgent/mother_ai_agent_system_design.md) | Phase 18 design document (implemented) |
| [Docs/30-ArtificialEmotion/README.md](Docs/30-ArtificialEmotion/README.md) | Artificial Emotional System (Phase 19 — designed) |
| [Docs/30-ArtificialEmotion/mother_ai_emotional_system_design.md](Docs/30-ArtificialEmotion/mother_ai_emotional_system_design.md) | Emotional system design document |
| [Docs/index.md](Docs/index.md) | Master documentation index |
| [Docs/00-Overview/PROGRESS.md](Docs/00-Overview/PROGRESS.md) | Detailed development progress |
| [AGENTS.md](AGENTS.md) | Developer notes for AI agents |
| [Report/rules/](Report/rules/) | Writing, testing, academic, corporate, lab standards |
| [LICENSE](LICENSE) | Copyright and licensing terms |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.11+, FastAPI, Uvicorn, SQLite |
| Frontend | React 19, TypeScript, Vite, TailwindCSS, D3.js |
| Desktop | Electron 43 |
| Deployment | Docker, Kubernetes, Cloudflare Tunnel |
| Monitoring | Prometheus, Grafana |
| CI/CD | GitHub Actions (Bandit + Trivy security scanning) |
| Testing | pytest (984+ tests) |

---

## Contributing

This repository is **private** and governed by a strict access control
policy. All contributor access is a privilege, not a right, and may be
revoked at any time by the project lead.

### Before You Start

**Read these documents first:**

1. [Contributor Onboarding](Docs/30-Contributors/00_contributor_onboarding.md)
2. [Access Governance Policy](Docs/30-Contributors/08_access_governance.md) — **mandatory before any access**
3. [Security Architecture Overview](Docs/30-Contributors/01_security_architecture_overview.md)
4. [Contributor Codebase Map](Docs/30-Contributors/07_contributor_codebase_map.md)

### Access Tiers

| Stage | Access | How to Earn |
|---|---|---|
| 1 — Trial | Read-only | Answer onboarding questions |
| 2 — Contributor | Feature branches | 1 merged PR |
| 3 — Trusted | Review others | 3 merged PRs, no regressions |
| 4 — Maintainer | Founder-only | Never granted |

### Branch Naming

```
feature/<name>     # New functionality
fix/<name>         # Bug fixes
security/<name>    # Security hardening
agent/<name>       # Agent-specific work
dashboard/<name>   # Dashboard / frontend
docs/<name>        # Documentation
test/<name>        # Test additions
```

**No contributor merges their own PR. No contributor has production or
secrets access.**

---

## Security

### Secrets Policy

- `.env`, API keys, database credentials, Cloudflare tokens — **founder-only**
- Contributors use placeholder values from `.env.example`
- If you accidentally gain access to a secret: notify the founder
  immediately, delete your local copy, do not commit or share it

### Branch Protection

- `main` requires PR + 1 founder approval + passing CI
- Force-push and deletions disabled
- Linear history required

### Incident Response

If you suspect a security incident:

1. Do not attempt to fix it yourself
2. Do not disclose it publicly
3. Notify the founder immediately via private channel
4. Document what you observed (timestamps, screenshots, logs)

---

## Project Lead

**Tobias Østen** — Founder & Project Lead

- Public API: https://chat.novaspireai.one
- Repository: https://github.com/tobiasosten46-lab/Condrox-AI-Coder

---

## License

Proprietary. Copyright © 2026 Tobias Østen. All rights reserved.

See [LICENSE](LICENSE) for full terms. No redistribution, modification,
or commercial use permitted without written approval from the copyright
holder.

---

<div align="center">

**This repository is private. Do not share, fork publicly, or
distribute without written approval from the project lead.**

</div>
