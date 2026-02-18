# MTS-SDLC-Lite v1.0.0

**Community Edition of SDLC Enterprise Framework 6.1.0**

> A tool-agnostic methodology for AI+Human software teams. Open source under MIT license.
> Built by [MTS (Minh Tam Solution)](https://github.com/Minh-Tam-Solution) — battle-tested on 3 production platforms.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![SDLC Framework](https://img.shields.io/badge/SDLC-6.1.0-blue.svg)](01-core-concepts/10-stage-lifecycle.md)

---

## What is MTS-SDLC-Lite?

MTS-SDLC-Lite is a **lightweight, open-source methodology** for teams building software with AI assistance. It teaches you how to organize AI+Human collaboration through structured stages, defined roles, quality gates, and clear governance — without locking you into any specific tool.

**Core philosophy**: Process-first, not tool-first. AI tools amplify thinking — make sure the thinking is worth amplifying.

**Proven results**: 10-50x productivity gains across 3 production platforms (BFlow, NQH-Bot, MTEP).

---

## The 10-Stage Lifecycle

Every software project moves through 10 stages. LITE tier activates the 5 most critical stages for small teams.

```
Stage   Name            Core Question    LITE Tier
─────   ──────────────  ──────────────   ─────────
  00    FOUNDATION      WHY?             [active]
  01    PLANNING        WHAT?            [active]
  02    DESIGN          HOW?             [active]
  03    INTEGRATE       WITH WHAT?       [active]
  04    BUILD           DO IT            [active]
  05    TEST            DOES IT WORK?    --------
  06    DEPLOY          SHIP IT          --------
  07    OPERATE         KEEP IT RUNNING  --------
  08    COLLABORATE     WORK TOGETHER    --------
  09    GOVERN          STAY COMPLIANT   --------
```

Most teams skip stages 00-02 and jump straight to BUILD. This is the root cause of feature waste (60-70% of features never used) and AI tool chaos.

Read more: [10-Stage Lifecycle](01-core-concepts/10-stage-lifecycle.md)

---

## 4-Tier Classification

Choose the tier that matches your team size. Start with LITE and grow.

| Tier | Team Size | Active Stages | Documentation Level |
|------|-----------|---------------|---------------------|
| **LITE** | 1-2 developers | 00, 01, 02, 03, 04 | README + docs/ basics |
| STANDARD | 3-10 developers | 00-06 | + ADRs + CLAUDE.md |
| PROFESSIONAL | 10-50 developers | All 10 stages | + Full specifications |
| ENTERPRISE | 50+ developers | All 10 stages | + Executive reports |

**You are here: LITE** — This repository covers LITE and STANDARD tiers.

Read more: [4-Tier Classification](01-core-concepts/4-tier-classification.md)

---

## SE4H / SE4A Governance

The most important concept in SDLC 6.1.0: **humans decide, agents execute**.

| Role | Who | Authority |
|------|-----|-----------|
| **SE4H** (Human Coach) | You — the developer, PM, CTO | Full — approves gates, validates deliverables |
| **SE4A** (Agent Executor) | AI tools — Claude, GPT, Copilot, Cursor, Ollama | None — proposes, implements, never self-approves |

This separation prevents "vibecoding" (AI generating code without human oversight) and ensures quality gates are meaningful.

Read more: [SE4H/SE4A Governance](01-core-concepts/se4h-se4a-governance.md)

---

## 12 SDLC Roles + 6 Team Archetypes

### Roles (8 SE4A + 3 SE4H + 1 Router)

| Role | Type | Stage | Gate | Key Constraint |
|------|------|-------|------|----------------|
| **researcher** | SE4A | 00-01 | G0.1 | Investigates, never decides product direction |
| **pm** (Product Manager) | SE4A | 00-01 | G0.1, G1 | Defines WHAT to build, never HOW |
| **pjm** (Project Manager) | SE4A | 01-04 | G-Sprint | Tracks execution, never changes scope |
| **architect** | SE4A | 02-03 | G2 | Designs systems, never writes production code |
| **coder** | SE4A | 04 | Sprint Gate | Implements, never merges without review |
| **reviewer** | SE4A | 04-05 | G3 | Reviews quality, never approves own code |
| **tester** | SE4A | 05 | G3 | Validates quality, never modifies code to pass tests |
| **devops** | SE4A | 06-07 | G4 | Deploys, never ships without G3 confirmation |
| **ceo** | SE4H | all | override | Strategic direction, budget — STANDARD+ |
| **cpo** | SE4H | 00-01 | G0.1, G1 | Product vision, priorities — STANDARD+ |
| **cto** | SE4H | 02-05 | G2, G3 | Architecture, security — STANDARD+ |
| **assistant** | Router | all | — | Guides users to correct agent — STANDARD+ |

### Teams (4 core + 2 STANDARD+)

| Team | Agents | Stages | Use Case |
|------|--------|--------|----------|
| **planning** | researcher, pm, pjm, architect | 00-01 | Foundation & Planning |
| **dev** | coder, reviewer | 04-05 | Build & Review |
| **qa** | tester, reviewer | 05 | Quality Assurance (required for G3) |
| **fullstack** | researcher, pm, pjm, architect, coder, reviewer | 00-05 | LITE tier end-to-end |
| **executive** | ceo, cpo, cto | all | Strategic decisions — STANDARD+ |
| **support** | assistant | all | User guidance, routing — STANDARD+ |

At LITE tier, one person often wears multiple hats. The 8 SE4A roles apply as *thinking modes* — when you write requirements, you're thinking as `pm`; when you review code, you're thinking as `reviewer`. The 4 additional roles (ceo, cpo, cto, assistant) activate at STANDARD+ tier.

Read more: [12 SDLC Roles](02-roles-and-teams/12-sdlc-roles.md) | [4 Team Archetypes](02-roles-and-teams/4-team-archetypes.md) | [Multi-Provider Strategy](02-roles-and-teams/multi-provider-strategy.md)

---

## Quick Start

### Path 1: Founders / CTOs (strategic)
1. Read [Iceberg of Change](01-core-concepts/iceberg-of-change.md) — understand system thinking
2. Follow the [Founder Playbook](03-playbooks/founder-playbook.md) — 3 steps in 3-4 weeks
3. Learn from [Case Studies](05-case-studies/battle-tested-platforms.md) — real examples

### Path 2: Team Leads (tactical)
1. Read [10-Stage Lifecycle](01-core-concepts/10-stage-lifecycle.md) — understand the framework
2. Start with [LITE Quickstart](03-playbooks/lite-quickstart.md) — running in 30 minutes
3. Set up roles with [12 SDLC Roles](02-roles-and-teams/12-sdlc-roles.md)

### Path 3: Developers (hands-on)
1. Follow [LITE Quickstart](03-playbooks/lite-quickstart.md) — folder structure + first docs
2. Try [TinySDLC](05-case-studies/tinysdlc-reference.md) — reference implementation with AI agents
3. Use [Templates](04-templates/) — ready-to-use project templates

---

## Proven Results

| Platform | Domain | Team | Result | Framework |
|----------|--------|------|--------|-----------|
| **BFlow** | SME Operations | Small team | 20x productivity, 200K SMEs | SDLC 4.8 → 6.1.0 |
| **NQH-Bot** | F&B Workforce | Small team | 78% → 95% success rate | SDLC 4.8 → 6.1.0 |
| **MTEP** | Education PaaS | 1 developer | 50x productivity, <30min setup | SDLC 5.0 → 6.1.0 |

**Common pattern**: Small team + AI tools + SDLC discipline = output that rivals teams 10x larger.

Read more: [Battle-Tested Platforms](05-case-studies/battle-tested-platforms.md)

---

## The SDLC Ecosystem

SDLC 6.1.0 is organized in **2 layers** across **2 tiers**:

```
                 METHODOLOGY                       IMPLEMENTATION
                 (what to do — tool-agnostic)       (how to run it — platforms & tools)

COMMUNITY   MTS-SDLC-Lite (MIT)             ←→    TinySDLC (MIT)
TIER        "Learn the concepts"                   "See it running"
             This repository                        github.com/Minh-Tam-Solution/tinysdlc

ENTERPRISE  SDLC Enterprise Framework       ←→    Your Platform
TIER        "Full methodology at scale"            Build your own, or use:
             Licensed per organization              • SDLC Orchestrator (by MTS)
                                                    • Your custom tooling
                                                    • Any SDLC-compatible platform
```

### How the 2 layers work

**Methodology layer** (left) defines *what to do* — stages, gates, roles, teams, governance model. It is tool-agnostic and works with any AI coder (Claude, GPT, Copilot, Cursor, Ollama) or project management tool.

**Implementation layer** (right) provides *how to run it* — specific platforms, agent orchestration, automation. Each organization chooses or builds their own implementation.

### Key relationships

- **MTS-SDLC-Lite** is the community edition of the SDLC methodology. **TinySDLC** is one open-source implementation — but anyone can build their own tools on these concepts.
- **SDLC Enterprise Framework** is the full methodology for organizations of 10-500+. It is **independently licensable** — any organization can adopt it and build their own platform.
- **SDLC Orchestrator** is MTS's own enterprise platform implementation — one of potentially many. Other enterprises may license the framework and develop entirely custom platforms suited to their domain.
- The framework survives independent of any tool. Your team might use different tools, different AI providers, different workflows — and still follow SDLC 6.1.0.

| Product | Layer | License | Access |
|---------|-------|---------|--------|
| **MTS-SDLC-Lite** | Methodology (community) | MIT | This repo |
| **TinySDLC** | Implementation (community) | MIT | [github.com/Minh-Tam-Solution/tinysdlc](https://github.com/Minh-Tam-Solution/tinysdlc) |
| **SDLC Enterprise Framework 6.1.0** | Methodology (enterprise, all tiers) | Per-org license | Contact MTS |
| **SDLC Orchestrator** | Implementation (enterprise, by MTS) | Proprietary | Contact MTS |

Read more: [Lite vs Enterprise](06-reference/lite-vs-enterprise.md)

---

## Repository Structure

```
MTS-SDLC-Lite/
├── 01-core-concepts/        Core SDLC 6.1.0 principles
│   ├── 10-stage-lifecycle    The 10-stage software lifecycle
│   ├── 4-tier-classification LITE / STANDARD / PROFESSIONAL / ENTERPRISE
│   ├── se4h-se4a-governance  Human Coach + Agent Executor model
│   ├── quality-gates         G0.1 through G4 gate system
│   ├── iceberg-of-change     System thinking framework
│   └── design-thinking       Build the RIGHT thing first
│
├── 02-roles-and-teams/      Who does what
│   ├── 12-sdlc-roles        12 roles (8 SE4A + 3 SE4H + 1 Router)
│   ├── 4-team-archetypes    6 teams: Planning, Dev, QA, Fullstack + Executive, Support
│   └── multi-provider       Model assignment per role
│
├── 03-playbooks/            Step-by-step guides
│   ├── lite-quickstart       LITE tier in 30 minutes
│   ├── founder-playbook      3-step audit-design-standardize
│   ├── quick-win-checklist   First win in 1 week
│   └── crisis-to-pattern     Turn failures into reusable assets
│
├── 04-templates/            Ready-to-use templates
│   ├── project-folder        10-stage folder structure
│   ├── use-case-canvas       Map use cases through stages
│   ├── sdlc-config           Starter project config
│   └── gate-checklist        Quality gate pass/fail criteria
│
├── 05-case-studies/         Real-world examples
│   ├── battle-tested         BFlow, NQH-Bot, MTEP
│   └── tinysdlc-reference    How TinySDLC implements 6.1.0
│
└── 06-reference/            Background & context
    ├── lite-vs-enterprise    Community vs Enterprise comparison
    ├── glossary              Key terms and definitions
    └── version-history       How SDLC evolved to 6.1.0
```

---

## Contributing

We welcome contributions from the community. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Ways to contribute**:
- Share success stories (most valuable!)
- Improve documentation
- Add templates and patterns
- Report issues

---

## License

MIT License. See [LICENSE](LICENSE).

Both MTS-SDLC-Lite and [TinySDLC](https://github.com/Minh-Tam-Solution/tinysdlc) are open source under MIT. The SDLC Enterprise Framework 6.1.0 is licensed separately per organization — see [Lite vs Enterprise](06-reference/lite-vs-enterprise.md) for details.

---

## Contact

**Minh Tam Solution (MTS)**
- GitHub: [Minh-Tam-Solution](https://github.com/Minh-Tam-Solution)
- Email: taidt@mtsolution.com.vn
- Enterprise inquiries: [Lite vs Enterprise](06-reference/lite-vs-enterprise.md)

---

*"Tools amplify thinking — choose thinking wisely."*

*Built by MTS. Battle-tested on BFlow, NQH-Bot, MTEP. Open source for the community.*
