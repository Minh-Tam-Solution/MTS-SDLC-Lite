# Design Thinking Foundation

**SDLC Version**: 6.1.0
**Category**: Core Concept
**Status**: Active
**License**: MIT

---

## Overview

Design Thinking is the foundation of SDLC 6.1.0's early stages. It ensures you **build the RIGHT thing** before you build the thing right.

Most failed software projects don't fail because of bad code — they fail because they solve the wrong problem.

---

## The 5 Phases

```
  Empathize  →  Define  →  Ideate  →  Prototype  →  Test
     │            │           │           │            │
   Understand   Clarify     Explore     Build        Validate
   the user     the real    multiple    quickly      with real
   deeply       problem     solutions                users
```

### Phase 1: Empathize

**Goal**: Understand the user's real pain, not what they say they want.

**Methods**: User interviews, observation, data analysis, journey mapping.

**Key question**: "What does the user actually do today, and where does it hurt?"

### Phase 2: Define

**Goal**: Frame the problem clearly and specifically.

**Output**: A problem statement: "[User type] needs [outcome] because [reason], but currently [obstacle]."

**Key question**: "Are we solving the right problem?"

### Phase 3: Ideate

**Goal**: Generate multiple possible solutions before committing to one.

**Rule**: Explore at least 3 options. The first idea is rarely the best.

**Key question**: "What are the trade-offs between our options?"

### Phase 4: Prototype

**Goal**: Build the smallest possible version to test the idea.

**Rule**: If your prototype takes more than 2 weeks, it's too big.

**Key question**: "What's the minimum we need to build to learn?"

### Phase 5: Test

**Goal**: Validate with real users and data.

**Rule**: Measure outcomes, not outputs. "Users completed checkout 20% faster" > "We shipped 5 features."

**Key question**: "Does this actually solve the problem we defined?"

---

## Design Thinking x SDLC Stages

Each Design Thinking phase maps to specific SDLC stages:

| Design Thinking Phase | SDLC Stage | Gate |
|----------------------|------------|------|
| **Empathize** | 00-FOUNDATION | G0.1 (Problem Validated) |
| **Define** | 00-FOUNDATION | G0.2 (Solution Diversity) |
| **Ideate** | 01-PLANNING | G1 (Requirements Complete) |
| **Prototype** | 02-DESIGN + 03-INTEGRATE | G2 (Design Approved) |
| **Test** | 04-BUILD + 05-TEST | G3 (Ship Ready) |

Quality gates G0.1 and G0.2 are the Design Thinking gates — they force you to empathize and define before jumping to solutions.

---

## The "Build the Right Thing" Principle

```
                    ┌──────────────────────┐
                    │ Build the RIGHT      │ ← Design Thinking
                    │ thing                │   (Stages 00-01)
                    │                      │   G0.1, G0.2, G1
                    ├──────────────────────┤
                    │ Build the thing      │ ← Engineering Excellence
                    │ RIGHT                │   (Stages 02-04)
                    │                      │   G2, G-Sprint, G3
                    └──────────────────────┘
```

- **Stages 00-01** (Design Thinking): Ensure you're building the right thing
- **Stages 02-04** (Engineering): Ensure you're building it correctly

Both matter. But if you build the wrong thing perfectly, you've wasted everything.

---

## Practical Application for Small Teams

At LITE tier, Design Thinking doesn't require formal workshops or post-it walls:

| Phase | LITE Tier Version | Time |
|-------|-------------------|------|
| Empathize | Talk to 3-5 users. Ask "show me how you do X today." | 2-3 hours |
| Define | Write a 1-paragraph problem statement. | 30 minutes |
| Ideate | List 3 possible solutions with pros/cons. | 1 hour |
| Prototype | Build the smallest version that tests the riskiest assumption. | 1-2 weeks |
| Test | Show it to 3 users. Measure one metric. | 1-2 hours |

**Total time**: 1-2 days of thinking spread over 2 weeks of building.

**ROI**: This small investment prevents building the wrong thing entirely — a mistake that typically costs 2-6 months.

---

## See Also

- [10-Stage Lifecycle](10-stage-lifecycle.md) — how stages map to Design Thinking
- [Quality Gates](quality-gates.md) — G0.1 and G0.2 are Design Thinking gates
- [Founder Playbook](../03-playbooks/founder-playbook.md) — practical 3-step approach
- [Use Case Mapping Canvas](../04-templates/use-case-mapping-canvas.md) — template for mapping use cases
