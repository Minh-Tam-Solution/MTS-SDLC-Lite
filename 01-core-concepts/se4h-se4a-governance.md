# SE4H / SE4A Governance Model

**SDLC Version**: 6.1.0
**Category**: Core Concept
**Status**: Active
**License**: MIT

---

## Overview

The most important principle in SDLC 6.1.0: **humans decide, agents execute**.

SE4H/SE4A is a governance model that defines the boundary between human authority and AI capability. It ensures that AI tools amplify human decision-making without replacing it.

---

## The Two Roles

| Role | Full Name | Who | Authority |
|------|-----------|-----|-----------|
| **SE4H** | Software Engineer for Human | You — the developer, PM, CTO, team lead | **Full** — approves gates, validates deliverables, makes decisions |
| **SE4A** | Software Engineer for Agent | AI tools — Claude, GPT, Copilot, Cursor, Ollama, any AI | **None** — proposes, implements, analyzes, but never self-approves |

---

## Why This Matters

### The Problem: Vibecoding

Without SE4H/SE4A governance, teams fall into "vibecoding" — letting AI generate code without human oversight:

```
Without governance:
  User: "Build a login system"
  AI: generates 500 lines of code
  User: ships it without review
  Result: security vulnerabilities, hardcoded secrets, no tests

With SE4H/SE4A:
  User (SE4H): "Build a login system"
  AI (SE4A): proposes architecture, implements code, writes tests
  User (SE4H): reviews design, validates security, approves gate
  Result: reviewed, tested, secure code
```

### The Principle

AI tools are powerful executors but unreliable decision-makers. They can:
- Write code faster than humans
- Generate comprehensive test suites
- Analyze large codebases

They cannot:
- Judge whether the right problem is being solved
- Evaluate business trade-offs
- Take responsibility for production failures
- Approve their own quality

**SE4H/SE4A makes this explicit**: agents produce, humans validate.

---

## SE4H Responsibilities

The human coach (SE4H) is responsible for:

| Responsibility | Example |
|----------------|---------|
| **Define goals** | "We need to reduce checkout abandonment by 20%" |
| **Validate deliverables** | Review AI-generated architecture before implementation |
| **Approve quality gates** | Sign off on G3 (Ship Ready) after reviewing tests |
| **Make product decisions** | "We'll support 3 payment methods, not 5" |
| **Resolve conflicts** | When reviewer and coder disagree, SE4H decides |
| **Accept risk** | "We'll ship with known limitation X, fix in next sprint" |

### SE4H Rules
1. **Never delegate gate approval to AI** — even if the AI says "all checks pass"
2. **Review before trust** — AI output is a draft until SE4H validates it
3. **Own the outcome** — if it breaks in production, SE4H is accountable (not the AI)

---

## SE4A Constraints

Every AI agent (SE4A) operates under constraints:

| Constraint | What It Means |
|-----------|---------------|
| **No self-approval** | An agent cannot approve its own work |
| **No gate sign-off** | Only SE4H can approve quality gates |
| **Propose, don't decide** | Agents suggest solutions; humans choose |
| **Stay in lane** | Each role has defined boundaries (pm doesn't write code, coder doesn't merge without review) |
| **Document, don't hide** | Agents must surface uncertainties, not suppress them |

### Per-Role SE4A Examples

| Role | Can Do | Cannot Do |
|------|--------|-----------|
| **pm** | Write requirements, create user stories | Approve requirements without SE4H |
| **architect** | Design systems, write ADRs | Select technology without documenting why |
| **coder** | Implement features, write tests | Merge without reviewer approval |
| **reviewer** | Review code, flag security issues | Approve own code |
| **tester** | Create test plans, measure coverage | Mark G3 ready without running tests |
| **devops** | Set up pipelines, deploy | Ship without G3 confirmation |

---

## Applying SE4H/SE4A

### For Solo Developers

Even when you're the only person, SE4H/SE4A applies as *thinking modes*:

```
You (as SE4H): "I need to solve the cart abandonment problem"
You (using AI as SE4A): "Generate 3 architecture options"
AI: produces 3 options with trade-offs
You (as SE4H): "Option 2 fits our constraints. Implement it."
AI: implements Option 2
You (as SE4H): review code, run tests, approve gate
```

The key: **pause between AI output and action**. That pause is where SE4H governance happens.

### For Teams with AI Agents

When using multi-agent systems (like TinySDLC), SE4A constraints are encoded in each agent's role template:

```
Team: @planning
  pm (SE4A): writes requirements → presents to user (SE4H) for approval
  architect (SE4A): reviews feasibility → presents to user (SE4H) for G2

Team: @dev
  coder (SE4A): implements → sends to reviewer (SE4A)
  reviewer (SE4A): reviews → presents to user (SE4H) for merge approval
```

Every chain ends at SE4H. Agents never close the loop without human validation.

### For AI Tool Configuration

If your AI tool supports system prompts or configuration, encode SE4A constraints:

```markdown
## Your Role
You are a Software Engineer for Agent (SE4A). You:
- Propose solutions, never make final decisions
- Present options with trade-offs, never hide uncertainty
- Request human review for all deliverables
- Never approve your own work or close quality gates
```

---

## SE4H/SE4A and Quality Gates

Every quality gate is an SE4H checkpoint:

| Gate | SE4A Prepares | SE4H Approves |
|------|--------------|---------------|
| G0.1 | Research brief, problem analysis | "Yes, this problem is worth solving" |
| G1 | Requirements document, user stories | "Yes, these requirements are complete" |
| G2 | Architecture design, ADRs | "Yes, this design is sound" |
| G3 | Code review report, test coverage | "Yes, this is ship-ready" |
| G4 | Deployment checklist, monitoring setup | "Yes, deploy to production" |

**An agent saying "all checks pass" is NOT the same as SE4H approval.** The human must review the evidence and make the call.

---

## Connection to the Iceberg Model

SE4H/SE4A operates at the deepest layers of the [Iceberg of Change](iceberg-of-change.md):

| Layer | SE4H/SE4A Application |
|-------|----------------------|
| Events | Individual AI mistakes (bugs, wrong code) |
| Patterns | AI consistently makes certain types of errors |
| **Structures** | **Quality gates, role constraints, review processes** |
| **Mental Models** | **"Humans decide, agents execute" — the SE4H/SE4A principle** |

By operating at Layers 3 and 4, SE4H/SE4A prevents entire categories of issues — not just individual bugs.

---

## STANDARD+ Extension: Formalized SE4H Roles

At LITE tier, SE4H is simply "the human" — you, the developer. At **STANDARD tier and above**, SDLC 6.1.0 formalizes SE4H into 3 distinct roles with AI advisory support:

| SE4H Role | Decision Domain | Gate Authority | AI Advisory Support |
|-----------|----------------|----------------|---------------------|
| **ceo** | Strategy, budget, final escalation | All gates (override) | Risk analysis, market summaries, executive dashboards |
| **cpo** | Product vision, feature scope, priorities | G0.1, G1 | PRD drafts, competitive analysis, user research synthesis |
| **cto** | Architecture, security, technology choices | G2, G3 | Architecture reviews, security scans, ADR drafts, code quality reports |

### How SE4H Roles Use AI

SE4H roles are **humans with AI advisors**, not autonomous agents. The AI:
- Prepares analysis and drafts (SE4A-style execution)
- Presents options with trade-offs (never decides)
- Summarizes evidence for gate reviews
- Generates reports for human consumption

The human SE4H:
- Reviews AI-prepared materials critically
- Makes the final decision (approve/reject/modify)
- Bears accountability for outcomes
- Signs VCR (Version Controlled Resolution) for audit trail

### When to Formalize SE4H

| Trigger | Action |
|---------|--------|
| Team grows to 3+ people | Assign explicit cpo (product decisions) and cto (technical decisions) |
| Multiple AI agents collaborating | SE4H roles provide escalation targets for CRP (Consultation Request Protocol) |
| Compliance/audit requirements | Formalized roles create clear accountability chain |
| Solo developer (LITE tier) | Keep it simple — you are all 3 SE4H roles in one |

**Reference**: [12 SDLC Roles — STANDARD+ Extension](../02-roles-and-teams/12-sdlc-roles.md#standard-extension-the-full-12-role-model)

---

## See Also

- [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) — SE4A constraints per role
- [Quality Gates](quality-gates.md) — SE4H approval points
- [Iceberg of Change](iceberg-of-change.md) — system thinking foundation
- [TinySDLC Reference](../05-case-studies/tinysdlc-reference.md) — SE4H/SE4A in practice
