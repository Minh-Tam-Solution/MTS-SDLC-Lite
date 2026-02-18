# LITE Tier Quickstart

**SDLC Version**: 6.1.0
**Category**: Playbook
**Status**: Active
**License**: MIT

---

## Overview

Get your LITE tier SDLC running in 30 minutes. This guide takes you from zero to a structured project with proper stages, quality gates, and documentation — whether you use AI agents or work solo.

**Who this is for**: Solo developers or 2-person teams starting a new project.

**What you'll have at the end**: A project with 5 active SDLC stages, a problem statement, initial requirements, and a clear path to building.

---

## Prerequisites

- A new or existing project idea
- A text editor or IDE
- 30 minutes of focused time
- Optional: An AI coding assistant (Claude, GPT, Copilot, Cursor, Ollama, etc.)

---

## Step 1: Create the Folder Structure (5 minutes)

LITE tier uses 5 active stages. Create the corresponding folders:

```bash
mkdir -p docs/00-foundation
mkdir -p docs/01-planning
mkdir -p docs/02-design
mkdir -p docs/03-integrate
mkdir -p docs/04-build
```

```
your-project/
├── docs/
│   ├── 00-foundation/    # WHY — Problem validation
│   ├── 01-planning/      # WHAT — Requirements & scope
│   ├── 02-design/        # HOW — Architecture & decisions
│   ├── 03-integrate/     # CONTRACTS — APIs & integrations
│   └── 04-build/         # BUILD — Sprint plans & implementation
├── src/                  # Your source code
└── README.md
```

**Why 5 folders?** Each folder maps to an SDLC stage. Documents live where they belong. When someone asks "where are the requirements?", the answer is always `docs/01-planning/`.

---

## Step 2: Write the Problem Statement (10 minutes)

Create `docs/00-foundation/problem-statement.md`:

```markdown
# Problem Statement

**SDLC Version**: 6.1.0
**Stage**: 00 - FOUNDATION
**Status**: Draft

---

## Problem

[User type] needs [outcome] because [reason], but currently [obstacle].

## Evidence

- Who has this problem? (be specific)
- How often does it occur?
- What is the cost of not solving it?

## Key Assumptions

1. [Assumption about users]
2. [Assumption about market]
3. [Assumption about technology]

## Gate G0.1 — Problem Validated

- [ ] Problem is real (not hypothetical)
- [ ] Target users identified
- [ ] Evidence gathered (even informal)
- [ ] Business case exists (even rough)
```

**SE4H checkpoint**: Before moving on, ask yourself — "Am I confident this problem is worth solving?" This is Gate G0.1. At LITE tier, it's a 2-minute mental check, not a formal review.

---

## Step 3: Define Requirements (10 minutes)

Create `docs/01-planning/requirements.md`:

```markdown
# Requirements

**SDLC Version**: 6.1.0
**Stage**: 01 - PLANNING
**Status**: Draft

---

## User Stories

### Must-Have (MVP)

1. As a [user], I want to [action] so that [benefit].
   - Acceptance: [specific, testable criteria]

2. As a [user], I want to [action] so that [benefit].
   - Acceptance: [specific, testable criteria]

### Nice-to-Have (Post-MVP)

3. As a [user], I want to [action] so that [benefit].

## Non-Functional Requirements

- Performance: [target, e.g., page load < 2s]
- Security: [minimum, e.g., input validation on all forms]

## Scope

**In scope**: [what you will build]
**Out of scope**: [what you will NOT build]

## Gate G1 — Requirements Complete

- [ ] User stories have acceptance criteria
- [ ] Scope defined (in/out)
- [ ] Feasibility considered
- [ ] Priority ordered
```

**Tip**: Start with 3-5 user stories. You can always add more. Perfect is the enemy of shipped.

---

## Step 4: Choose Your Architecture (5 minutes)

Create `docs/02-design/architecture-decisions.md`:

```markdown
# Architecture Decisions

**SDLC Version**: 6.1.0
**Stage**: 02 - DESIGN
**Status**: Draft

---

## Decision 1: [Technology/Framework Choice]

**Context**: [What we're building and constraints]
**Decision**: [What we chose]
**Why**: [Reasoning — keep it to 2-3 sentences]
**Trade-offs**: [What we're giving up]

## Decision 2: [Data Storage]

**Context**: [What data we need to store]
**Decision**: [Database/storage choice]
**Why**: [Reasoning]

## Integration Points

List external services or APIs:
1. [Service] — [purpose]
2. [Service] — [purpose]

## Gate G2 — Design Approved

- [ ] Key technology choices documented
- [ ] Integration points identified
- [ ] Security considerations noted
```

**At LITE tier**, architecture decisions can be informal. The point is to write them down so you (or future you) understand *why* you chose what you chose.

---

## Step 5: Start Building (Immediately)

At this point you have:

- A validated problem (Stage 00)
- Clear requirements with acceptance criteria (Stage 01)
- Documented architecture decisions (Stage 02)

Now build. Create `docs/04-build/sprint-plan.md`:

```markdown
# Sprint Plan

**SDLC Version**: 6.1.0
**Stage**: 04 - BUILD
**Status**: Active

---

## Sprint 1 — [Theme]

**Duration**: [1-2 weeks]
**Goal**: [What will be working at the end]

### Tasks

- [ ] [Task 1] — estimated [X hours]
- [ ] [Task 2] — estimated [X hours]
- [ ] [Task 3] — estimated [X hours]

### Definition of Done

- [ ] Code written and working
- [ ] Basic tests pass
- [ ] Code reviewed (even self-review after a break)
- [ ] No hardcoded secrets
```

---

## What About Stage 03 (Integrate)?

Stage 03 is for documenting integration contracts — API specifications, third-party service configurations, data format agreements. At LITE tier:

- If your project has no external integrations yet, `docs/03-integrate/` stays empty for now
- If you're integrating an API, document the contract: endpoint, auth method, request/response format
- This becomes critical when your project grows and other people (or AI agents) need to understand the boundaries

---

## Optional: Set Up AI Agent Support

If you're using an AI coding assistant, create a project configuration:

```json
{
  "_comment": "SDLC 6.1.0 LITE tier — tool-agnostic configuration",
  "sdlc_version": "6.1.0",
  "tier": "LITE",
  "active_stages": [
    "00-foundation",
    "01-planning",
    "02-design",
    "03-integrate",
    "04-build"
  ],
  "roles": {
    "pm": { "stage": "00-01", "gate": "G0.1, G1" },
    "architect": { "stage": "02-03", "gate": "G2" },
    "coder": { "stage": "04", "gate": "Sprint Gate" },
    "reviewer": { "stage": "04-05", "gate": "G3" }
  }
}
```

For TinySDLC specifically:

```bash
# Install TinySDLC
git clone https://github.com/Minh-Tam-Solution/tinysdlc.git
cd tinysdlc && npm install && npm run build

# Apply SDLC configuration (creates 8 active SE4A agents + 4 core teams)
./tinysdlc.sh start
tinysdlc sdlc init
```

See [TinySDLC Reference](../05-case-studies/tinysdlc-reference.md) for details.

---

## The LITE Tier Mindset

At LITE tier, you don't need formal processes. You need **thinking modes**:

| When you're... | Think as... | Ask yourself... |
|----------------|-------------|-----------------|
| Defining the problem | Product Manager | Is this worth building? |
| Choosing technology | Architect | Will this scale when needed? |
| Writing code | Developer | Does this meet acceptance criteria? |
| Reviewing code | Reviewer | Would I trust this in production? |

The minimum rule: **Always pause between writing code and reviewing it.** Never review in the same session you wrote it.

---

## Quality Gates at LITE Tier

Gates are 2-minute mental checklists, not formal reviews:

| Gate | Question | When |
|------|----------|------|
| G0.1 | Is this problem real and worth solving? | Before requirements |
| G1 | Are requirements clear enough to build? | Before architecture |
| G2 | Is the architecture sound enough to code? | Before building |
| G3 | Is the code safe to ship? | Before deploying |

If you can't confidently answer "yes" — stop and fix what's missing.

---

## Next Steps

After completing this quickstart:

1. **Read** [Founder Playbook](founder-playbook.md) for a deeper 3-step adoption guide
2. **Review** [Quality Gates](../01-core-concepts/quality-gates.md) for detailed gate checklists
3. **Explore** [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) to understand role-based thinking
4. **Try** [Use Case Mapping Canvas](../04-templates/use-case-mapping-canvas.md) for mapping your first use case

---

## See Also

- [10-Stage Lifecycle](../01-core-concepts/10-stage-lifecycle.md) — the full stage model
- [4-Tier Classification](../01-core-concepts/4-tier-classification.md) — when to upgrade from LITE
- [Project Folder Structure](../04-templates/project-folder-structure.md) — complete folder reference
- [Gate Checklist Template](../04-templates/gate-checklist-template.md) — ready-to-use checklists
