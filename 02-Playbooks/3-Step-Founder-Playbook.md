# 🎯 3-Step Founder Playbook
**From Tool Chaos → Execution Discipline**

> **Timeline**: 3-4 tuần  
> **Effort**: 8-12 giờ total  
> **Result**: 5-10x productivity improvement  

---

## 🚨 The Problem You're Facing

```
❌ Team đang dùng 5-10 AI tools
❌ Không ai biết tool nào cho việc gì
❌ Productivity không tăng tương xứng với tool budget
❌ Team mệt mỏi vì context switching
❌ Mỗi project lại bắt đầu từ đầu (không có patterns)
```

**Root Cause**: Nhiều tools ≠ nhiều kết quả. Thiếu **hệ tư duy**.

---

## ✅ The 3-Step Solution

```
┌─────────────────────────────────────────────────────┐
│  STEP 1: AUDIT                                      │
│  "Dừng đốt tiền tool"                              │
│  ⏱️ Timeline: Week 1 (2 giờ)                        │
└─────────────────────────────────────────────────────┘
         ↓
┌─────────────────────────────────────────────────────┐
│  STEP 2: DESIGN                                     │
│  "Start ridiculously small"                        │
│  ⏱️ Timeline: Week 2-3 (4-6 giờ)                    │
└─────────────────────────────────────────────────────┘
         ↓
┌─────────────────────────────────────────────────────┐
│  STEP 3: STANDARDIZE                                │
│  "Pattern hóa & replicate"                         │
│  ⏱️ Timeline: Week 4 (2-4 giờ)                      │
└─────────────────────────────────────────────────────┘
```

---

## 📋 STEP 1: AUDIT (Week 1 - 2 giờ)

### Objective: 
Biết rõ **đang có gì**, **thiếu gì**, **thừa gì**.

### Activities:

#### 1.1 List All AI Tools (30 phút)
```markdown
Create a spreadsheet with columns:
- Tool Name
- Purpose (1 sentence)
- Who Uses It
- Frequency (daily/weekly/rarely)
- Cost ($/month)
```

**Pro Tip**: Hỏi team qua Slack poll để có full list.

---

#### 1.2 Map Tools to 4 Stages (45 phút)
```markdown
For each tool, answer:
- This tool solves WHICH stage?
  □ WHY (Foundation): Vision, strategy, principles
  □ WHAT (Planning): Outcomes, requirements, specs
  □ HOW (Design): Architecture, flows, roles
  □ BUILD (Implementation): Coding, testing, deployment

Example:
- ChatGPT → WHY & WHAT (ideation, requirements)
- Claude Code → HOW & BUILD (design, implementation)
- Cursor → BUILD (coding with AI assistance)
- Figma → HOW (design mockups)
```

**Red Flags to spot**:
- ❌ Tool không map vào stage nào → Kill it
- ❌ 3 tools cùng làm 1 việc → Consolidate
- ❌ Stage nào không có tool → Potential gap

---

#### 1.3 Identify Owner & KPIs (30 phút)
```markdown
For each tool, ask:
1. WHO owns this tool?
   - Not "team" - need specific name
   - Owner = person who:
     * Trains others
     * Measures ROI
     * Decides to continue/stop

2. WHAT is the KPI?
   - Time saved per week?
   - Quality improvement?
   - Cost reduction?
   - Specific output metrics?

Example:
- Cursor (Owner: Lead Dev)
  KPI: 30% reduction in code time
  Measured: Time tracking per feature
```

**Red Flags**:
- ❌ Không có owner → Orphan tool → Kill candidate
- ❌ Không có KPI → Không biết có work không → Kill candidate

---

#### 1.4 Kill Orphan Tools (15 phút)
```markdown
Decision matrix:
┌─────────────┬──────────────┬─────────────┐
│             │ Has Owner    │ No Owner    │
├─────────────┼──────────────┼─────────────┤
│ Has KPI     │ ✅ KEEP      │ ⚠️ ASSIGN   │
│ No KPI      │ ⚠️ ADD KPI   │ ❌ KILL     │
└─────────────┴──────────────┴─────────────┘

Action: Kill at least 20% of tools ngay tuần này
```

**Expected**: Từ 10 tools → 6-7 tools with clear purpose

---

### Step 1 Deliverables:
- [ ] Tool inventory spreadsheet
- [ ] Tools mapped to 4 stages
- [ ] Each tool has owner + KPI
- [ ] 20%+ orphan tools killed
- [ ] Team briefed on survivors

**🎯 Success Metric**: Team nói "Wow, giờ mới rõ mình đang xài gì"

---

## 🎨 STEP 2: DESIGN (Week 2-3 - 4-6 giờ)

### Objective: 
Prove value với **1 use case nhỏ nhất**, không phải toàn bộ product.

### Activities:

#### 2.1 Pick ONE Use Case (30 phút)
```markdown
Criteria for first use case:
✅ Small (complete trong 2 tuần)
✅ High pain (team feels the problem daily)
✅ Measurable (know if it worked)
✅ Repeatable (can apply pattern to others)

Examples:
- GOOD: "Idea → PRD spec" (1 loop, 1 week)
- BAD: "Entire product development" (too big)

- GOOD: "Bug report → Root cause analysis" (focused)
- BAD: "All QA processes" (too broad)
```

**Pro Tip**: Pick something team does 5-10x per week = high ROI.

---

#### 2.2 Map Use Case to 4 Stages (1 giờ)
```markdown
Use Case: [YOUR USE CASE]

00. WHY?
   - Why does this matter?
   - What problem does it solve?
   - What's our unique approach?

01. WHAT?
   - What's the outcome?
   - How do we measure success?
   - Timeline?

02. HOW?
   - What's the flow? (draw it)
   - Human does what? AI does what?
   - Quality gates where?

03. BUILD
   - Tool(s) to use? (MAX 3)
   - Test & learn loop?
   - When to review?

Example: See Use-Case-Mapping-Canvas.md
```

**Key**: Spend time on HOW. Nếu HOW rõ, BUILD sẽ smooth.

---

#### 2.3 Choose 1-3 AI Tools MAX (30 phút)
```markdown
For your use case, pick:
- Primary tool (does 70% of work)
- Secondary tool (assists or validates)
- Optional: Tertiary tool (special needs)

Example for "Idea → PRD":
- Primary: ChatGPT (ideation & structure)
- Secondary: Claude Code (detail & validation)
- Tertiary: None needed

NO MORE THAN 3 TOOLS per use case.
```

**Why limit?** Cognitive load. Context switching kills productivity.

---

#### 2.4 Define Quality Gates (1 giờ)
```markdown
For each step in your flow, define:

Gate 1: [Step Name]
   Check: [What to verify]
   Who/What: [Human or AI or Auto]
   Pass Criteria: [Specific]
   Fail Action: [What happens]

Example:
Gate 1: Idea clarity
   Check: Can explain in 2 sentences?
   Who: Human (peer review)
   Pass: Yes, it's clear
   Fail: Refine with ChatGPT, try again

Gate 2: PRD completeness
   Check: Has WHY/WHAT/HOW sections?
   Who: AI (Claude validates structure)
   Pass: All sections present
   Fail: Generate missing sections
```

**Pro Tip**: Gates = Safety nets. AI can hallucinate. Gates catch it.

---

#### 2.5 Run Experiment (2 tuần)
```markdown
Timeline:
- Week 1: Use case iterations 1-5
- Week 2: Use case iterations 6-10

For each iteration, track:
- Time taken (actual)
- Quality score (1-10, subjective OK)
- Blockers encountered
- Learnings

Compare:
- BEFORE: Time & quality without framework
- AFTER: Time & quality with framework

Target: At least 30% improvement in time OR quality
```

**Critical**: Actually track. Không track = không biết có work.

---

### Step 2 Deliverables:
- [ ] 1 use case selected & scoped
- [ ] Use case mapped through 4 stages
- [ ] 1-3 AI tools chosen with roles
- [ ] Quality gates defined
- [ ] 2-week experiment run & measured
- [ ] Improvement proven (30%+ time or quality)

**🎯 Success Metric**: Team nói "This actually worked better"

---

## 📚 STEP 3: STANDARDIZE (Week 4 - 2-4 giờ)

### Objective:
Biến success thành **pattern** để replicate.

### Activities:

#### 3.1 Write 1-Page Guideline (1 giờ)
```markdown
Template: See 1-Page-Guideline-Template.md

Sections (1-page total):
1. Use Case (1 paragraph)
2. 4-Stage Map (bullet points)
3. Tools & Roles (table)
4. Quality Gates (checklist)
5. Expected Time & Quality (metrics)
6. Common Pitfalls (3-5 items)

Keep it SHORT. 1 page forces clarity.
```

**Pro Tip**: Let AI draft it, human refine. Saves 30 minutes.

---

#### 3.2 Put in docs/ Structure (15 phút)
```bash
# Create if not exists
mkdir -p docs/04-Patterns/

# Save guideline
docs/04-Patterns/Pattern-[Use-Case-Name].md

# Update index
Add to docs/DOCUMENT-INDEX.md:
- Link to new pattern
- Brief description
- When to use

Example:
docs/04-Patterns/Pattern-Idea-to-PRD.md
docs/04-Patterns/Pattern-Bug-to-RCA.md
```

**Why docs/?** Single source of truth. Everyone knows where to look.

---

#### 3.3 Replicate to 2nd Use Case (1-2 giờ)
```markdown
Pick 2nd use case (similar to 1st)

Steps:
1. Copy pattern guideline
2. Adjust for specific use case
3. Run 1 week experiment
4. Compare results

Expected: 
- 1st use case: 30% improvement
- 2nd use case: 40-50% improvement (pattern helps)
- 3rd use case: 50-60% improvement (team learning)
```

**This proves pattern is replicable, not one-time luck.**

---

#### 3.4 Share Wins with Team (30 phút)
```markdown
Format: 15-min team demo

Show:
1. Problem before (time/quality metrics)
2. Solution (4-stage map + tools + gates)
3. Results after (metrics improvement)
4. Pattern created (show 1-page guideline)
5. Next steps (which use cases to apply next)

Ask:
- Which use case should we tackle next?
- Who wants to try this pattern?

Goal: Build momentum. Small wins → Big enthusiasm.
```

---

#### 3.5 Schedule Monthly Review (15 phút)
```markdown
Set recurring calendar event:
- Frequency: Monthly
- Duration: 1 hour
- Agenda:
  * Review all patterns (still working?)
  * Measure total impact (time saved, quality up)
  * Identify new patterns needed
  * Kill patterns that don't work
  * Share success stories

This keeps system ALIVE, not one-and-done.
```

---

### Step 3 Deliverables:
- [ ] 1-page guideline written for use case
- [ ] Guideline saved in docs/04-Patterns/
- [ ] Pattern replicated to 2nd use case successfully
- [ ] Team demo completed
- [ ] Monthly review scheduled

**🎯 Success Metric**: Team is using pattern WITHOUT asking how.

---

## 📊 Expected Results Timeline

```
Week 1 (Audit):
  Effort: 2 hours
  Result: Clarity (know what you have)
  ROI: Kill 20% waste immediately

Week 2-3 (Design):
  Effort: 4-6 hours
  Result: 1 proven pattern
  ROI: 30-50% improvement on 1 use case

Week 4 (Standardize):
  Effort: 2-4 hours
  Result: Replicable pattern + team adoption
  ROI: 40-60% improvement on 2nd use case

Month 2:
  Effort: 1 hour/week maintenance
  Result: 3-5 patterns in production
  ROI: 5-10x overall productivity

Month 3:
  Result: Patterns become "how we work"
  ROI: Compound - new people learn fast via patterns
```

---

## 🚫 Common Pitfalls & How to Avoid

### Pitfall 1: "Let's audit everything at once"
**Problem**: Analysis paralysis. Never start.

**Fix**: Start with tools being used THIS week. Ignore dormant ones for now.

---

### Pitfall 2: "Let's design perfect process before testing"
**Problem**: Perfect never ships. No learning.

**Fix**: 2-week experiment is enough. Iterate after.

---

### Pitfall 3: "This pattern is perfect, never change"
**Problem**: Context changes. Pattern ossifies.

**Fix**: Monthly review. Kill patterns that stop working.

---

### Pitfall 4: "Only I can do this right"
**Problem**: Bus factor. Doesn't scale.

**Fix**: Make 1-page guideline. Train 1 other person. Let them run next pattern.

---

## 💡 Pro Tips từ Real Battles

### Tip 1: Start Even Smaller Than You Think
```
If you think "2 weeks" is small enough → Go smaller.
Try: "Can we see improvement in 3 days?"

Example:
- Too big: "Improve entire sprint planning"
- Right size: "Improve sprint kickoff meeting prep"
```

---

### Tip 2: Measure Imperfectly > Don't Measure
```
Imperfect metrics:
- "Feels 30% faster" ✅ (subjective but directional)
- Time tracking rounded to 30min ✅ (good enough)

Perfect metrics:
- Time tracked to the second ❌ (overhead kills ROI)
```

---

### Tip 3: Let AI Do Grunt Work
```
Ask AI:
"Based on this experiment log, write a 1-page pattern guideline"
"Draft quality gates for this use case"
"Suggest 3 similar use cases to apply this pattern"

AI drafts → Human refines → 50% time saved
```

---

### Tip 4: Celebrate Small Wins Loudly
```
When 1 pattern works:
- Share in Slack/Teams
- Demo in standup
- Write quick success story
- Thank people involved

Momentum matters more than scale early on.
```

---

## ✅ Your Week-by-Week Checklist

### Week 1: AUDIT
- [ ] Monday: List all AI tools (30 min)
- [ ] Tuesday: Map to 4 stages (45 min)
- [ ] Wednesday: Assign owners & KPIs (30 min)
- [ ] Thursday: Kill orphan tools (15 min)
- [ ] Friday: Brief team on cleaned list (30 min)

### Week 2: DESIGN - Part 1
- [ ] Monday: Pick 1 use case (30 min)
- [ ] Tuesday: Map through 4 stages (1 hour)
- [ ] Wednesday: Choose 1-3 tools (30 min)
- [ ] Thursday: Define quality gates (1 hour)
- [ ] Friday: Start experiment (ongoing)

### Week 3: DESIGN - Part 2
- [ ] Monday-Thursday: Continue experiment
- [ ] Friday: Measure results, document learnings (1 hour)

### Week 4: STANDARDIZE
- [ ] Monday: Write 1-page guideline (1 hour)
- [ ] Tuesday: Save in docs/, update index (15 min)
- [ ] Wednesday: Apply to 2nd use case (1 hour)
- [ ] Thursday: Run 2nd experiment (track it)
- [ ] Friday: Team demo + monthly review setup (45 min)

---

## 🎯 Final Success Criteria

**After 4 weeks, you should have:**

✅ Clear tool inventory (no orphans)  
✅ 1 proven pattern (30%+ improvement measured)  
✅ Pattern replicated successfully (2nd use case)  
✅ Team trained and using pattern  
✅ Monthly review scheduled  
✅ 5-10x productivity on the horizon  

**If NOT hitting these**, likely causes:
- Picked too big a use case → Go smaller
- Didn't actually measure → Track next time
- No quality gates → Add them
- Team not involved → Get buy-in

---

## 🚀 What's Next?

**Short-term (Month 2-3)**:
- Add 2-3 more patterns
- Build pattern library
- Train entire team
- Measure total productivity gain

**Long-term (Month 6+)**:
- Patterns become muscle memory
- New people onboard via patterns
- Tools consolidate further
- Share success with community

**Need Help?**
- SDLC 4.7 Full Framework (deep dive)
- Office hours (mentoring)
- Bflow platform (automates patterns)

---

**Key Takeaway**:

> **"You don't need more tools.  
> You need more DISCIPLINE with fewer tools."**

**The Playbook teaches**:

> **"Audit → Design → Standardize  
> = Tool chaos → Execution excellence"**

---

**Document**: 3-Step-Founder-Playbook  
**Part of**: MTS SDLC Lite for Startups  
**Contact**: taidt@mtsolution.com.vn | 0939116006  
**Usage**: Slide 8 core content  
**Time to Value**: 4 weeks to 5-10x improvement

