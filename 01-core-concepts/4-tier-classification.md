# 4-Tier Classification

**SDLC Version**: 6.1.0
**Category**: Core Concept
**Status**: Active
**License**: MIT

---

## Overview

Not every project needs the same level of process. SDLC 6.1.0 defines 4 tiers based on team size, each with appropriate stages, documentation, and gate formality. Start with the tier that fits — upgrade when you grow.

---

## The 4 Tiers

| Tier | Team Size | Active Stages | Documentation | Gate Formality |
|------|-----------|---------------|---------------|----------------|
| **LITE** | 1-2 developers | 00, 01, 02, 03, 04 | README + `docs/` basics | Self-assessed |
| **STANDARD** | 3-10 developers | 00-06 | + ADRs + CLAUDE.md | Tech Lead review |
| **PROFESSIONAL** | 10-50 developers | All 10 stages | + Full specifications | CTO sign-off |
| **ENTERPRISE** | 50+ developers | All 10 stages | + Executive reports | Board-level governance |

---

## LITE Tier (1-2 Developers)

**You are here.** MTS-SDLC-Lite focuses on LITE and STANDARD tiers.

### Active Stages
```
00-FOUNDATION    → Problem statement (even 1 paragraph)
01-PLANNING      → Requirements (even a bullet list)
02-DESIGN        → Architecture (even a diagram on paper)
03-INTEGRATE     → API contracts (even rough notes)
04-BUILD         → Code + tests
```

### Minimum Documentation
```
project/
├── README.md                    # What this project does
├── .env.example                 # Environment variables
└── docs/
    ├── 00-foundation/
    │   └── problem-statement.md
    ├── 01-planning/
    │   └── requirements.md
    ├── 02-design/
    │   └── architecture.md
    ├── 03-integrate/
    │   └── integrations.md
    └── 04-build/
        └── setup-guide.md
```

### Gate Formality
- **Self-assessed**: You review your own gates before moving forward
- Use the [Gate Checklist Template](../04-templates/gate-checklist-template.md) as a guide
- At LITE tier, a 2-minute mental checklist is sufficient

### When to Use
- Side projects, prototypes, MVPs
- Solo developer or pair programming
- Early-stage startups (pre-product-market-fit)
- Internal tools with limited users

---

## STANDARD Tier (3-10 Developers)

### Additional Stages
- **05-TEST**: Formal test plans and coverage tracking
- **06-DEPLOY**: Deployment runbooks and CI/CD

### Additional Documentation
- Architecture Decision Records (ADRs)
- CLAUDE.md (or equivalent AI assistant config)
- Sprint plans with task breakdown
- Code review checklists

### Gate Formality
- **Tech Lead review**: Gates require at least one other person's sign-off
- Reviewer and tester roles become explicit (not just "thinking modes")
- G3 (Ship Ready) requires both code review and test coverage

### When to Upgrade from LITE
- Team grows beyond 2 people
- Multiple feature branches running in parallel
- External users depend on your software
- You're spending time onboarding new team members

---

## PROFESSIONAL Tier (10-50 Developers)

### All 10 Stages Active
- Stages 07-09 (Operate, Collaborate, Govern) become formal
- Dedicated DevOps and QA roles

### Additional Documentation
- Full specification documents (YAML frontmatter, BDD format)
- Security assessments and compliance reports
- Incident response runbooks
- Architecture review boards

### Gate Formality
- **CTO sign-off**: Critical gates (G2, G3) require senior leadership
- Formal sprint retrospectives
- Automated gate enforcement in CI/CD

---

## ENTERPRISE Tier (50+ Developers)

### Full Governance
- Executive reporting and dashboards
- Cross-team coordination frameworks
- Regulatory compliance (SOC 2, HIPAA, etc.)
- Budget and resource governance

### Additional Documentation
- Executive status reports
- Risk registers
- Audit trails
- Vendor management documents

### Gate Formality
- **Board-level governance**: Major gates involve executive sign-off
- Automated policy enforcement (Policy-as-Code)
- Evidence vault for audit compliance

---

## Choose Your Tier

```
Start here:
          │
          ▼
    ┌─────────────┐
    │ How many     │
    │ developers?  │
    └──────┬──────┘
           │
    ┌──────┼──────────────────┐
    │      │                  │
   1-2    3-10              10+
    │      │                  │
    ▼      ▼                  ▼
  LITE   STANDARD    ┌───────┼───────┐
                    10-50           50+
                     │               │
                     ▼               ▼
                PROFESSIONAL     ENTERPRISE
```

**Rule of thumb**: When in doubt, start one tier lower than you think you need. It's easier to add process than to remove it.

---

## Growth Path

Moving up tiers is a gradual process, not a switch:

1. **LITE → STANDARD**: Add a reviewer. Formalize your sprint plan. Write ADRs for key decisions.
2. **STANDARD → PROFESSIONAL**: Add dedicated QA. Automate gate checks in CI/CD. Write specifications.
3. **PROFESSIONAL → ENTERPRISE**: Add governance dashboards. Implement policy-as-code. Set up audit trails.

Each transition takes 2-4 weeks of process setup. The SDLC Enterprise Framework (proprietary) provides detailed transition guides.

---

## See Also

- [10-Stage Lifecycle](10-stage-lifecycle.md) — which stages each tier activates
- [Quality Gates](quality-gates.md) — gate formality per tier
- [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) — which roles are needed per tier
- [Lite vs Enterprise](../06-reference/lite-vs-enterprise.md) — what the Enterprise framework adds
