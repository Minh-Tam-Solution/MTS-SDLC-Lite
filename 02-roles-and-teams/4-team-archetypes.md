# 4 Team Archetypes

**SDLC Version**: 6.0.6
**Category**: Roles & Teams
**Status**: Active
**License**: MIT

---

## Overview

SDLC 6.0.6 defines 4 pre-configured team archetypes aligned with lifecycle stages. Each team has a leader (first point of contact), defined members, and clear stage/gate ownership.

Teams enable structured collaboration — agents (or humans) communicate through defined channels, not ad-hoc chaos.

---

## Team Summary

```
User (SE4H)
    │
    ├── @planning  → [researcher → pm → pjm → architect]           Stage 00-01
    ├── @dev       → [coder → reviewer]                             Stage 04-05
    ├── @qa        → [tester → reviewer]                            Stage 05
    └── @fullstack → [researcher → pm → pjm → architect → coder → reviewer]  All stages
```

---

## Team 1: Planning

**Composition**: researcher, pm (leader), pjm, architect
**Stages**: 00-Foundation, 01-Planning
**Gates**: G0.1 (Problem Validated), G1 (Requirements Complete)

```
User: "I want to add voice message support"
  └── pm (leader): analyzes scope, assigns research
        └── researcher: investigates market need, technical landscape
              └── pm: writes requirements from research
                    └── architect: reviews technical feasibility
                          └── pjm: creates sprint plan
                                └── pm: presents to SE4H for G1 approval
```

**When to use**:
- Starting a new project or feature
- Clarifying requirements before development
- Prioritizing backlog items
- Creating sprint plans

---

## Team 2: Dev

**Composition**: coder (leader), reviewer
**Stages**: 04-Build, 05-Test (review)
**Gates**: Sprint Gate, G3 contribution

```
User: "Fix the authentication bug"
  └── coder (leader): implements fix, writes tests
        └── reviewer: OWASP check, coverage check
              ├── if issues: sends back to coder with findings
              └── if clean: LGTM — ready for G3
```

**When to use**:
- Implementing features from sprint plan
- Fixing bugs
- Code review requests

---

## Team 3: QA

**Composition**: tester (leader), reviewer
**Stages**: 05-Test
**Gates**: G3 (Ship Ready) — **required, not optional**

```
User: "Validate the auth module for G3"
  └── tester (leader): creates test plan, executes, measures coverage
        ├── if coverage insufficient: sends back to coder with missing areas
        └── if coverage met: sends to reviewer for security review
              └── reviewer: OWASP check, security scan
                    └── both co-sign G3 → presents to SE4H for approval
```

**Critical**: This team is **required** when targeting Gate G3 Ship Ready. G3 requires both reviewer AND tester sign-off.

**When to use**:
- End-of-sprint validation
- Pre-release verification
- Security audit requests

---

## Team 4: Fullstack (LITE Tier)

**Composition**: researcher, pm (leader), pjm, architect, coder, reviewer
**Stages**: 00 through 05 — simplified pipeline
**Gates**: All gates (simplified)

```
User: "Add a new /status command"
  └── pm (leader): analyzes scope
        └── researcher: quick research
        └── architect: feasibility check
        └── pjm: task breakdown
        └── coder: implements
              └── reviewer: reviews
```

**When to use**:
- Small projects (1-2 developers, LITE tier)
- Tasks that don't warrant separate planning/dev/qa phases
- Rapid prototyping

**Limitations**:
- Does not include `tester` or `devops` — cannot fulfill G3 or G4 formally
- Suitable for internal tools or early-stage projects
- Upgrade to separate teams when project matures

---

## Standalone Usage

Some roles work well as standalone queries (not routed through a team):

| Role | Usage |
|------|-------|
| `researcher` | Quick research or competitive analysis |
| `architect` | Quick architectural consultation |
| `reviewer` | Ad-hoc security review of a code snippet |
| `devops` | Infrastructure or deployment question |

---

## Team Collaboration Rules

1. Messages to a team route to the **leader** first
2. The leader can delegate to any teammate
3. Teammates can delegate to each other within the same team
4. Cross-team delegation is not supported (route back through SE4H)
5. Maximum 50 messages per conversation (loop prevention safety net)

---

## Setting Up Teams

### With TinySDLC (Reference Implementation)

```bash
tinysdlc sdlc init    # Creates all 8 agents + 4 teams
tinysdlc sdlc status  # Verify configuration
```

### Manual Configuration (Any Tool)

Define teams in your project configuration:

```json
{
  "teams": {
    "planning": {
      "name": "Planning Team",
      "agents": ["researcher", "pm", "pjm", "architect"],
      "leader_agent": "pm"
    },
    "dev": {
      "name": "Development Team",
      "agents": ["coder", "reviewer"],
      "leader_agent": "coder"
    },
    "qa": {
      "name": "QA Team",
      "agents": ["tester", "reviewer"],
      "leader_agent": "tester"
    },
    "fullstack": {
      "name": "Full Stack Team",
      "agents": ["researcher", "pm", "pjm", "architect", "coder", "reviewer"],
      "leader_agent": "pm"
    }
  }
}
```

---

## See Also

- [8 SDLC Roles](8-sdlc-roles.md) — role details and SE4A constraints
- [Multi-Provider Strategy](multi-provider-strategy.md) — model assignment per role
- [TinySDLC Reference](../05-case-studies/tinysdlc-reference.md) — teams in practice
