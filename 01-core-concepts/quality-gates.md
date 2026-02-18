# Quality Gates

**SDLC Version**: 6.1.0
**Category**: Core Concept
**Status**: Active
**License**: MIT

---

## Overview

Quality gates are checkpoints between stages that prevent teams from moving forward with incomplete or low-quality work. Each gate has defined criteria, designated owners, and requires SE4H (human) approval.

Gates are guardrails, not bureaucracy. They exist because the cost of catching issues early is 10-100x less than fixing them in production.

---

## Feature Gates

Feature gates validate deliverables at stage transitions.

| Gate | Name | Between Stages | What It Validates |
|------|------|---------------|-------------------|
| **G0.1** | Problem Validated | 00 → 01 | The problem is real, worth solving, evidence gathered |
| **G0.2** | Solution Diversity | 00 → 01 | Multiple solutions explored (not just the first idea) |
| **G1** | Requirements Complete | 01 → 02 | Requirements are clear, feasible, with acceptance criteria |
| **G2** | Design Approved | 02 → 04 | Architecture is sound, contracts defined, risks identified |
| **G3** | Ship Ready | 04 → 06 | Code reviewed, tested, security checked, ready to deploy |
| **G4** | Production Ready | 06 → 07 | Deployed successfully, monitoring active, rollback tested |

---

## Sprint Gate

The Sprint Gate validates sprint-level deliverables during the BUILD stage.

| Gate | Name | When | What It Validates |
|------|------|------|-------------------|
| **G-Sprint** | Sprint Gate | During Stage 04 | Sprint deliverables meet acceptance criteria, tasks complete |

---

## Gate Ownership by Role

Each gate has designated owners who prepare the evidence, and an approver (SE4H) who makes the final call.

| Gate | Owner(s) | Approver |
|------|---------|----------|
| G0.1 | researcher, pm | SE4H |
| G0.2 | pm, architect | SE4H |
| G1 | pm, architect | SE4H |
| G-Sprint | pjm, coder | SE4H |
| G2 | architect, reviewer | SE4H / CTO |
| G3 | reviewer (primary), tester (co-owner) | SE4H |
| G4 | devops | SE4H |

**Critical rule**: G3 (Ship Ready) requires **both** reviewer AND tester sign-off. This is not optional, even at LITE tier (where one person may wear both hats).

---

## Gate Formality by Tier

| Tier | Gate Process | Evidence Required |
|------|-------------|-------------------|
| **LITE** | Self-assessed (2-minute mental checklist) | Minimal — "did I check these things?" |
| **STANDARD** | Tech Lead review (written sign-off) | Written — PR review, test report |
| **PROFESSIONAL** | CTO sign-off for G2/G3 (formal review) | Formal — specification compliance, audit trail |
| **ENTERPRISE** | Board-level governance (automated + manual) | Full — evidence vault, policy engine, compliance report |

---

## Gate Details

### G0.1 — Problem Validated

**Purpose**: Ensure you're solving a real problem before investing in solutions.

**Checklist**:
- [ ] Problem statement written (who, what, why)
- [ ] Target users identified
- [ ] Evidence gathered (interviews, data, market research)
- [ ] Business case exists (even informal: "this saves us X hours/week")
- [ ] Key assumptions listed

**Common failure**: Team jumps to building before validating the problem. 60-70% of features built this way are never used.

### G1 — Requirements Complete

**Purpose**: Ensure requirements are clear enough to design a solution.

**Checklist**:
- [ ] User stories written with acceptance criteria
- [ ] Non-functional requirements identified (performance, security)
- [ ] Scope defined (what's in, what's out)
- [ ] Feasibility confirmed by architect
- [ ] Priority ordered (must-have vs nice-to-have)

### G2 — Design Approved

**Purpose**: Ensure the architecture is sound before writing code.

**Checklist**:
- [ ] Architecture documented (system diagram, component design)
- [ ] Key decisions recorded (ADRs or informal decision log)
- [ ] Integration points identified (APIs, third-party services)
- [ ] Security considerations addressed
- [ ] Technology choices justified

### G3 — Ship Ready

**Purpose**: Ensure the code is production-quality before deployment.

**Checklist**:
- [ ] Code reviewed by reviewer (OWASP Top 10 at minimum)
- [ ] Tests pass with adequate coverage
- [ ] No critical or high-severity bugs open
- [ ] Security scan clean (no hardcoded secrets, no injection vulnerabilities)
- [ ] Documentation updated
- [ ] Tester sign-off (test plan executed, acceptance criteria met)

**G3 is the most critical gate**. Skipping it is the #1 cause of production incidents.

### G4 — Production Ready

**Purpose**: Ensure the deployment is safe and monitored.

**Checklist**:
- [ ] Staging deployment successful
- [ ] Rollback procedure documented and tested
- [ ] Monitoring and alerts configured
- [ ] No secrets in configuration files
- [ ] Post-deploy smoke test passing

---

## What Happens When a Gate Fails

Gates are not punishments — they are learning opportunities.

```
Gate fails:
  │
  ├── Identify what's missing
  │     └── "Requirements lack acceptance criteria for edge cases"
  │
  ├── Fix the gap
  │     └── Add missing acceptance criteria, re-review
  │
  ├── Re-assess the gate
  │     └── Run the checklist again
  │
  └── Document the pattern
        └── "We consistently miss edge cases → add edge-case prompt to G1 checklist"
```

A failed gate today prevents a production incident tomorrow.

---

## Connection to the 679-Mock Crisis

The 679-Mock Crisis (see [Case Studies](../05-case-studies/battle-tested-platforms.md)) happened because there was **no G3 gate**:

- AI-generated code contained 679 mock implementations
- No code review caught the pattern
- No test coverage requirement existed
- Mocks reached production, causing 78% failure rate

**After adding G3 with Zero-Mock Policy**:
- Mock detection automated in pre-commit hooks
- Code review checklist includes mock pattern scan
- Test coverage required before merge
- Result: 78% → 95% operational success in 48 hours

**Lesson**: One well-designed gate prevents entire categories of failures.

---

## See Also

- [SE4H/SE4A Governance](se4h-se4a-governance.md) — who approves gates
- [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) — gate ownership per role
- [Gate Checklist Template](../04-templates/gate-checklist-template.md) — ready-to-use checklists
- [10-Stage Lifecycle](10-stage-lifecycle.md) — where gates sit in the lifecycle
