# Multi-Provider Strategy

**SDLC Version**: 6.0.6
**Category**: Roles & Teams
**Status**: Active
**License**: MIT

---

## Overview

Different SDLC roles need different AI model strengths. A researcher analyzing market trends needs deep reasoning. A coder writing implementations needs fast, reliable output. A reviewer checking security needs precise, criteria-based evaluation.

The multi-provider strategy assigns the right model tier to each role, optimizing for both quality and cost.

---

## The 3-Tier Model Assignment

| Tier | Strength | Best For | Example Models |
|------|----------|----------|----------------|
| **Deep Reasoning** | Complex analysis, multi-step thinking, nuanced judgment | researcher, architect | Claude Opus, GPT-4o, large local models |
| **Precise Analysis** | Structured output, checklist adherence, criteria evaluation | pm, reviewer | GPT-5.2, Claude Sonnet (with structured prompts) |
| **Fast Execution** | High-frequency tasks, rapid iteration, reliable output | pjm, coder, tester, devops | Claude Sonnet, Codex, medium local models |

---

## Role-to-Tier Mapping

| Role | Tier | Why |
|------|------|-----|
| **researcher** | Deep Reasoning | Research requires synthesizing large volumes of information and producing nuanced analysis |
| **pm** | Precise Analysis | Requirements need structured output — user stories, acceptance criteria, clear documentation |
| **pjm** | Fast Execution | Project management is operational — tracking tasks, updating timelines, generating reports |
| **architect** | Deep Reasoning | Architecture requires reasoning about trade-offs, security implications, and long-term maintainability |
| **coder** | Fast Execution | Development is high-frequency — writing code, running tests, iterating quickly |
| **reviewer** | Precise Analysis | Code review demands pattern matching, checklist adherence, and systematic security analysis |
| **tester** | Fast Execution | Testing is execution-heavy — running test plans, measuring coverage, producing reports |
| **devops** | Fast Execution | DevOps is operational — CI/CD pipelines, deployments, monitoring |

---

## The 2-2-4 Split

In practice, this creates a **2-2-4 provider split**:

```
Deep Reasoning (2 roles):    researcher, architect
Precise Analysis (2 roles):  pm, reviewer
Fast Execution (4 roles):    pjm, coder, tester, devops
```

This split optimizes cost — deep reasoning models are expensive, so you only use them where the thinking complexity justifies it.

---

## Cost Optimization

| Tier | Relative Cost | Usage Frequency | Monthly Estimate |
|------|--------------|-----------------|-----------------|
| Deep Reasoning | High ($$$) | Low (research, design phases) | $100-500/month |
| Precise Analysis | Medium ($$) | Medium (requirements, reviews) | $50-200/month |
| Fast Execution | Low ($) | High (daily development) | $20-100/month |

**Key insight**: Most AI usage (60-70%) is in Fast Execution tier. By routing only complex work to expensive models, you save 50-80% compared to using the most capable model for everything.

---

## Tool-Agnostic Application

This strategy works with any AI provider combination:

### Example: All Anthropic
```
Deep Reasoning:    Claude Opus
Precise Analysis:  Claude Sonnet (with structured prompts)
Fast Execution:    Claude Haiku or Sonnet
```

### Example: Mixed Providers
```
Deep Reasoning:    Claude Opus (Anthropic)
Precise Analysis:  GPT-5.2 (OpenAI)
Fast Execution:    Claude Sonnet (Anthropic)
```

### Example: Local-First (Privacy/Cost)
```
Deep Reasoning:    Qwen 72B (Ollama, self-hosted)
Precise Analysis:  Qwen 32B (Ollama, self-hosted)
Fast Execution:    Qwen 14B (Ollama, self-hosted)
Fallback:          Claude Sonnet (cloud, when local is unavailable)
```

### Example: Budget-Constrained
```
All roles:         One capable model (e.g., Claude Sonnet)
Upgrade path:      Move researcher + architect to Opus when budget allows
```

---

## Implementation

### With TinySDLC

TinySDLC implements the 2-2-4 split in its default configuration:

```json
{
  "agents": {
    "researcher": { "provider": "anthropic", "model": "opus" },
    "pm":         { "provider": "openai",    "model": "gpt-5.2" },
    "pjm":        { "provider": "anthropic", "model": "sonnet" },
    "architect":  { "provider": "anthropic", "model": "opus" },
    "coder":      { "provider": "anthropic", "model": "sonnet" },
    "reviewer":   { "provider": "openai",    "model": "gpt-5.2" },
    "tester":     { "provider": "anthropic", "model": "sonnet" },
    "devops":     { "provider": "anthropic", "model": "sonnet" }
  }
}
```

### Without TinySDLC

Apply the principle manually:
1. Use your best/most expensive model for research and architecture tasks
2. Use a structured-output-focused model for requirements and code review
3. Use your fastest/cheapest model for daily development tasks
4. Always configure fallbacks for when a provider is unavailable

---

## See Also

- [8 SDLC Roles](8-sdlc-roles.md) — role responsibilities that drive model selection
- [4 Team Archetypes](4-team-archetypes.md) — how roles combine in teams
- [TinySDLC Reference](../05-case-studies/tinysdlc-reference.md) — multi-provider in practice
