# Founder Playbook

**SDLC Version**: 6.1.0
**Category**: Playbook
**Status**: Active
**License**: MIT

---

## Overview

A 3-step playbook for founders and tech leads to go from AI tool chaos to execution discipline. Works with any AI tool stack and any team size.

**Timeline**: 3-4 weeks
**Effort**: 8-12 hours total
**Result**: Structured AI+Human workflow with measurable productivity improvement

---

## The Problem You're Facing

Your team uses 5-10 AI tools. Nobody knows which tool is for what. Productivity isn't increasing proportionally to the tool budget. Every project starts from scratch with no reusable patterns.

**Root cause**: More tools does not equal more results. What's missing is a **thinking system** — a structure that tells you *when* to use *what* and *how* to validate the output.

---

## The 3-Step Solution

```
Step 1: AUDIT          Step 2: DESIGN         Step 3: STANDARDIZE
"Stop burning money"   "Start small"          "Make it replicable"
Week 1 (2 hours)       Week 2-3 (4-6 hours)   Week 4 (2-4 hours)
        │                       │                       │
        ↓                       ↓                       ↓
   Know what you have     Prove value with       Turn success into
   Kill what's wasted     1 small use case       reusable patterns
```

---

## Step 1: AUDIT (Week 1 — 2 hours)

**Objective**: Know exactly what you have, what's missing, and what's wasted.

### 1.1 List All AI Tools (30 minutes)

Create a spreadsheet with:

| Tool | Purpose (1 sentence) | Who Uses It | Frequency | Cost/month |
|------|---------------------|-------------|-----------|-----------|
| ChatGPT | Ideation and drafting | PM, Designer | Daily | $20 |
| Claude Code | Implementation | Developer | Daily | $100 |
| Cursor | Coding with AI | Developer | Daily | $20 |
| ... | ... | ... | ... | ... |

**Tip**: Send a quick team poll — "What AI tools are you using this week?" You'll discover tools you didn't know about.

### 1.2 Map Tools to SDLC Stages (45 minutes)

For each tool, identify which SDLC stage it serves:

| Stage | Question | Tools |
|-------|----------|-------|
| 00-FOUNDATION | WHY are we building this? | [tools for research, ideation] |
| 01-PLANNING | WHAT are we building? | [tools for requirements, specs] |
| 02-DESIGN | HOW will we build it? | [tools for architecture, design] |
| 03-INTEGRATE | What CONTRACTS do we need? | [tools for API design] |
| 04-BUILD | Let's BUILD it | [tools for coding, testing] |

**Red flags**:
- Tool doesn't map to any stage — **kill it**
- 3 tools doing the same job — **consolidate**
- A stage with no tool — **potential gap** (not always a problem at LITE tier)

### 1.3 Assign Owners and KPIs (30 minutes)

Every surviving tool needs:

- **Owner**: A specific person (not "the team"), responsible for training, measuring ROI, and deciding to continue or stop
- **KPI**: What success looks like (e.g., "Generate 3 PRDs per week in <1 hour each")

**Kill matrix**:

|  | Has Owner | No Owner |
|--|-----------|----------|
| **Has KPI** | KEEP | ASSIGN owner this week |
| **No KPI** | ADD KPI this week | KILL immediately |

### 1.4 Kill Orphan Tools (15 minutes)

Act on the matrix. Cut at least 20% of your tool inventory this week.

**Expected result**: From 10 tools down to 6-7 with clear purpose, ownership, and measurement.

### Step 1 Deliverables

- [ ] Tool inventory with purpose, owner, frequency, cost
- [ ] Tools mapped to SDLC stages
- [ ] Every tool has an owner + KPI, or is marked for removal
- [ ] 20%+ orphan tools killed
- [ ] Team briefed on the cleaned tool list

---

## Step 2: DESIGN (Week 2-3 — 4-6 hours)

**Objective**: Prove value with one small use case, not the entire product.

### 2.1 Pick ONE Use Case (30 minutes)

Criteria — all must be true:

- **Small**: Completable in 2 weeks or less
- **Frequent**: Team does this 3+ times per week
- **Painful**: Everyone groans when it comes up
- **Measurable**: You can track time or quality
- **Repeatable**: Will do this again and again

Good examples:
- "Idea to initial PRD draft"
- "Bug report to root cause analysis"
- "Feature request to technical spec"

Bad examples:
- "Entire product development" (too big)
- "Yearly strategic planning" (not frequent)

### 2.2 Map Through 5 SDLC Stages (1 hour)

Use the [Use Case Mapping Canvas](../04-templates/use-case-mapping-canvas.md):

```
00-FOUNDATION: Why does this use case matter?
01-PLANNING:   What's the desired outcome? How do we measure success?
02-DESIGN:     What's the step-by-step flow? Human does what? AI does what?
03-INTEGRATE:  What tools/APIs connect? What data flows between steps?
04-BUILD:      Which tools execute it? How do we test and iterate?
```

**Key**: Spend the most time on DESIGN. If the flow is clear, building is smooth.

### 2.3 Choose 1-3 AI Tools MAX (30 minutes)

For your use case:
- **Primary tool** (does 70% of the work)
- **Secondary tool** (assists or validates)
- **Optional tertiary** (special needs only)

No more than 3 tools per use case. Cognitive load from context-switching kills productivity.

### 2.4 Define Quality Gates (1 hour)

For each step in your flow, define checkpoints:

```
Gate: [After which step]
  Check: [What to verify]
  Who: [Human, AI, or automated]
  Pass: [Specific criteria]
  Fail: [What happens — rework, escalate, or skip]
```

Quality gates catch AI hallucinations before they propagate. Without gates, errors compound through every downstream step.

### 2.5 Run the Experiment (2 weeks)

Execute your use case 5-10 times following the mapped flow:

| Iteration | Time (min) | Quality (1-10) | Notes |
|-----------|-----------|----------------|-------|
| 1 (baseline) | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

**Target**: At least 30% improvement in time or quality by iteration 5.

**Expect**: Iteration 1 will be slower than usual (learning the framework). By iteration 3, you'll be at baseline. By iteration 5, you'll see the gains.

### Step 2 Deliverables

- [ ] 1 use case selected and scoped
- [ ] Use case mapped through 5 stages
- [ ] 1-3 AI tools chosen with clear roles
- [ ] Quality gates defined for key steps
- [ ] 5+ iterations run and measured
- [ ] Improvement proven (30%+ in time or quality)

---

## Step 3: STANDARDIZE (Week 4 — 2-4 hours)

**Objective**: Turn success into a reusable pattern.

### 3.1 Write a 1-Page Pattern (1 hour)

Document what worked:

```markdown
# Pattern: [Use Case Name]

**When to use**: [Trigger condition]
**Tools**: [Primary + secondary]
**Time**: [Expected duration]

## Steps
1. [Action] — [who: Human/AI] — [output]
2. [Action] — [who: Human/AI] — [output]
3. [Action] — [who: Human/AI] — [output]

## Quality Gates
- After step [X]: Check [Y]
- After step [Z]: Verify [W]

## Expected Results
- Time: [X]% faster than manual
- Quality: [X]/10 average

## Common Pitfalls
- [Pitfall 1]: [How to avoid]
- [Pitfall 2]: [How to avoid]
```

### 3.2 Save in Project Documentation (15 minutes)

```
docs/
└── 04-build/
    └── patterns/
        ├── pattern-idea-to-prd.md
        ├── pattern-bug-to-rca.md
        └── ...
```

One location. Everyone knows where to look.

### 3.3 Replicate to a 2nd Use Case (1-2 hours)

Apply the same approach to a similar use case:

1. Copy the pattern structure
2. Adjust for the new use case
3. Run 3-5 iterations
4. Measure improvement

**Expected**: The 2nd use case will show 40-50% improvement because the *method* is already learned.

### 3.4 Share Results (30 minutes)

Run a 15-minute team demo:

1. Problem before (time and quality metrics)
2. Solution (stage mapping + tools + gates)
3. Results after (measured improvement)
4. Pattern created (show the 1-page document)
5. Next steps (which use cases to apply next)

### 3.5 Schedule Monthly Review (15 minutes)

Set a recurring monthly meeting (1 hour):

- Are existing patterns still working?
- What new patterns are needed?
- Kill patterns that stopped working
- Measure total cumulative impact

This keeps the system alive — not a one-time effort.

### Step 3 Deliverables

- [ ] 1-page pattern documented
- [ ] Pattern saved in project documentation
- [ ] Pattern replicated to 2nd use case successfully
- [ ] Team demo completed
- [ ] Monthly review scheduled

---

## Expected Results Timeline

```
Week 1 (Audit):     Clarity — know what you have, kill 20% waste
Week 2-3 (Design):  Proof — 1 pattern working, 30-50% improvement
Week 4 (Standard):  Scale — pattern replicable, team adopting
Month 2:            Growth — 3-5 patterns in production
Month 3:            Culture — patterns become "how we work"
```

---

## Common Pitfalls

### "Let's audit everything at once"
Analysis paralysis. Start with tools used *this week*. Ignore dormant ones.

### "Let's design the perfect process before testing"
Perfect never ships. A 2-week experiment teaches more than a month of planning.

### "This pattern is perfect, never change it"
Context changes. Monthly review exists to kill patterns that stop working.

### "Only I can do this right"
Bus factor of one. The 1-page pattern document exists so anyone can run the process.

---

## Connection to SDLC 6.1.0

This playbook applies SDLC concepts at the simplest level:

| Playbook Step | SDLC Concept |
|---------------|-------------|
| Audit (map to stages) | [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md) |
| Design (define gates) | [Quality Gates](../01-core-concepts/quality-gates.md) |
| Design (human validates AI) | [SE4H/SE4A Governance](../01-core-concepts/se4h-se4a-governance.md) |
| Standardize (document patterns) | [Iceberg of Change](../01-core-concepts/iceberg-of-change.md) — fixing at Structure level |

---

## See Also

- [LITE Quickstart](lite-quickstart.md) — 30-minute getting started guide
- [Quick-Win Checklist](quick-win-checklist.md) — 1-week condensed version
- [Crisis to Pattern](crisis-to-pattern.md) — turning failures into reusable patterns
- [Use Case Mapping Canvas](../04-templates/use-case-mapping-canvas.md) — template for Step 2.2
