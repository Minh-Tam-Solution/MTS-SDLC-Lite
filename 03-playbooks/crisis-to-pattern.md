# Crisis to Pattern

**SDLC Version**: 6.1.0
**Category**: Playbook
**Status**: Active
**License**: MIT

---

## Overview

Every crisis is a pattern waiting to be extracted. This playbook shows you how to turn production failures, quality incidents, and team breakdowns into reusable, enforceable patterns that prevent entire categories of problems.

The formula: **Crisis → Policy → Automation → Enforcement → Document**

---

## The 5-Step Process

```
Step 1: DIAGNOSE        → Analyze at the right level (not just symptoms)
Step 2: CREATE POLICY   → Write the principle that prevents recurrence
Step 3: AUTOMATE        → Build tooling that enforces the policy
Step 4: ENFORCE         → Make violation impossible (not just discouraged)
Step 5: DOCUMENT        → Record the pattern for reuse across projects
```

---

## Step 1: DIAGNOSE — Find the Real Problem

When a crisis hits, resist the urge to fix the symptom. Use the [Iceberg of Change](../01-core-concepts/iceberg-of-change.md) model:

```
What happened?           → EVENT (visible symptom)
Has this happened before?→ PATTERN (recurring theme)
What allowed it?         → STRUCTURE (process gap)
What belief caused this? → MENTAL MODEL (team assumption)
```

**The rule**: Fix at one level deeper than where you found the problem.

- If you see an **event** → look for the **pattern**
- If you see a **pattern** → fix the **structure**
- If the **structure** keeps failing → change the **mental model**

### Diagnostic Questions

Ask these in order:

1. **What happened?** (Describe the incident factually)
2. **When did it start?** (Not when it was discovered — when did the root cause begin?)
3. **How many times has something similar happened?** (Look for patterns)
4. **What process was supposed to prevent this?** (Identify the structural gap)
5. **What did the team believe that made this possible?** (Surface the mental model)

---

## Step 2: CREATE POLICY — Write the Principle

A policy is a clear, enforceable statement that prevents the diagnosed problem class.

**Format**:

```
Policy: [Name]
Principle: [One-sentence rule]
Rationale: [Why this matters — reference the crisis]
Scope: [Where this applies]
Enforcement: [How it will be enforced]
```

**Good policies are**:
- Absolute (not "try to" or "when possible")
- Measurable (can verify compliance)
- Automatable (machines can enforce them)

**Bad policies**: "Be careful with mocks" (vague, not enforceable)
**Good policies**: "Zero mock implementations in production code. All external dependencies use real integrations or contract-validated test doubles." (specific, enforceable)

---

## Step 3: AUTOMATE — Build the Tooling

A policy without automation relies on human memory. Human memory fails under pressure.

**Automation ladder** (from least to most reliable):

| Level | Method | Reliability |
|-------|--------|-------------|
| 1 | Documentation only | Low — people forget |
| 2 | Checklist in code review | Medium — reviewers miss things |
| 3 | Pre-commit hook | High — blocks before commit |
| 4 | CI/CD pipeline gate | Very high — blocks before merge |
| 5 | Runtime enforcement | Highest — blocks in production |

**Target**: Level 3 or higher. If a human has to remember to check it, it will eventually be forgotten.

---

## Step 4: ENFORCE — Make Violation Impossible

The difference between "policy" and "pattern" is enforcement:

- **Policy** = "We should do X" → gets forgotten
- **Pattern** = "The system prevents not-X" → always works

**Enforcement checklist**:

- [ ] Can a developer bypass this enforcement? (If yes, add another layer)
- [ ] Does CI/CD block non-compliant code? (If no, add a pipeline check)
- [ ] Is there an escape hatch for emergencies? (If no, add one with approval requirement)
- [ ] Is the enforcement documented? (If no, new team members will be confused)

---

## Step 5: DOCUMENT — Record for Reuse

The pattern exists so the *next* project starts with the solution, not the crisis.

**Pattern template**:

```markdown
# Pattern: [Name]

## Origin
Crisis: [What happened]
Date: [When]
Impact: [How bad was it]

## Diagnosis
Event: [What was visible]
Pattern: [What kept recurring]
Structure: [What process was missing]
Mental Model: [What belief caused this]

## Policy
[One-sentence principle]

## Enforcement
- Pre-commit: [What hook runs]
- CI/CD: [What pipeline check runs]
- Runtime: [What production check runs, if any]

## Verification
How to confirm this pattern is working:
- [ ] [Check 1]
- [ ] [Check 2]

## Applicability
When to apply this pattern to a new project:
- [Condition 1]
- [Condition 2]
```

---

## Real-World Examples

### Example 1: 679-Mock Crisis (NQH-Bot)

**What happened**: A production platform's operational success rate dropped to 78%. Investigation revealed 679 mock implementations scattered across the codebase, inserted over 4 months.

**Diagnosis**:
- Event: 78% failure rate in production
- Pattern: Mock count grew gradually (undetected for months)
- Structure: No detection mechanism, no code review checklist for mocks
- Mental Model: "Mocks are acceptable shortcuts for development speed"

**Policy**: Zero-Mock Policy — absolute prohibition of mock implementations in production code. All integrations use real services or contract-validated test doubles.

**Automation**:
- Pre-commit hook: Scans for mock patterns (`mock`, `TODO`, `placeholder`, `stub`)
- CI/CD gate: Blocks PRs containing mock indicators
- Code review checklist: Mock pattern scan as mandatory item

**Result**: 78% → 95% operational success in 48 hours. Pattern now applied to all new projects from day 1.

---

### Example 2: API Contract Breaks (BFlow)

**What happened**: A critical API (TreeNode) broke during integration, causing cascading failures across dependent services.

**Diagnosis**:
- Event: TreeNode API returned unexpected response format
- Pattern: API contracts changed without notification to consumers
- Structure: No contract validation between services
- Mental Model: "Internal APIs don't need formal contracts"

**Policy**: Contract-First Development — all API endpoints must have an OpenAPI specification written and agreed upon *before* implementation begins. Changes require consumer notification.

**Automation**:
- Pre-commit: OpenAPI spec validation (schema correctness)
- CI/CD: Contract compatibility check (breaking change detection)
- Integration tests: Real API calls validated against OpenAPI spec

**Result**: 45-minute resolution (fix the structure, not just the broken endpoint). No recurring API contract breaks.

---

### Example 3: Naming Chaos (Cross-Project)

**What happened**: Documents across multiple projects used inconsistent naming (PascalCase, snake_case, spaces, Vietnamese, English). Finding anything required tribal knowledge.

**Diagnosis**:
- Event: Team members couldn't find documents
- Pattern: Every person named files differently
- Structure: No naming standard existed
- Mental Model: "File names don't matter, content matters"

**Policy**: kebab-case naming standard for all documentation. No dates, sprint numbers, or version numbers in filenames.

**Automation**:
- Pre-commit: Filename validation (regex check for kebab-case)
- Template: All new files created from templates with correct naming

**Result**: Any team member can find any document by guessing the kebab-case name. Onboarding time for document navigation cut by 50%.

---

## When to Use This Playbook

| Trigger | Action |
|---------|--------|
| Production incident | Run full 5-step process |
| Same bug category appears 3+ times | Diagnose the pattern, create policy |
| Code review catches the same issue repeatedly | Automate the check |
| New project starting | Review existing patterns, apply relevant ones from day 1 |
| Monthly review | Check if existing patterns are still relevant |

---

## Connection to SDLC 6.1.0

This playbook embodies several SDLC principles:

| Playbook Step | SDLC Concept |
|---------------|-------------|
| Diagnose (Iceberg levels) | [Iceberg of Change](../01-core-concepts/iceberg-of-change.md) |
| Create Policy (governance) | [SE4H/SE4A Governance](../01-core-concepts/se4h-se4a-governance.md) |
| Enforce (quality gates) | [Quality Gates](../01-core-concepts/quality-gates.md) — especially G3 |
| Document (patterns) | [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md) — Stage 08 Learn |

---

## See Also

- [Iceberg of Change](../01-core-concepts/iceberg-of-change.md) — the diagnostic model
- [Quality Gates](../01-core-concepts/quality-gates.md) — gate enforcement details
- [Battle-Tested Platforms](../05-case-studies/battle-tested-platforms.md) — full case studies
- [Founder Playbook](founder-playbook.md) — broader adoption guide
