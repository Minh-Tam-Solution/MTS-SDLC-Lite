# 10-Stage Software Lifecycle

**SDLC Version**: 6.1.0
**Category**: Core Concept
**Status**: Active
**License**: MIT

---

## Overview

Every software project — from a weekend prototype to an enterprise platform — moves through the same lifecycle. SDLC 6.1.0 defines 10 stages, each answering a specific question.

Skipping early stages (00-02) is the #1 cause of wasted work. The earlier you invest in clarity, the less you rework later.

---

## The 10 Stages

```
                    ┌─────────────────────────────────────┐
                    │     THE 10-STAGE LIFECYCLE           │
                    │         SDLC 6.1.0                   │
                    └─────────────────────────────────────┘

  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐
  │    00    │──▶│    01    │──▶│    02    │──▶│    03    │──▶│    04    │
  │FOUNDATION│   │ PLANNING │   │  DESIGN  │   │INTEGRATE │   │  BUILD   │
  │   WHY?   │   │  WHAT?   │   │   HOW?   │   │WITH WHAT?│   │  DO IT   │
  └──────────┘   └──────────┘   └──────────┘   └──────────┘   └──────────┘
                                                                    │
  ┌──────────┐   ┌──────────┐   ┌──────────┐   ┌──────────┐        │
  │    09    │   │    08    │   │    07    │   │    06    │   ┌──────────┐
  │  GOVERN  │   │COLLABORATE│   │ OPERATE  │◀──│  DEPLOY  │◀──│    05    │
  │ COMPLIANT│   │ TOGETHER │   │KEEP ALIVE│   │  SHIP IT │   │   TEST   │
  └──────────┘   └──────────┘   └──────────┘   └──────────┘   │DOES WORK?│
       │              │                                         └──────────┘
       └──────────────┘ (can start early from Stage 01)
```

---

## Stage Reference

| # | Stage | Core Question | Primary Deliverable | Folder |
|---|-------|---------------|---------------------|--------|
| 00 | **FOUNDATION** | WHY are we building this? | Problem statement, stakeholder analysis | `docs/00-foundation/` |
| 01 | **PLANNING** | WHAT will we build? | Requirements, user stories, sprint plan | `docs/01-planning/` |
| 02 | **DESIGN** | HOW will we build it? | Architecture, ADRs, system design | `docs/02-design/` |
| 03 | **INTEGRATE** | WITH WHAT systems/services? | API contracts, third-party integrations | `docs/03-integrate/` |
| 04 | **BUILD** | DO IT — implement the solution | Working code, unit tests, implementation notes | `docs/04-build/` |
| 05 | **TEST** | DOES IT WORK correctly? | Test plans, coverage reports, QA sign-off | `docs/05-test/` |
| 06 | **DEPLOY** | SHIP IT to users | Deployment runbooks, release notes | `docs/06-deploy/` |
| 07 | **OPERATE** | KEEP IT RUNNING in production | Monitoring, incident response, runbooks | `docs/07-operate/` |
| 08 | **COLLABORATE** | WORK TOGETHER effectively | Team communication, knowledge sharing | `docs/08-collaborate/` |
| 09 | **GOVERN** | STAY COMPLIANT and aligned | Compliance reports, audits, strategic reviews | `docs/09-govern/` |

---

## LITE Tier: 5 Active Stages

At LITE tier (1-2 developers), you activate **5 stages**:

```
 [active]  00-FOUNDATION    WHY?        → Problem statement
 [active]  01-PLANNING      WHAT?       → Requirements + user stories
 [active]  02-DESIGN        HOW?        → Architecture decisions
 [active]  03-INTEGRATE     WITH WHAT?  → API contracts + integrations
 [active]  04-BUILD         DO IT       → Implementation + tests
 --------  05-TEST          (covered inline during BUILD at LITE tier)
 --------  06-DEPLOY        (manual deployment at LITE tier)
 --------  07-OPERATE       (basic monitoring at LITE tier)
 --------  08-COLLABORATE   (informal at LITE tier)
 --------  09-GOVERN        (not required at LITE tier)
```

Stages 05-09 are not skipped — they happen informally. LITE tier means you don't need formal documentation for them. As your team grows, activate more stages.

---

## Mapping from the Old 4-Stage Model

If you learned the earlier MTS-SDLC-Lite (v0.1.0), here's how it maps:

| Old 4-Stage Name | SDLC 6.1.0 Stage(s) | Stage Numbers |
|-------------------|---------------------|--------------|
| **WHY** (Foundation) | FOUNDATION | 00 |
| **WHAT** (Plan & Analyze) | PLANNING | 01 |
| **HOW** (Design & Architect) | DESIGN + INTEGRATE | 02 + 03 |
| **BUILD** (Do It) | BUILD | 04 |

The 10-stage model is an expansion, not a replacement. Your existing 4-stage knowledge maps directly — you gain awareness of stages 05-09 that you'll add when your team grows.

---

## Stage Dependencies

Stages must be completed in order for their primary deliverables. Some stages can overlap:

```
Sequential flow:
  00 → 01 → 02 → 03 ──┐
                        ├──▶ 04 → 05 → 06 → 07
                        │
  (03 and 04 can run in parallel for different features)

Early start:
  08-COLLABORATE can start from Stage 01 (team coordination is ongoing)
  09-GOVERN can start early if you're in a regulated industry
```

**Key rule**: Never start BUILD (04) before DESIGN (02) is at least drafted. This prevents the #1 failure mode: building the wrong thing.

---

## Quality Gates Between Stages

Each stage transition has a quality gate that must be approved by SE4H (human):

| Gate | Between | What It Validates |
|------|---------|-------------------|
| **G0.1** | 00 → 01 | Problem is validated, worth solving |
| **G0.2** | 00 → 01 | Solution diversity explored (not just first idea) |
| **G1** | 01 → 02 | Requirements complete, feasible |
| **G2** | 02 → 04 | Design approved, contracts defined |
| **G-Sprint** | During 04 | Sprint deliverables meet acceptance criteria |
| **G3** | 04 → 06 | Code reviewed, tested, ship-ready |
| **G4** | 06 → 07 | Deployed successfully, monitoring active |

At LITE tier, gates are self-assessed. At higher tiers, gates require formal sign-off from designated roles.

Read more: [Quality Gates](quality-gates.md) | [SE4H/SE4A Governance](se4h-se4a-governance.md)

---

## Self-Assessment Checklist

Use this to evaluate where your project stands:

### Stage 00: FOUNDATION
- [ ] Problem statement written (who has the problem, what it is, why it matters)
- [ ] Target users identified
- [ ] Key assumptions listed

### Stage 01: PLANNING
- [ ] At least 5 user stories written
- [ ] Acceptance criteria defined for each story
- [ ] Sprint plan or task breakdown exists

### Stage 02: DESIGN
- [ ] Architecture documented (even a simple diagram)
- [ ] Key decisions recorded (even informal ADRs)
- [ ] Technology choices justified

### Stage 03: INTEGRATE
- [ ] Third-party services identified
- [ ] API contracts documented (even rough ones)
- [ ] Integration approach decided

### Stage 04: BUILD
- [ ] Code follows the architecture from Stage 02
- [ ] Tests exist for critical paths
- [ ] Code has been reviewed (even self-review)

**Score**: Count your checkmarks. 0-5 = early stage, 6-10 = solid foundation, 11-15 = well-structured project.

---

## See Also

- [4-Tier Classification](4-tier-classification.md) — choose the right level of formality
- [Quality Gates](quality-gates.md) — gate details and ownership
- [LITE Quickstart](../03-playbooks/lite-quickstart.md) — set up the 5-stage structure in 30 minutes
- [Project Folder Structure](../04-templates/project-folder-structure.md) — ready-to-use folder template
