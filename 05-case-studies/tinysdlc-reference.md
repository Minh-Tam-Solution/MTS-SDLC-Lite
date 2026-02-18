# TinySDLC Reference Implementation

**SDLC Version**: 6.1.0
**Category**: Case Study
**Status**: Active
**License**: MIT

---

## Overview

TinySDLC is the **reference implementation** of SDLC 6.1.0 at LITE tier. It's an open-source multi-agent orchestrator that runs AI agents organized into teams with SDLC roles.

**Important**: TinySDLC is ONE implementation of SDLC 6.1.0. The SDLC methodology is tool-agnostic — you can implement it with any AI tool (Claude, GPT, Copilot, Cursor, Ollama) or without AI entirely. TinySDLC is the MTS reference implementation, not the only valid approach.

**Repository**: [github.com/Minh-Tam-Solution/tinysdlc](https://github.com/Minh-Tam-Solution/tinysdlc)
**License**: MIT

---

## What TinySDLC Implements

### 8 Active SE4A Agents

TinySDLC creates 8 AI agents (the SE4A roles), each assigned an SDLC role:

| Agent | SDLC Role | Stage | AI Provider Tier |
|-------|-----------|-------|-----------------|
| researcher | Researcher | 00-01 | Deep Reasoning |
| pm | Product Manager | 00-01 | Precise Analysis |
| pjm | Project Manager | 01-04 | Fast Execution |
| architect | Solution Architect | 02-03 | Deep Reasoning |
| coder | Developer | 04 | Fast Execution |
| reviewer | Code Reviewer | 04-05 | Precise Analysis |
| tester | QA Tester | 05 | Fast Execution |
| devops | DevOps Engineer | 06-07 | Fast Execution |

Each agent gets:
- An isolated workspace directory
- A role-specific system prompt (defining responsibilities and constraints)
- SE4A constraints (what the agent is forbidden from doing)
- A configured AI provider and model

### 4 Team Archetypes

Agents are organized into teams with defined leaders and communication patterns:

| Team | Agents | Leader | Stages |
|------|--------|--------|--------|
| @planning | researcher, pm, pjm, architect | pm | 00-01 |
| @dev | coder, reviewer | coder | 04-05 |
| @qa | tester, reviewer | tester | 05 |
| @fullstack | researcher, pm, pjm, architect, coder, reviewer | pm | All |

Messages to a team route to the leader first. The leader delegates to teammates. Teammates can communicate within the team via `[@teammate: message]` tags.

### Multi-Provider Model Assignment

TinySDLC implements the [2-2-4 split](../02-roles-and-teams/multi-provider-strategy.md):

```
Deep Reasoning (2 roles):    researcher, architect    → Opus-tier models
Precise Analysis (2 roles):  pm, reviewer             → GPT-5.2 or structured-output models
Fast Execution (4 roles):    pjm, coder, tester, devops → Sonnet-tier models
```

Supported AI providers:
- **Anthropic** (Claude Code CLI) — primary for most roles
- **OpenAI** (Codex CLI) — for structured analysis roles
- **Ollama** (local REST API) — for privacy/cost-sensitive deployments

### 5 Communication Channels

Messages reach agents through multiple channels:

- **Discord** — DM-based interaction
- **Telegram** — Bot API integration
- **WhatsApp** — WhatsApp Web.js
- **Zalo OA** — Zalo Official Account Bot Platform
- **Zalo Personal** — Personal account via zca-cli

All channels feed into a single file-based queue. Agents process messages regardless of which channel they arrived from.

### SE4H/SE4A Governance

TinySDLC enforces governance through:

- **Role-specific system prompts**: Each agent knows its responsibilities and constraints
- **SE4A constraints**: Agents cannot self-approve, cannot merge without review, cannot bypass gates
- **Conversation limits**: Maximum 50 messages per team conversation (loop prevention)
- **Human approval**: Gate decisions require human (SE4H) confirmation

### Safety Guards

- **Shell guard**: 8 mandatory deny patterns prevent destructive commands (rm -rf, fork bombs, etc.)
- **Input sanitizer**: 12 prompt injection patterns stripped from incoming messages
- **Workspace isolation**: Each agent operates in its own directory
- **Failover system**: 6-category error classification with automatic provider fallback

---

## How to Try It

### Quick Start

```bash
git clone https://github.com/Minh-Tam-Solution/tinysdlc.git
cd tinysdlc
npm install
npm run build
./tinysdlc.sh start    # Interactive setup wizard
```

### Apply SDLC Configuration

```bash
tinysdlc sdlc init     # Creates 8 SE4A agents + 4 teams
tinysdlc sdlc status   # Verify configuration
```

### Talk to a Team

```
@planning I want to add user authentication to the app
```

The planning team's PM (leader) receives the message, analyzes scope, and delegates to researcher (for technical landscape), architect (for feasibility), and pjm (for sprint planning).

### Talk to a Specific Agent

```
@architect Review the authentication approach for security concerns
```

The architect agent responds with its role-specific knowledge and constraints.

---

## Architecture

```
Channels (Discord, Telegram, WhatsApp, Zalo)
        │
        ↓  Write message.json
File-Based Queue (~/.tinysdlc/queue/)
  incoming/ → processing/ → outgoing/
        │
        ↓  Queue Processor (polls 1s)
Parallel Agent Processing
  ┌──────────┐  ┌──────────┐  ┌──────────┐
  │ coder    │  │ reviewer │  │ pm       │
  │ (Claude) │  │ (GPT)    │  │ (GPT)    │
  └──────────┘  └──────────┘  └──────────┘
```

Key design decisions:
- **File-based queue** instead of Redis/RabbitMQ — zero external dependencies, crash-safe via atomic file renames
- **Parallel across agents, sequential per agent** — prevents race conditions while maximizing throughput
- **Plugin architecture** for channels — add new channels without modifying core code

---

## SDLC Concepts Demonstrated

| SDLC Concept | TinySDLC Implementation |
|-------------|------------------------|
| 12 SDLC Roles | 8 SE4A agents active (LITE tier); 12-role model defined in config |
| 6 Team Archetypes | 4 core teams active (LITE tier); 6 archetypes defined in config |
| SE4H/SE4A Governance | Human approves gates; agents execute but cannot self-approve |
| Multi-Provider Strategy | Different AI models per role tier (2-2-4 split) |
| Quality Gates | Agents reference gate criteria in their role prompts |
| Stage Ownership | Each agent knows which stages it operates in |

---

## What TinySDLC Does NOT Implement

TinySDLC is a LITE tier implementation. It does not include:

- **Formal gate enforcement** — gates are referenced in agent prompts, not programmatically enforced
- **Evidence vault** — no artifact storage system
- **Automated compliance** — no policy engine
- **Enterprise governance** — no board-level approval workflows
- **Stages 05-09** — LITE tier uses stages 00-04

For these capabilities, see [LITE vs Enterprise](../06-reference/lite-vs-enterprise.md).

---

## Configuration Reference

TinySDLC uses `.sdlc-config.json` in the project root:

```json
{
  "version": "1.0.0",
  "project": {
    "id": "your-project",
    "name": "Your Project",
    "description": "Project description"
  },
  "sdlc": {
    "frameworkVersion": "6.1.0",
    "tier": "LITE",
    "stages": {
      "00-foundation": "docs/00-foundation",
      "01-planning": "docs/01-planning",
      "02-design": "docs/02-design",
      "03-integrate": "docs/03-integrate",
      "04-build": "docs/04-build"
    }
  },
  "gates": {
    "current": "G0.1",
    "passed": []
  }
}
```

For a tool-agnostic configuration template, see [SDLC Config Template](../04-templates/sdlc-config-template.json).

---

## See Also

- [12 SDLC Roles](../02-roles-and-teams/12-sdlc-roles.md) — role responsibilities
- [4 Team Archetypes](../02-roles-and-teams/4-team-archetypes.md) — team structures
- [Multi-Provider Strategy](../02-roles-and-teams/multi-provider-strategy.md) — model assignment
- [LITE vs Enterprise](../06-reference/lite-vs-enterprise.md) — what Lite covers vs Enterprise
