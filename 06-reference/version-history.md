# Version History

**SDLC Version**: 6.1.0
**Category**: Reference
**Status**: Active
**License**: MIT

---

## Overview

The SDLC methodology has evolved through real-world application across multiple platforms. Each version was shaped by practical lessons — the framework grew because projects demanded it.

---

## Evolution Timeline

```
2024-Q3       2024-Q4       2025-Q1       2025-Q2       2026-Q1
   │             │             │             │             │
   ▼             ▼             ▼             ▼             ▼
SDLC 4.7      SDLC 4.8      SDLC 5.0      SDLC 6.0.6   SDLC 6.1.0
Initial       Refined        4-Tier         7 Pillars     Consolidation
4 Stages      + Gates        Classification Complete      Ring 1 Slim
```

---

## SDLC 4.7 — The Starting Point (2024-Q3)

**Context**: First public release as "SDLC Lite for Startups"

**Key concepts introduced**:
- 4-stage framework: WHY → WHAT → HOW → BUILD
- Iceberg of Change model (systems thinking)
- Use Case Mapping Canvas
- 3-Step Founder Playbook (Audit → Design → Standardize)

**Platforms built with 4.7**: BFlow, NQH-Bot, MTEP

**Limitations discovered**:
- 4 stages insufficient for larger teams (no test, deploy, operate stages)
- No formal governance model (human/AI boundaries undefined)
- No tier classification (same process for solo dev and 50-person team)
- No defined quality gates (quality was ad-hoc)

---

## SDLC 4.8 — Post-Summit Refinement (2024-Q4)

**What changed**:
- Refined stage definitions based on battle-tested feedback
- Added quality gate concepts (informal, not yet formalized)
- Improved documentation standards

**Key event**: 679-Mock Crisis (NQH-Bot) — proved that quality gates are not optional

---

## SDLC 5.0 — 4-Tier Classification (2025-Q1)

**Major addition**: Tier classification system

| Tier | Team Size | Process Level |
|------|-----------|--------------|
| LITE | 1-2 | Self-assessed |
| STANDARD | 3-10 | Tech lead review |
| PROFESSIONAL | 10-50 | Formal review |
| ENTERPRISE | 50+ | Governance board |

**What changed**:
- 4 stages expanded to 10 stages (added TEST, DEPLOY, OPERATE, LEARN, GOVERN)
- Quality gates formalized (G0.1 through G4)
- Tier-appropriate process levels defined
- SE4H/SE4A governance model introduced

**Limitation**: Role definitions still informal

---

## SDLC 6.0.6 — The Complete Framework (2025-Q2)

**The complete framework** — built on 7 pillars:

### What 6.0.6 Added

1. **12 SDLC Roles**: 8 SE4A agents (researcher, pm, pjm, architect, coder, reviewer, tester, devops) + 3 SE4H advisors (ceo, cpo, cto) + 1 Router (assistant) — with defined stage ownership, gate ownership, and SE4A/SE4H constraints

2. **6 Team Archetypes**: 4 core (planning, dev, qa, fullstack) + 2 STANDARD+ (executive, support) — with leaders, members, and communication patterns

3. **Multi-Provider Strategy**: 3-tier model assignment (deep reasoning, precise analysis, fast execution) with extended 4-3-5 split at STANDARD+

4. **Design Thinking Foundation**: Integration of Design Thinking phases with SDLC stages (Empathize → Define → Ideate → Prototype → Test)

5. **Formalized Gate Ownership**: Each gate has specific role owners and human approval requirements

6. **pm vs pjm Separation**: Product Manager (WHAT) explicitly separated from Project Manager (WHEN)

7. **LITE Tier Refinement**: 5 active stages (00-04, including 03-INTEGRATE) with "thinking modes" model for solo developers

---

## SDLC 6.1.0 — Consolidation Release (2026-Q1, Current)

**Ring 1 Consolidation** — cleaner separation, dedicated foundation documents, multi-agent patterns:

### What 6.1.0 Changed

1. **Ring 1 Monolith Slim**: Design Thinking 2,018→364 lines, Agentic Core 1,313→293 lines — cleaner separation of principles vs. templates

2. **System Thinking Foundation**: Dedicated standalone document for the 4-Layer Iceberg Model and 6 Mental Models (core concept since SDLC 4.0)

3. **Crisis-to-Pattern Methodology**: Extracted from Design Thinking into standalone 5-step pipeline document

4. **Multi-Agent Patterns**: NEW — 10 battle-tested collaboration patterns (lane queues, failover chains, snapshot precedence)

5. **Agentic Docs Reorganization**: Moved to AI Governance section (correct ring placement)

6. **Terminology Cleanup**: BRS/MTS/LPS deprecated → AGENTS.md (industry-standard naming)

### Why 6.1.0

No breaking changes — additive consolidation with internal reorganization. The 6.0.6 content is preserved but better organized.

---

## MTS-SDLC-Lite Versions

### v0.1.0 (2024-Q3) — Initial Release

- 4-stage framework (WHY/WHAT/HOW/BUILD)
- Vietnamese primary language
- Based on SDLC 4.7/4.8
- 12 files in 5 sections

### v1.0.0 (2025-Q2) — Community Edition (Current)

- Complete overhaul to SDLC 6.1.0
- English primary language
- 10-stage lifecycle (5 active at LITE tier)
- 12 roles, 6 teams, quality gates, SE4H/SE4A
- Multi-provider AI strategy
- 25+ files across 6 sections
- Tool-agnostic methodology
- TinySDLC as reference implementation

---

## What Drove Each Change

| Version | Trigger | Key Lesson |
|---------|---------|-----------|
| 4.7 → 4.8 | 679-Mock Crisis | Quality gates are mandatory, not optional |
| 4.8 → 5.0 | Team scaling challenges | Same process for 1 person and 50 fails — need tier classification |
| 5.0 → 6.0.6 | TinySDLC implementation | Roles, teams, and model assignment need formal definitions |
| 6.0.6 → 6.1.0 | Ring 1 document growth | Core docs too large; foundation concepts need standalone documents |

Each version was driven by practical need, not theoretical improvement. The framework only grew when real projects demanded it.

---

## See Also

- [CHANGELOG](../CHANGELOG.md) — detailed release notes
- [Battle-Tested Platforms](../05-case-studies/battle-tested-platforms.md) — the projects that shaped the framework
- [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md) — the current stage model
- [4-Tier Classification](../01-core-concepts/4-tier-classification.md) — the tier system
