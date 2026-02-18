# Iceberg of Change

**SDLC Version**: 6.1.0
**Category**: Core Concept
**Status**: Active
**License**: MIT

---

## Overview

Most teams operate at the surface level — reacting to bugs, fires, and urgent requests. The Iceberg of Change model reveals 4 layers of organizational depth. The deepest layers produce the most lasting impact.

This is the system thinking foundation of SDLC 6.1.0.

---

## The 4 Layers

```
┌──────────────────────────────────────────────────┐
│                                                  │
│  LAYER 1: EVENTS (Visible)                       │
│  Symptoms: bugs, fires, ad-hoc tool adoption     │
│  Response: Reactive — fix the immediate problem   │
│                                                  │
├──────────────────────────────────────────────────┤
│                                                  │
│  LAYER 2: PATTERNS (Visible)                     │
│  Trends: recurring issues, repeated failures     │
│  Response: Recognize — identify what repeats      │
│                                                  │
├──────────────────────────── waterline ───────────┤
│                                                  │
│  LAYER 3: STRUCTURES (Hidden)                    │
│  Systems: processes, roles, quality gates,       │
│           team organization, documentation       │
│  Response: Design — create systems that prevent   │
│                                                  │
├──────────────────────────────────────────────────┤
│                                                  │
│  LAYER 4: MENTAL MODELS (Hidden)                 │
│  Principles: process-first, data-from-activities,│
│              SE4H/SE4A governance, system thinking│
│  Response: Transform — change how people think    │
│                                                  │
└──────────────────────────────────────────────────┘
```

**Key insight**: Teams that win play at Layers 3 and 4 (Structures and Mental Models), not just Layers 1 and 2 (Events and Patterns).

---

## Layer 1: Events

**What you see**: Individual incidents — a bug in production, an AI tool that didn't work, a missed deadline.

**Typical response**: Fix the bug. Switch tools. Work overtime.

**Problem**: You'll be fixing the same types of issues forever because the root cause is deeper.

**Example**: Your AI coding assistant generates code with 15 bugs. You fix each bug manually.

---

## Layer 2: Patterns

**What you see**: Recurring themes — "AI always generates buggy auth code", "we always miss sprint deadlines", "every project starts without requirements."

**Typical response**: Create a checklist. Add a review step. "Be more careful next time."

**Problem**: Checklists help but don't prevent the issues from occurring.

**Example**: You notice AI-generated code fails most often in authentication and database queries. You create a "review checklist" for these areas.

---

## Layer 3: Structures

**What you build**: Systems that prevent issues by design — quality gates, defined roles, documentation standards, automated checks.

**This is where SDLC 6.1.0 operates**: The 10-stage lifecycle, 12 roles, quality gates, and SE4H/SE4A governance are all structural interventions.

**Impact**: Issues are prevented before they occur. New team members inherit good practices automatically.

**Example**: You implement Gate G3 (Ship Ready) requiring both code review and test coverage before deployment. AI-generated bugs are caught before they reach production — by structure, not by heroism.

---

## Layer 4: Mental Models

**What you change**: How people think about software development — "process-first, not tool-first", "humans decide, agents execute", "crisis is an asset if documented."

**This is the deepest and most powerful layer.**

**SDLC 6.1.0 Mental Models**:

| Mental Model | What It Means |
|-------------|---------------|
| **Process-First** | Design the process before choosing tools |
| **SE4H/SE4A** | Humans decide, agents execute — never the reverse |
| **Data-From-Activities** | Trusted data comes from operational activities, not manual entry |
| **Design for Change** | Build composable systems with guardrails, not rigid monoliths |
| **Crisis → Pattern** | Every failure is a future asset if you document it correctly |
| **Start Ridiculously Small** | 1 use case, 2 weeks, measurable results — then scale |

---

## Real Example: The 679-Mock Crisis

**Layer 1 (Event)**: Production system failing — 679 mock implementations discovered, 78% operational success rate.

**Layer 2 (Pattern)**: AI tools consistently generated placeholder code that looked real but didn't work. This happened across multiple sprints.

**Layer 3 (Structure)**: Response within 48 hours:
1. **Zero-Mock Policy** — explicit rule: no `// TODO`, no `return { mock: true }`
2. **Mock Detection Agent** — automated scanner that flags mock patterns
3. **Pre-commit Hook** — blocks commits containing mock patterns
4. Result: 78% → 95% operational success

**Layer 4 (Mental Model)**: The crisis became a reusable principle:
- "If AI can generate it wrong, AI will generate it wrong — unless you have a gate."
- This principle now applies to every new project, not just the one that failed.
- The Zero-Mock Policy became an organizational asset, not a one-time fix.

**The pattern**: `Crisis → Policy → Automation → Enforcement → Document → Reuse`

Read more: [Crisis to Pattern Playbook](../03-playbooks/crisis-to-pattern.md)

---

## Applying the Iceberg to Your Team

### Step 1: Diagnose Your Current Layer

Ask yourself:
- Are you constantly firefighting? → You're at **Layer 1**
- Do you recognize recurring issues but can't stop them? → You're at **Layer 2**
- Do you have systems that prevent issues by design? → You're at **Layer 3**
- Does your team think in terms of process, not tools? → You're at **Layer 4**

### Step 2: Move One Layer Deeper

Don't try to jump from Layer 1 to Layer 4. Move one layer at a time:

| Current | Next Step | Time Investment |
|---------|-----------|----------------|
| Layer 1 (Events) | Start tracking patterns — what repeats? | 30 min/week |
| Layer 2 (Patterns) | Create one structural intervention (e.g., a quality gate) | 2-4 hours |
| Layer 3 (Structures) | Codify the mental model behind your best structure | 1-2 hours |
| Layer 4 (Mental Models) | Share and teach the model to new team members | Ongoing |

### Step 3: Use SDLC 6.1.0 as Your Structure Layer

The 10-stage lifecycle, 12 roles, and quality gates are pre-built structural interventions. You don't need to invent your own — adopt the framework and customize it to your context.

---

## Connection to SDLC 6.1.0

| Iceberg Layer | SDLC 6.1.0 Concept |
|-------------|---------------------|
| Events | Individual bugs, missed deadlines, tool failures |
| Patterns | Recurring types of issues across sprints |
| **Structures** | **10 stages, 12 roles, quality gates, SE4H/SE4A governance** |
| **Mental Models** | **Process-first, humans decide agents execute, crisis→pattern** |

SDLC 6.1.0 is primarily a **Layer 3 + Layer 4 intervention** — it changes both the structures (how you work) and the mental models (how you think about work).

---

## See Also

- [SE4H/SE4A Governance](se4h-se4a-governance.md) — the governance mental model
- [Quality Gates](quality-gates.md) — structural interventions between stages
- [Crisis to Pattern](../03-playbooks/crisis-to-pattern.md) — turning Layer 1 events into Layer 3 structures
- [Founder Playbook](../03-playbooks/founder-playbook.md) — practical steps to move deeper
