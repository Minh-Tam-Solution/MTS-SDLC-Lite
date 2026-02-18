# LITE vs Enterprise

**SDLC Version**: 6.1.0
**Category**: Reference
**Status**: Active
**License**: MIT

---

## Overview

MTS-SDLC-Lite (this repository) teaches SDLC 6.1.0 **concepts** — the methodology that makes AI+Human teams effective. The full SDLC Enterprise Framework provides complete **specifications, templates, and governance systems** for larger organizations.

This page helps you understand what's covered at each level and when to consider upgrading.

---

## What This Repository Covers

MTS-SDLC-Lite is the **community edition** — free, open-source (MIT), designed to teach SDLC concepts to anyone.

| Category | What's Included |
|----------|----------------|
| **Lifecycle** | 10 stage names, core questions, deliverables, stage dependencies |
| **Classification** | 4 tier definitions (LITE through ENTERPRISE) with team size ranges |
| **Governance** | SE4H/SE4A concept, human-approves / agent-executes model |
| **Quality Gates** | Gate names (G0.1-G4, G-Sprint), purposes, basic checklists |
| **Roles** | 12 role names (8 SE4A + 3 SE4H + 1 Router), stage/gate ownership, SE4A constraints, LITE tier "thinking modes" |
| **Teams** | 6 team archetypes (4 core + 2 STANDARD+), compositions, leaders, interaction patterns |
| **AI Strategy** | Multi-provider concept (2-2-4 split), cost optimization principles |
| **Playbooks** | Quickstart, Founder Playbook, Quick-Win Checklist, Crisis-to-Pattern |
| **Templates** | Folder structure, use case canvas, config template, gate checklists |
| **Case Studies** | BFlow, NQH-Bot, MTEP, 679-Mock Crisis |
| **Reference** | TinySDLC implementation guide, glossary |

---

## What the Enterprise Framework Adds

The SDLC Enterprise Framework (private, licensed per organization) provides the complete system for teams of 10-500+.

| Category | Enterprise Addition |
|----------|-------------------|
| **Lifecycle** | Full stage exit criteria with measurable thresholds per tier |
| **Governance** | Complete Sprint Governance system, advanced enforcement workflows |
| **Quality Assurance** | Advanced quality scoring, automated detection systems |
| **Specifications** | Full specification standards, compliance templates |
| **Security** | Advanced security review templates and formal architecture review |
| **AI Governance** | Advanced AI governance model, codegen patterns |
| **Documentation** | Full naming standards, RACI matrices, collaboration templates |
| **Automation** | Policy engine integration, evidence vault design, CI/CD gate enforcement |

---

## Side-by-Side Comparison

| Feature | LITE (This Repo) | Enterprise Framework |
|---------|------------------|---------------------|
| **License** | MIT (free, open-source) | Per-organization license |
| **Audience** | Solo developers, small teams, learners | Engineering organizations (10-500+) |
| **Stages** | 10 stage names + questions | 10 stages + full exit criteria + dependency matrix |
| **Gates** | Gate names + basic checklists | Gates + measurable thresholds + evidence requirements |
| **Roles** | 8 SE4A roles (+ 4 STANDARD+ documented) | 12 roles (8 SE4A + 3 SE4H + 1 Router) + RACI matrix |
| **Teams** | 6 archetypes + compositions | 6 archetypes + full communication matrix + escalation paths |
| **Governance** | SE4H/SE4A concept | SE4H/SE4A + advanced enforcement + override queues |
| **Quality** | Basic review checklists | Advanced quality scoring + automated detection |
| **Templates** | Starter templates | Full production templates (50+ documents) |
| **AI Integration** | Model assignment concepts | Advanced AI governance + codegen patterns |
| **Security** | OWASP Top 10 checklist | Advanced security review templates |
| **Compliance** | Self-assessed gates | Automated compliance + evidence vault + audit trails |

---

## When to Upgrade

### Stay at LITE When

- You're 1-2 developers learning SDLC concepts
- Your project is in early stages (MVP, prototype)
- You need a thinking framework, not a governance system
- You're teaching SDLC to your team

### Consider STANDARD When

- Your team grows to 3-10 people
- You need formal code review processes
- You're deploying to production with real users
- You want written gate sign-offs (not just mental checks)

### Consider PROFESSIONAL When

- Your team is 10-50 people
- You need CTO/tech lead gate approval workflows
- You're handling sensitive data or regulated industries
- You want automated compliance checking

### Consider ENTERPRISE When

- Your organization has 50+ engineers
- You need board-level governance and audit trails
- You're in regulated industries (finance, healthcare, government)
- You need automated evidence collection and policy enforcement

---

## The SDLC Ecosystem

SDLC 6.1.0 has **2 layers** (methodology + implementation) across **2 tiers** (community + enterprise):

```
                 METHODOLOGY                       IMPLEMENTATION
                 (what to do)                       (how to run it)

COMMUNITY   MTS-SDLC-Lite (MIT)             ←→    TinySDLC (MIT)
TIER        "Learn the concepts"                   "See it running"

ENTERPRISE  SDLC Enterprise Framework       ←→    Your Platform
TIER        "Full methodology at scale"            • SDLC Orchestrator (by MTS)
             Licensed per organization              • Your custom platform
                                                    • Any SDLC-compatible tooling
```

**Key principle**: The methodology layer is **independent** of any implementation. Any organization can license the SDLC Enterprise Framework and build their own platform. SDLC Orchestrator is MTS's own implementation — one of potentially many.

| Product | Layer | License |
|---------|-------|---------|
| **MTS-SDLC-Lite** | Methodology (community) | MIT |
| **TinySDLC** | Implementation (community) | MIT |
| **SDLC Enterprise Framework 6.1.0** | Methodology (enterprise) | Per-org license |
| **SDLC Orchestrator** | Implementation (enterprise, by MTS) | Proprietary |

---

## Getting Started

1. **Read** this repository's [README](../README.md) to understand the concepts
2. **Try** [TinySDLC](https://github.com/Minh-Tam-Solution/tinysdlc) to see the concepts in practice
3. **Apply** the [LITE Quickstart](../03-playbooks/lite-quickstart.md) to your own project
4. **Contact** MTS when your team is ready for Enterprise: [GitHub](https://github.com/Minh-Tam-Solution)

---

## See Also

- [4-Tier Classification](../01-core-concepts/4-tier-classification.md) — detailed tier descriptions
- [TinySDLC Reference](../05-case-studies/tinysdlc-reference.md) — implementation details
- [LITE Quickstart](../03-playbooks/lite-quickstart.md) — get started immediately
