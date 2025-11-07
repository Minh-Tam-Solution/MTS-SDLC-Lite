# 📁 Project Documentation Blueprint - Your Operating System

**Concept**: Documentation structure = Operating System cho cả Người và AI

---

## 🎯 Tại sao cần Documentation "Operating System"?

### Problem Statement:
Startup với team nhỏ + AI tools thường gặp:
- ❌ Documentation rải rác (Notion, Google Docs, Slack, email...)
- ❌ Người mới mất 1-2 tuần mới hiểu project
- ❌ AI tools không biết context → output sai
- ❌ Quyết định được make nhưng không được ghi lại → lặp lại debate

### Solution: Structure = Operating System
- ✅ **Predictable**: Ai cũng biết tìm gì ở đâu
- ✅ **Onboarding**: Người/AI mới hiểu trong 1 ngày
- ✅ **AI-Friendly**: AI đọc structure → hiểu context
- ✅ **Scalable**: Add người/project không chaos

---

## 📂 The Minimal Structure (for Startups)

```
project-root/
├── docs/
│   ├── 00-Project-Foundation/
│   │   ├── Vision-and-Principles.md
│   │   └── Problem-Statement.md
│   │
│   ├── 01-Planning-Analysis/
│   │   ├── Target-Outcomes.md
│   │   └── Success-Metrics.md
│   │
│   ├── 02-Design-Architecture/
│   │   ├── System-Flow.md
│   │   ├── Human-AI-Roles.md
│   │   └── Quality-Gates.md
│   │
│   ├── 03-Development/
│   │   ├── Tech-Stack.md
│   │   ├── Implementation-Notes.md
│   │   └── Lessons-Learned.md
│   │
│   └── DOCUMENT-INDEX.md
│
├── src/          # Code goes here
├── tests/        # Tests go here
└── README.md     # Start here
```

**Key Insight**: Chỉ cần **4 folders map to 4 stages** (WHY/WHAT/HOW/BUILD)

---

## 📝 What Goes in Each Folder?

### 00-Project-Foundation/ (WHY?)

**Purpose**: Answer "Tại sao project này tồn tại?"

**Minimal Contents**:
```markdown
Vision-and-Principles.md:
  - 1 paragraph vision
  - 3-5 core principles
  - AI's role in vision
  
Problem-Statement.md:
  - Problem we're solving
  - Current pain points
  - Our unique approach
```

**⏱️ Time to create**: 1-2 giờ  
**👥 Who writes**: Founder/Product lead + AI assistance  
**🔄 Update frequency**: Rarely (unless pivot)

---

### 01-Planning-Analysis/ (WHAT?)

**Purpose**: Answer "Chúng ta sẽ deliver cái gì?"

**Minimal Contents**:
```markdown
Target-Outcomes.md:
  - 1-3 concrete outcomes
  - Timeline for each
  - Resources needed
  
Success-Metrics.md:
  - How we measure success
  - Current baseline (if any)
  - Target numbers
```

**⏱️ Time to create**: 2-3 giờ  
**👥 Who writes**: Product + Tech lead  
**🔄 Update frequency**: Monthly or per major milestone

---

### 02-Design-Architecture/ (HOW?)

**Purpose**: Answer "Chúng ta sẽ làm thế nào?"

**Minimal Contents**:
```markdown
System-Flow.md:
  - Flow diagram (can be Mermaid syntax)
  - Key components
  - Integration points
  
Human-AI-Roles.md:
  - What humans do (and why)
  - What AI does (and limitations)
  - Hand-off points
  
Quality-Gates.md:
  - Where we check quality
  - What we check
  - Who/what does checking
```

**⏱️ Time to create**: 3-4 giờ  
**👥 Who writes**: Tech lead + AI (diagrams, specs)  
**🔄 Update frequency**: Per sprint or when architecture changes

---

### 03-Development/ (BUILD & LEARN)

**Purpose**: Track "Chúng ta đang build gì và học được gì?"

**Minimal Contents**:
```markdown
Tech-Stack.md:
  - Languages & frameworks
  - Why we chose them
  - Trade-offs acknowledged
  
Implementation-Notes.md:
  - Current sprint focus
  - Blockers and solutions
  - Quick decisions log
  
Lessons-Learned.md:
  - What worked well
  - What didn't work
  - What we'd do differently
```

**⏱️ Time to create**: Ongoing (15 min/day)  
**👥 Who writes**: Dev team + AI  
**🔄 Update frequency**: Daily/Weekly

---

## 🤖 DOCUMENT-INDEX.md - The Map

**Purpose**: Single source of truth for "What's where?"

**Template**:
```markdown
# Project Name - Document Index

## 🎯 Quick Links
- [Vision](00-Project-Foundation/Vision-and-Principles.md)
- [Outcomes](01-Planning-Analysis/Target-Outcomes.md)
- [System Flow](02-Design-Architecture/System-Flow.md)
- [Tech Stack](03-Development/Tech-Stack.md)

## 📊 Project Status (Updated: YYYY-MM-DD)
- **Stage**: [Foundation/Planning/Design/Build]
- **Progress**: [Brief 1-liner]
- **Blockers**: [None / List]

## 🔗 External Resources
- GitHub: [link]
- Staging: [link]
- Design: [Figma link]

## 👥 Key Contacts
- Product: [Name]
- Tech: [Name]
- Design: [Name]

## 📝 Latest Updates
- YYYY-MM-DD: [Brief update]
- YYYY-MM-DD: [Brief update]
```

**⏱️ Time to maintain**: 5 phút/ngày  
**💡 Pro tip**: Ask AI to update this daily from standup notes

---

## ✅ Why This Structure Works

### 1. Onboarding = 1 Day
```yaml
Hour 1: Read DOCUMENT-INDEX + Vision
Hour 2: Read Problem-Statement + Outcomes
Hour 3: Review System-Flow + Roles
Hour 4: Scan Tech-Stack + current work

Result: New person (or AI) is productive
```

### 2. AI Context = Automatic
```yaml
When asking AI:
"Claude, read docs/02-Design-Architecture/ 
and help me implement the user auth flow"

AI reads structure → understands context → better output
```

### 3. Decisions = Traceable
```yaml
Question: "Why did we choose PostgreSQL over MongoDB?"
Answer: docs/03-Development/Tech-Stack.md line 23

No more "I think John said something 3 months ago..."
```

### 4. Patterns = Replicable
```yaml
Project 1 success? 
→ Copy docs/ structure to Project 2
→ Fill in specific content
→ Same success pattern
```

---

## 🚫 Common Mistakes to Avoid

### Mistake 1: "We'll document later"
**Reality**: Later never comes. Team forgets. Debt accumulates.

**Fix**: Document as you go (15 min/day habit)

---

### Mistake 2: "Let's use [fancy tool]"
**Reality**: Tool overhead > documentation benefit for small teams.

**Fix**: Start with Markdown + Git. Simple wins.

---

### Mistake 3: "Everything must be perfect"
**Reality**: Perfect docs never get written. Good enough > perfect.

**Fix**: 1-pager per topic. Bullet points OK. Iterate.

---

### Mistake 4: "Docs are separate from work"
**Reality**: If docs don't reflect reality, they're useless.

**Fix**: Update docs as part of Definition of Done.

---

## 🎯 Implementation Plan

### Week 1: Create Structure
```bash
# 30 minutes
mkdir -p docs/{00-Project-Foundation,01-Planning-Analysis,02-Design-Architecture,03-Development}
touch docs/DOCUMENT-INDEX.md
touch docs/00-Project-Foundation/Vision-and-Principles.md
# ... create other key files
```

### Week 2: Fill Foundation
```bash
# 4-6 hours total
- Write Vision (1 hour)
- Write Problem Statement (1 hour)
- Define Outcomes (2 hours)
- Draft System Flow (2 hours)
```

### Week 3: Make it Habit
```bash
# 15 min/day
- Update Implementation-Notes daily
- Update DOCUMENT-INDEX weekly
- Review & refine as needed
```

### Week 4: Evaluate & Adjust
```bash
# 1 hour retro
- Is structure helping or hindering?
- What's missing? What's overkill?
- Adjust and continue
```

---

## 📊 Success Metrics for Docs

**Good documentation means**:

✅ New person can onboard in <1 day  
✅ AI tools give better outputs (context-aware)  
✅ Decisions can be traced (no "I forgot why")  
✅ Patterns can be replicated (to new projects)  
✅ Time spent searching << Time spent creating  

**Bad documentation means**:

❌ People ask same questions repeatedly  
❌ AI outputs are off-target  
❌ Re-debating decided issues  
❌ Each project starts from zero  
❌ More time searching than working  

---

## 💡 Pro Tips từ Real Usage

### Tip 1: Let AI Help
```
"Claude, based on today's standup notes, 
update docs/DOCUMENT-INDEX.md and 
docs/03-Development/Implementation-Notes.md"

→ AI does grunt work, human reviews
```

### Tip 2: Link, Don't Copy
```markdown
Bad:  Copy-paste code into docs
Good: Link to code with line numbers

Example: See auth implementation in 
src/auth/oauth.ts lines 45-67
```

### Tip 3: Visual > Text
```markdown
Instead of: "User logs in, then system validates..."
Better: [Flow diagram using Mermaid or simple ASCII]
```

### Tip 4: Living Documents
```markdown
Add at top of each doc:
**Last Updated**: YYYY-MM-DD
**Status**: [Draft/Active/Archived]
**Owner**: [Name]

→ Know if doc is current
```

---

## 🎓 Beyond the Basics

**MTS SDLC Lite covers startup essentials.** Full SDLC 4.8 framework (evolved from 4.7) includes:

- Complete folder structure (10 folders cho enterprise)
- Document naming standards (no dates/versions in names)
- Archival strategies (Legacy/Active separation)
- Advanced AI integration patterns
- Multi-project scaling patterns

**Interested?** → Contact MTS for office hours, Bflow demo, mentoring sessions

---

## ✅ Your Next Action

**Today (30 min)**:
```bash
1. Create the folder structure
2. Create DOCUMENT-INDEX.md
3. Write 1-paragraph Vision
```

**This Week (6 hours)**:
```bash
4. Fill all 00-Foundation/ docs
5. Fill all 01-Planning/ docs
6. Draft 02-Design/ flows
```

**Next Week (ongoing)**:
```bash
7. Update daily (15 min)
8. Review weekly (30 min)
9. Iterate monthly (1 hour)
```

**In 1 Month**: Bạn sẽ có OS for your team. Onboard người mới trong 1 ngày. AI tools work better. Decisions traceable.

---

**Key Takeaway**:

> **"Structure is not overhead. Structure is infrastructure.  
> Good infrastructure makes everything faster."**

**The Blueprint teaches**:

> **"When Người mới + AI agents chỉ cần đọc structure  
> → They understand & work correctly → You've won."**

---

**Document**: Project-Documentation-Blueprint  
**Part of**: MTS SDLC Lite for Startups  
**Usage**: Slide 5 visual + talking points  
**Note**: This is the startup-friendly version. Full enterprise structure available through SDLC 4.8 framework via MTS.

