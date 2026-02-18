# Project Folder Structure

**SDLC Version**: 6.1.0
**Category**: Template
**Status**: Active
**License**: MIT

---

## Overview

Every SDLC 6.1.0 project uses a standard folder structure based on the 10-stage lifecycle. Documents live where they belong — when someone asks "where are the requirements?", the answer is always `docs/01-planning/`.

---

## Full 10-Stage Structure

```
project-root/
├── docs/
│   ├── 00-foundation/        # WHY — Problem validation, research
│   │   ├── problem-statement.md
│   │   ├── market-research.md
│   │   └── stakeholder-interviews.md
│   │
│   ├── 01-planning/          # WHAT — Requirements, scope, priorities
│   │   ├── requirements.md
│   │   ├── user-stories.md
│   │   └── sprint-plan.md
│   │
│   ├── 02-design/            # HOW — Architecture, decisions
│   │   ├── architecture-overview.md
│   │   ├── architecture-decisions.md
│   │   └── system-diagram.md
│   │
│   ├── 03-integrate/         # CONTRACTS — APIs, integrations
│   │   ├── api-contracts.md
│   │   └── third-party-services.md
│   │
│   ├── 04-build/             # BUILD — Sprint execution, implementation
│   │   ├── sprint-plan.md
│   │   ├── build-notes.md
│   │   └── patterns/
│   │       └── pattern-*.md
│   │
│   ├── 05-test/              # VERIFY — Test plans, coverage
│   │   ├── test-plan.md
│   │   └── test-results.md
│   │
│   ├── 06-deploy/            # SHIP — Deployment, runbooks
│   │   ├── deployment-guide.md
│   │   └── rollback-procedure.md
│   │
│   ├── 07-operate/           # RUN — Monitoring, incidents
│   │   ├── runbook.md
│   │   └── incident-log.md
│   │
│   ├── 08-learn/             # LEARN — Retrospectives, metrics
│   │   ├── retrospective.md
│   │   └── lessons-learned.md
│   │
│   └── 09-govern/            # GOVERN — Compliance, audits
│       ├── compliance-report.md
│       └── audit-log.md
│
├── src/                      # Source code
├── tests/                    # Test code
├── .sdlc-config.json         # SDLC configuration (optional)
└── README.md                 # Project overview
```

---

## LITE Tier Subset (Recommended Starting Point)

At LITE tier (1-2 developers), you only need 5 active stages:

```
project-root/
├── docs/
│   ├── 00-foundation/        # WHY — Problem validation
│   │   └── problem-statement.md
│   │
│   ├── 01-planning/          # WHAT — Requirements
│   │   └── requirements.md
│   │
│   ├── 02-design/            # HOW — Architecture decisions
│   │   └── architecture-decisions.md
│   │
│   ├── 03-integrate/         # CONTRACTS — API specs (if applicable)
│   │   └── (empty until needed)
│   │
│   └── 04-build/             # BUILD — Sprint plans
│       └── sprint-plan.md
│
├── src/
├── README.md
└── .sdlc-config.json         # Optional
```

**Start with this.** Add stages 05-09 when your project or team grows. See [4-Tier Classification](../01-core-concepts/4-tier-classification.md) for when to upgrade.

---

## Naming Standards

### Files

- **Convention**: kebab-case (lowercase, hyphens between words)
- **No dates** in filenames (use git history)
- **No sprint numbers** in filenames (files evolve across sprints)
- **No version numbers** in filenames (use git tags)

| Good | Bad | Why |
|------|-----|-----|
| `requirements.md` | `Requirements.md` | kebab-case, not PascalCase |
| `api-contracts.md` | `API_Contracts.md` | no underscores, no capitals |
| `problem-statement.md` | `2024-01-15-problem-statement.md` | no dates in filenames |
| `sprint-plan.md` | `sprint-45-plan.md` | no sprint numbers |
| `architecture-decisions.md` | `arch-decisions-v2.md` | no version numbers |

### SDLC Document Header

Every document should include the standard header:

```markdown
# [Document Title]

**SDLC Version**: 6.1.0
**Stage**: NN - STAGE_NAME
**Status**: Draft | Active | Archived
```

---

## Stage-to-Folder Mapping

| Stage | Folder | Core Question | Key Documents |
|-------|--------|--------------|---------------|
| 00 | `00-foundation/` | WHY are we building this? | Problem statement, research, interviews |
| 01 | `01-planning/` | WHAT are we building? | Requirements, user stories, sprint plan |
| 02 | `02-design/` | HOW will we build it? | Architecture, ADRs, system diagrams |
| 03 | `03-integrate/` | What CONTRACTS do we need? | API specs, service contracts |
| 04 | `04-build/` | Let's BUILD it | Sprint plans, implementation notes, patterns |
| 05 | `05-test/` | Does it WORK correctly? | Test plans, coverage reports |
| 06 | `06-deploy/` | Can we SHIP it safely? | Deployment guides, rollback procedures |
| 07 | `07-operate/` | Is it RUNNING well? | Runbooks, monitoring, incident logs |
| 08 | `08-learn/` | What did we LEARN? | Retrospectives, metrics, improvements |
| 09 | `09-govern/` | Are we COMPLIANT? | Audit trails, compliance reports |

---

## Growth Path

As your project matures, add folders:

```
LITE tier (1-2 devs):
  docs/00-foundation/
  docs/01-planning/
  docs/02-design/
  docs/03-integrate/
  docs/04-build/

STANDARD tier (add when 3-10 people):
  + docs/05-test/        # Formal test plans
  + docs/06-deploy/      # Deployment procedures

PROFESSIONAL tier (add when 10-50 people):
  + docs/07-operate/     # Operational runbooks
  + docs/08-learn/       # Retrospectives, metrics

ENTERPRISE tier (add when 50+ people):
  + docs/09-govern/      # Compliance, audit trails
```

---

## See Also

- [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md) — what each stage covers
- [4-Tier Classification](../01-core-concepts/4-tier-classification.md) — which stages per tier
- [LITE Quickstart](../03-playbooks/lite-quickstart.md) — set up your first project
- [SDLC Config Template](sdlc-config-template.json) — machine-readable project config
