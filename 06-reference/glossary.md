# Glossary

**SDLC Version**: 6.1.0
**Category**: Reference
**Status**: Active
**License**: MIT

---

## Core Terms

### SDLC (Software Development Lifecycle)

A structured approach to building software, from understanding the problem to operating in production. SDLC 6.1.0 defines 10 stages, 4 tiers, 12 roles (8 SE4A + 3 SE4H + 1 Router), and quality gates.

### SE4H (Software Engineer for Human)

The human decision maker in AI+Human teams. SE4H approves quality gates, makes scope decisions, and provides strategic direction. The "coach" role — guides but doesn't execute.

See: [SE4H/SE4A Governance](../01-core-concepts/se4h-se4a-governance.md)

### SE4A (Software Engineer for Agent)

The AI agent executor in AI+Human teams. SE4A implements tasks, follows instructions, and produces deliverables. The "player" role — executes but never self-approves.

See: [SE4H/SE4A Governance](../01-core-concepts/se4h-se4a-governance.md)

---

## Stages

### 10-Stage Lifecycle

The complete SDLC 6.1.0 lifecycle:

| Stage | Name | Core Question |
|-------|------|--------------|
| 00 | FOUNDATION | WHY are we building this? |
| 01 | PLANNING | WHAT are we building? |
| 02 | DESIGN | HOW will we build it? |
| 03 | INTEGRATE | What CONTRACTS do we need? |
| 04 | BUILD | Let's BUILD it |
| 05 | TEST | Does it WORK correctly? |
| 06 | DEPLOY | Can we SHIP it safely? |
| 07 | OPERATE | Is it RUNNING well? |
| 08 | LEARN | What did we LEARN? |
| 09 | GOVERN | Are we COMPLIANT? |

See: [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md)

### Active Stages (LITE Tier)

At LITE tier, 5 stages are active: 00-FOUNDATION, 01-PLANNING, 02-DESIGN, 03-INTEGRATE, 04-BUILD. The remaining stages are activated as team size and project complexity grow.

---

## Quality Gates

### Quality Gate

A checkpoint between stages that prevents moving forward with incomplete or low-quality work. Each gate has defined criteria, owners, and requires human (SE4H) approval.

### Feature Gates

| Gate | Name | Purpose |
|------|------|---------|
| G0.1 | Problem Validated | Confirm the problem is real and worth solving |
| G0.2 | Solution Diversity | Ensure multiple solutions were explored |
| G1 | Requirements Complete | Verify requirements are clear and feasible |
| G2 | Design Approved | Validate architecture before coding |
| G3 | Ship Ready | Confirm code is production-quality |
| G4 | Production Ready | Verify safe deployment and monitoring |

### Sprint Gate (G-Sprint)

A gate during the BUILD stage that validates sprint-level deliverables. Sprint goal met, acceptance criteria satisfied, code compiles.

See: [Quality Gates](../01-core-concepts/quality-gates.md)

---

## Tiers

### 4-Tier Classification

Project classification by team size and process formality:

| Tier | Team Size | Key Characteristic |
|------|-----------|-------------------|
| LITE | 1-2 developers | Self-assessed gates, minimal documentation |
| STANDARD | 3-10 developers | Tech lead review, written sign-offs |
| PROFESSIONAL | 10-50 developers | CTO approval, formal reviews |
| ENTERPRISE | 50+ developers | Board governance, automated compliance |

See: [4-Tier Classification](../01-core-concepts/4-tier-classification.md)

---

## Roles

### 12 SDLC Roles (8 SE4A + 3 SE4H + 1 Router)

**SE4A Roles** (Agent Executors — active at all tiers):

| Role | Responsibility | Key Constraint |
|------|---------------|----------------|
| researcher | Investigates problems, gathers evidence | Never decides product direction |
| pm | Defines WHAT to build (Product Manager) | Never decides HOW to build |
| pjm | Tracks WHEN to build (Project Manager) | Never changes scope |
| architect | Designs HOW to build | Never writes production code |
| coder | Implements the solution | Never merges without review |
| reviewer | Validates quality and security | Never approves own code |
| tester | Validates test coverage | Never modifies code to pass tests |
| devops | Manages deployment | Never ships without G3 |

**SE4H Roles** (Human Coaches — STANDARD+ tier):

| Role | Responsibility | Key Constraint |
|------|---------------|----------------|
| ceo | Strategic direction, budget, final escalation | AI advisor only, human decides |
| cpo | Product vision, feature scope, priorities | AI advisor only, human decides |
| cto | Architecture, security, technology decisions | AI advisor only, human decides |

**Router Role** (STANDARD+ tier):

| Role | Responsibility | Key Constraint |
|------|---------------|----------------|
| assistant | Routes users to correct agent/team | No decision authority, guidance only |

**At LITE tier**: The 8 SE4A roles are "thinking modes" for one person. SE4H roles are implicit (you are the human). At STANDARD+, all 12 roles are explicitly defined.

See: [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md)

### pm vs pjm

**Product Manager (pm)**: Owns WHAT gets built — requirements, priorities, scope.
**Project Manager (pjm)**: Owns WHEN and HOW MUCH — timeline, resources, execution.

These are distinct roles. In smaller teams, one person may fill both, but the thinking modes are different.

---

## Teams

### 6 Team Archetypes (4 core + 2 STANDARD+)

| Team | Composition | When to Use |
|------|-------------|-------------|
| planning | researcher, pm, pjm, architect | Starting new features, clarifying requirements |
| dev | coder, reviewer | Implementing and reviewing code |
| qa | tester, reviewer | Pre-release validation, security audit |
| fullstack | researcher, pm, pjm, architect, coder, reviewer | Small projects, rapid prototyping |
| executive | ceo, cpo, cto | Strategic decisions, VCR approval — STANDARD+ |
| support | assistant | User guidance, routing — STANDARD+ |

See: [4 Team Archetypes](../02-roles-and-teams/4-team-archetypes.md)

---

## AI Strategy

### Multi-Provider Strategy

Different roles need different AI model strengths. The SE4A-only split is 2-2-4; at STANDARD+ with all 12 roles it extends to 4-3-5:

| Tier | SE4A Roles | STANDARD+ Additions |
|------|-----------|---------------------|
| Deep Reasoning | researcher, architect | + ceo, cto |
| Precise Analysis | pm, reviewer | + cpo |
| Fast Execution | pjm, coder, tester, devops | + assistant |

See: [Multi-Provider Strategy](../02-roles-and-teams/multi-provider-strategy.md)

### Vibecoding

Writing code by giving AI vague instructions without quality validation. Example: "make it work" without acceptance criteria, code review, or testing. The opposite of structured SDLC development. Quality gates (especially G3) exist to prevent vibecoded output from reaching production.

---

## Patterns

### Zero-Mock Policy

Absolute prohibition of mock implementations (placeholders, TODOs, stubs) in production code. Born from the [679-Mock Crisis](../05-case-studies/battle-tested-platforms.md).

### Contract-First Development

API specifications (e.g., OpenAPI) are written and agreed upon before implementation begins. Prevents integration failures.

### Process-First, Not App-First

Design workflows before writing code. Build the application to support the documented process.

### Iceberg of Change

A systems thinking model with 4 layers: Events (visible symptoms) → Patterns (recurring themes) → Structures (process gaps) → Mental Models (beliefs). Fix problems at least one level deeper than where you found them.

See: [Iceberg of Change](../01-core-concepts/iceberg-of-change.md)

---

## Tools

### TinySDLC

The MIT-licensed reference implementation of SDLC 6.1.0 at LITE tier. A multi-agent orchestrator that runs AI agents organized into teams with SDLC roles.

See: [TinySDLC Reference](../05-case-studies/tinysdlc-reference.md)

### SDLC Enterprise Framework

The complete SDLC 6.1.0 system for organizations (private, licensed). Includes full specifications, templates, governance systems, and automation patterns.

See: [LITE vs Enterprise](lite-vs-enterprise.md)

---

## See Also

- [README](../README.md) — project overview
- [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md) — stage details
- [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) — role details
- [Quality Gates](../01-core-concepts/quality-gates.md) — gate details
