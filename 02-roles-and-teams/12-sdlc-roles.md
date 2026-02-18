# 12 SDLC Roles

**SDLC Version**: 6.1.0
**Category**: Roles & Teams
**Status**: Active
**License**: MIT

---

## Overview

SDLC 6.1.0 defines **12 roles** for AI+Human software teams, organized into 3 types:

- **8 SE4A roles** (Agent Executors): researcher, pm, pjm, architect, coder, reviewer, tester, devops
- **3 SE4H roles** (Human Coaches): ceo, cpo, cto — formalized at STANDARD+ tier
- **1 Router role**: assistant — guides users to the correct agent/workflow

Each role has specific stage responsibilities, gate ownership, and constraints. These roles work with **any** AI tool or team structure. At LITE tier, the 8 SE4A roles apply as *thinking modes* for solo developers. The additional 4 roles activate at STANDARD+ tier.

---

## Role Summary

### SE4A Roles (8 Agent Executors)

| Role | Stage | Gate | Provider Tier | Key Constraint |
|------|-------|------|--------------|----------------|
| **researcher** | 00-01 | G0.1 | Deep reasoning | Investigates, never decides product direction |
| **pm** | 00-01 | G0.1, G1 | Precise analysis | Defines WHAT to build, never HOW |
| **pjm** | 01-04 | G-Sprint | Fast execution | Tracks execution, never changes scope |
| **architect** | 02-03 | G2 | Deep reasoning | Designs systems, never writes production code |
| **coder** | 04 | Sprint Gate | Fast execution | Implements, never merges without review |
| **reviewer** | 04-05 | G3 (primary) | Precise analysis | Reviews quality, never approves own code |
| **tester** | 05 | G3 (co-owner) | Fast execution | Validates quality, never modifies code to pass tests |
| **devops** | 06-07 | G4 | Fast execution | Deploys, never ships without G3 confirmation |

### SE4H Roles (3 Human Coaches — STANDARD+)

| Role | Decision Domain | Gate Authority | Provider Tier |
|------|----------------|----------------|--------------|
| **ceo** | Strategy, budget, final escalation | All gates (override) | Deep reasoning |
| **cpo** | Product vision, feature scope, priorities | G0.1, G1 | Precise analysis |
| **cto** | Architecture, security, technology | G2, G3 | Deep reasoning |

### Router Role (1 — STANDARD+)

| Role | Responsibility | Provider Tier | Constraint |
|------|---------------|--------------|-----------|
| **assistant** | Routes users to correct agent/team, explains framework | Fast execution | No decision authority, guidance only |

**Note on pm vs pjm**: These are distinct roles. The **Product Manager (pm)** owns WHAT gets built (requirements, priorities, scope). The **Project Manager (pjm)** owns WHEN and HOW MUCH (timeline, resources, sprint execution). In traditional teams, these are sometimes combined — SDLC 6.1.0 separates them for clarity.

---

## Role Details

### Researcher (`researcher`)

**Stage**: 00-Foundation, 01-Planning
**Gate**: G0.1 (Problem Validated)

**Responsibilities**:
- Conduct market research, competitive analysis, and user research
- Gather evidence for problem validation (interviews, surveys, data)
- Analyze industry trends and technology landscape
- Produce research briefs that feed into PM's requirements
- Validate assumptions with data before committing to solutions

**SE4A Constraints** (forbidden):
- Making product decisions (that's PM's role)
- Approving gates without SE4H sign-off
- Starting development based on research alone
- Presenting research as final requirements

**Communication pattern**:
> Researcher investigates → produces research brief → hands off to PM for requirements

---

### Product Manager (`pm`)

**Stage**: 00-Foundation, 01-Planning
**Gate**: G0.1 (Problem Validated), G1 (Requirements Complete)

**Responsibilities**:
- Define the problem statement and user needs
- Write requirements, user stories, and acceptance criteria
- Create and maintain the sprint plan
- Coordinate with architect for feasibility validation
- Track backlog priorities

**SE4A Constraints** (forbidden):
- Approving requirements without SE4H sign-off
- Making technology or architecture decisions
- Starting or assigning coding tasks directly

**Communication pattern**:
> PM receives feature request → analyzes → asks architect for feasibility → finalizes requirements → presents to SE4H for G1

---

### Project Manager (`pjm`)

**Stage**: 01-Planning, 02-Design, 03-Integrate, 04-Build
**Gate**: G-Sprint (Sprint Gate)

**Responsibilities**:
- Create and maintain sprint plans with task breakdown
- Track execution progress, blockers, and dependencies
- Manage timelines and resource allocation
- Run daily standups and sprint retrospectives
- Escalate risks and blockers to SE4H

**SE4A Constraints** (forbidden):
- Making product scope decisions (that's PM's role)
- Making architecture decisions (that's architect's role)
- Approving gates without SE4H sign-off
- Changing sprint scope without PM agreement

**Communication pattern**:
> PJM receives sprint plan → breaks into tasks → tracks progress → reports status to PM → escalates blockers to SE4H

---

### Solution Architect (`architect`)

**Stage**: 02-Design, 03-Integrate
**Gate**: G2 (Design Approved)

**Responsibilities**:
- Review technical feasibility of requirements
- Write Architecture Decision Records (ADRs)
- Design system architecture and component diagrams
- Define integration contracts for external services
- Review code for architectural conformance

**SE4A Constraints** (forbidden):
- Approving ADRs without SE4H/CTO sign-off
- Making product priority decisions
- Writing production implementation code
- Selecting technology without documenting the decision

**Communication pattern**:
> Architect receives feasibility request → analyzes → drafts ADR → asks reviewer for security review → presents design to SE4H for G2

---

### Developer (`coder`)

**Stage**: 04-Build
**Gate**: Sprint Gate

**Responsibilities**:
- Implement features and bug fixes per architecture and design
- Write unit tests alongside implementation
- Submit code for mandatory reviewer sign-off before merge
- Update build documentation with implementation notes

**SE4A Constraints** (forbidden):
- Merging without reviewer approval
- Introducing new dependencies without architect check
- Bypassing CI/CD gates (force push, skip verification)
- Making product decisions about scope

**Communication pattern**:
> Coder receives task → implements → writes tests → sends to reviewer for review

---

### Code Reviewer (`reviewer`)

**Stage**: 04-Build (review), 05-Test (gate)
**Gate**: G3 Ship Ready (primary owner)

**Responsibilities**:
- Review all code changes (quality, security, OWASP Top 10)
- Block merges with unresolved critical findings
- Validate test coverage against thresholds
- Co-own Gate G3 alongside tester

**SE4A Constraints** (forbidden):
- Approving own code under any circumstances
- Approving code without test coverage
- Rubber-stamping without running checks
- Approving G3 alone (requires tester co-sign + SE4H)

**OWASP Top 10 minimum checklist**:
- A01: Broken Access Control
- A02: Cryptographic Failures
- A03: Injection (SQL, command, LDAP)
- Input validation at system boundaries
- No hardcoded secrets
- Error handling doesn't leak sensitive data

**Communication pattern**:
> Reviewer receives review request → runs checklist → either sends back to coder with issues, or co-signs with tester for G3

---

### QA Tester (`tester`)

**Stage**: 05-Test
**Gate**: G3 Ship Ready (co-owner)

**Responsibilities**:
- Create test plans from requirements and acceptance criteria
- Execute test plans (unit, integration, UAT)
- Measure and report test coverage
- Co-validate Gate G3 alongside reviewer

**SE4A Constraints** (forbidden):
- Skipping coverage thresholds
- Marking G3 ready without running full test plan
- Modifying production code to make tests pass
- Approving G3 without reviewer co-sign

**Communication pattern**:
> Tester receives verify task → creates test plan → executes → either sends back to coder for missing coverage, or co-signs with reviewer for G3

---

### DevOps Engineer (`devops`)

**Stage**: 06-Deploy, 07-Operate
**Gate**: G4 (Production Ready)

**Responsibilities**:
- Set up and maintain CI/CD pipelines
- Manage deployment infrastructure and environments
- Monitor production and respond to incidents
- Write runbooks and operational documentation

**SE4A Constraints** (forbidden):
- Deploying to production without G3 confirmed
- Storing credentials in code or config files
- Making infrastructure changes affecting cost/security without SE4H notification
- Bypassing CI/CD gates without documented incident justification

**Communication pattern**:
> DevOps receives deploy request → confirms G3 sign-off → deploys to staging → smoke test → deploys to production → health check

---

## LITE Tier Guidance

At LITE tier (1-2 developers), you don't need 8 separate people. You need 8 *thinking modes*:

| When you're... | You're thinking as... |
|---------------|-----------------------|
| Researching the problem | `researcher` |
| Writing requirements | `pm` |
| Planning the sprint | `pjm` |
| Designing the architecture | `architect` |
| Writing code | `coder` |
| Reviewing your own code (after a break) | `reviewer` |
| Running tests | `tester` |
| Deploying | `devops` |

**Minimum for LITE tier**: Always pause between `coder` and `reviewer` thinking. Never review your code in the same session you wrote it.

---

## STANDARD+ Extension: The Full 12-Role Model

At **STANDARD tier and above**, SDLC 6.1.0 defines 4 additional roles — bringing the total to **12 roles across 3 types**:

| Type | Roles | Purpose |
|------|-------|---------|
| **SE4A** (Agent Executor) | researcher, pm, pjm, architect, coder, reviewer, tester, devops | Autonomous AI agents — execute tasks within delegated scope |
| **SE4H** (Agent Coach) | ceo, cpo, cto | Human decision-makers supported by AI — define intent, approve outputs, bear accountability |
| **Router** | assistant | Guides users to the correct agent or workflow — no decision authority |

### SE4H Roles (STANDARD+ Only)

| Role | Responsibility | AI Support |
|------|---------------|------------|
| **ceo** | Strategic direction, budget approval, final escalation | AI provides analysis summaries, risk assessments |
| **cpo** | Product vision, feature prioritization, requirement approval (G1) | AI drafts PRDs, competitive analysis, user research synthesis |
| **cto** | Architecture approval (G2), security sign-off, technology decisions | AI generates architecture reviews, security scans, ADR drafts |

SE4H roles are **not autonomous agents**. They represent humans who use AI as an advisor:
- `max_delegation_depth = 0` (cannot spawn sub-agents)
- Read-only tool access (analysis, not execution)
- Advisory output only (drafts, summaries, recommendations)
- All outputs require human review before action

### Router Role (STANDARD+ Only)

| Role | Responsibility | Constraint |
|------|---------------|-----------|
| **assistant** | Routes users to correct agent/team, explains SDLC framework | No decision authority, no code execution, guidance only |

### Why LITE Keeps 8 Roles

At LITE tier (1-2 developers), the 8 SE4A roles are sufficient — one person fills SE4H responsibilities directly. The additional 4 roles become valuable when:
- Team grows beyond 2 people (formalized decision authority)
- Multiple AI agents collaborate (routing and escalation needed)
- Compliance requires explicit role separation (audit trail)

**Reference**: [ADR-056 §12.5](https://github.com/Minh-Tam-Solution/SDLC-Orchestrator) — SASE Role Classification

---

## See Also

- [4 Team Archetypes](4-team-archetypes.md) — how roles organize into teams
- [Multi-Provider Strategy](multi-provider-strategy.md) — which AI model to assign per role
- [SE4H/SE4A Governance](../01-core-concepts/se4h-se4a-governance.md) — the constraint model
- [Quality Gates](../01-core-concepts/quality-gates.md) — gate ownership per role
