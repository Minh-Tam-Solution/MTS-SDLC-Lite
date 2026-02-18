# Gate Checklist Template

**SDLC Version**: 6.1.0
**Category**: Template
**Status**: Active
**License**: MIT

---

## Overview

Ready-to-use checklists for each quality gate. Copy the relevant section when your project reaches a gate. At LITE tier, these are 2-minute mental checks. At higher tiers, they become formal review documents.

For gate theory and ownership details, see [Quality Gates](../01-core-concepts/quality-gates.md).

---

## Gate G0.1 — Problem Validated

**Between stages**: 00-FOUNDATION → 01-PLANNING
**Owners**: researcher, pm
**Approver**: SE4H (human decision maker)

### Checklist

- [ ] **Problem statement written**: Who has the problem, what is it, why does it matter?
- [ ] **Target users identified**: Specific user type, not "everyone"
- [ ] **Evidence gathered**: At least one of: user interviews, survey data, market research, support tickets, personal experience
- [ ] **Business case exists**: Even informal — "this saves X hours/week" or "Y users need this"
- [ ] **Key assumptions listed**: What are we assuming to be true? What could invalidate our approach?

### Pass Criteria

The problem is real, specific, and worth solving. Evidence supports the need. Assumptions are explicit (not hidden).

### Common Failure Reasons

- Problem is hypothetical ("users might want...")
- No evidence beyond the team's own opinion
- Problem is too broad ("improve productivity")
- No business case articulated

---

## Gate G0.2 — Solution Diversity

**Between stages**: 00-FOUNDATION → 01-PLANNING
**Owners**: pm, architect
**Approver**: SE4H

### Checklist

- [ ] **Multiple solutions explored**: At least 3 options considered (not just the first idea)
- [ ] **Trade-offs documented**: Pros and cons for each option
- [ ] **Selection rationale clear**: Why the chosen approach over alternatives
- [ ] **Build vs buy evaluated**: Considered existing tools/libraries before building custom

### Pass Criteria

The team explored options before committing. The chosen solution has a documented rationale, not just "it felt right."

### Common Failure Reasons

- Only one solution considered (the obvious one)
- Trade-offs not examined
- Decision made by authority ("CTO said so") without documented reasoning

---

## Gate G1 — Requirements Complete

**Between stages**: 01-PLANNING → 02-DESIGN
**Owners**: pm, architect
**Approver**: SE4H

### Checklist

- [ ] **User stories written**: Each with acceptance criteria (testable conditions)
- [ ] **Non-functional requirements identified**: Performance targets, security needs, accessibility
- [ ] **Scope defined**: Clear "in scope" and "out of scope" lists
- [ ] **Feasibility confirmed**: Architect has reviewed and says "this is buildable"
- [ ] **Priority ordered**: Must-have vs nice-to-have distinguished

### Pass Criteria

Requirements are clear enough that a developer could start designing a solution. Acceptance criteria are specific enough to write tests against.

### Common Failure Reasons

- User stories lack acceptance criteria ("As a user, I want it to work well")
- Scope is vague or keeps changing
- No feasibility check — requirements may be technically impossible
- Everything marked as "must-have" (no prioritization)

---

## Gate G2 — Design Approved

**Between stages**: 02-DESIGN → 04-BUILD
**Owners**: architect, reviewer
**Approver**: SE4H / CTO

### Checklist

- [ ] **Architecture documented**: System diagram showing major components and their relationships
- [ ] **Key decisions recorded**: Architecture Decision Records (ADRs) or informal decision log with rationale
- [ ] **Integration points identified**: External APIs, third-party services, data sources
- [ ] **Security considerations addressed**: Authentication, authorization, data protection basics
- [ ] **Technology choices justified**: Why these tools/frameworks over alternatives

### Pass Criteria

The architecture is sound enough to start coding. Key decisions are documented (not just in someone's head). Security isn't an afterthought.

### Common Failure Reasons

- No architecture diagram (just "we'll figure it out while coding")
- Technology choices made without documented reasoning
- Security not considered until after development
- Integration dependencies not identified (discovered during build)

---

## Gate G-Sprint — Sprint Gate

**During stage**: 04-BUILD
**Owners**: pjm, coder
**Approver**: SE4H

### Checklist

- [ ] **Sprint goal met**: The committed deliverables are complete
- [ ] **Acceptance criteria satisfied**: Each completed story passes its criteria
- [ ] **Code compiles and runs**: No broken builds
- [ ] **Basic tests pass**: Unit tests for new code
- [ ] **No known blockers**: Nothing preventing the next sprint

### Pass Criteria

Sprint deliverables work as specified. The team can move to the next sprint without carrying critical debt.

### Common Failure Reasons

- Sprint goal partially met but declared "done"
- Acceptance criteria not actually tested
- Known bugs deferred without tracking

---

## Gate G3 — Ship Ready

**Between stages**: 04-BUILD → 06-DEPLOY
**Owners**: reviewer (primary), tester (co-owner)
**Approver**: SE4H

**This is the most critical gate. Both reviewer AND tester must sign off.**

### Checklist

- [ ] **Code reviewed**: All changes reviewed by someone who didn't write them
- [ ] **OWASP Top 10 checked** (minimum security review):
  - [ ] A01: No broken access control
  - [ ] A02: No cryptographic failures
  - [ ] A03: No injection vulnerabilities (SQL, command, XSS)
  - [ ] Input validation on all external inputs
  - [ ] No hardcoded secrets (API keys, passwords, tokens)
  - [ ] Error handling doesn't leak sensitive data
- [ ] **Tests pass**: All automated tests green
- [ ] **Test coverage adequate**: Coverage meets project threshold
- [ ] **No critical bugs open**: Zero P0/P1 issues unresolved
- [ ] **Documentation updated**: README, API docs, deployment notes current
- [ ] **Tester sign-off**: Test plan executed, acceptance criteria validated

### Pass Criteria

Code is production-quality. Security baseline met. Tests pass. Both reviewer and tester confirm readiness. Human (SE4H) gives final approval.

### Common Failure Reasons

- Self-review only ("I reviewed my own code")
- Security check skipped ("we'll do it later")
- Tests failing but ignored ("it works on my machine")
- No tester involvement (reviewer alone is not sufficient for G3)

### The 679-Mock Lesson

The [679-Mock Crisis](../05-case-studies/battle-tested-platforms.md) happened because G3 didn't exist. AI-generated code contained 679 mock implementations. No review caught them. No tests verified real integrations. The result was 78% failure in production. After adding G3 with a Zero-Mock Policy, success went from 78% to 95% in 48 hours.

---

## Gate G4 — Production Ready

**Between stages**: 06-DEPLOY → 07-OPERATE
**Owners**: devops
**Approver**: SE4H

### Checklist

- [ ] **Staging deployment successful**: Deployed to a staging environment first
- [ ] **Rollback procedure documented and tested**: Can revert within defined time window
- [ ] **Monitoring configured**: Alerts set for key metrics (errors, latency, availability)
- [ ] **No secrets in configuration files**: All secrets in environment variables or vault
- [ ] **Post-deploy smoke test passing**: Critical user paths verified after deployment

### Pass Criteria

Deployment is safe, monitored, and reversible. The team can detect problems and roll back quickly if needed.

### Common Failure Reasons

- Deployed directly to production (skipped staging)
- No rollback procedure (or procedure never tested)
- No monitoring (problems discovered by users, not alerts)
- Secrets committed to repository

---

## Gate Formality by Tier

| Tier | How to Use These Checklists |
|------|---------------------------|
| **LITE** | 2-minute mental check. Read the checklist, answer honestly, move on. |
| **STANDARD** | Written sign-off. Tech lead reviews checklist, documents pass/fail. |
| **PROFESSIONAL** | Formal review meeting. CTO/tech lead approves G2/G3 with evidence. |
| **ENTERPRISE** | Automated + manual. Pipeline enforces checks, governance board approves. |

---

## How to Use

### For a New Project

1. Copy the relevant gate checklist when you reach that stage transition
2. Fill in the checklist honestly
3. If any item fails, fix it before proceeding
4. At LITE tier, this is a self-assessment — no formal approval needed beyond your own honesty

### For an Ongoing Project

1. Review G3 before every deployment
2. Review G-Sprint at the end of each sprint
3. Review G0.1/G1 when starting new features

### For Team Adoption

1. Print or bookmark this page
2. Make gate review part of your sprint ceremony
3. Track which gates fail most often — those are your process gaps

---

## See Also

- [Quality Gates](../01-core-concepts/quality-gates.md) — theory, ownership, and failure handling
- [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) — who owns which gate
- [SE4H/SE4A Governance](../01-core-concepts/se4h-se4a-governance.md) — why humans approve gates
- [Crisis to Pattern](../03-playbooks/crisis-to-pattern.md) — what to do when gates fail
