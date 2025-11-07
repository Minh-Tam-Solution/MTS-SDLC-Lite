# 🎯 MTS SDLC Lite - 4 Core Stages Framework

**For Founders**: Start with the RIGHT questions, not the RIGHT tools.

> Based on **SDLC 4.8 Framework** - Battle-tested methodology with System Thinking & Design Thinking

---

## 🧭 The 4 Essential Questions

```
┌──────────────────────────────────────────────────────┐
│  00. FOUNDATION          WHY?                        │
│  ↓  Tầm nhìn, vấn đề gốc, lợi thế khác biệt          │
├──────────────────────────────────────────────────────┤
│  01. PLAN & ANALYZE      WHAT?                       │
│  ↓  Chọn đúng 1-3 outcomes đo được                   │
├──────────────────────────────────────────────────────┤
│  02. DESIGN & ARCH       HOW?                        │
│  ↓  Flow, vai trò Người/AI, gates & guardrails      │
├──────────────────────────────────────────────────────┤
│  03. BUILD               DO IT                       │
│     Incremental, AI-assisted, test-learn            │
└──────────────────────────────────────────────────────┘
```

**⚠️ Sai lầm phổ biến #1**: Nhảy thẳng vào BUILD trước khi trả lời WHY/WHAT/HOW

---

## 00. FOUNDATION - WHY?

### Câu hỏi cốt lõi:
- **Tại sao** project này quan trọng?
- **Vấn đề gốc** là gì? (không phải symptom)
- **Lợi thế khác biệt** của chúng ta là gì?
- **AI đóng vai trò** gì trong vision này?

### Output mong đợi:
- 1 trang Problem Statement rõ ràng
- 3-5 core principles (nguyên tắc dẫn dắt)
- Vision statement (know where you're going)

### 🚫 Red Flags:
- "Làm vì competitor đang làm"
- "Tool X hot nên dùng thử"
- "Không rõ problem, nhưng solution hay"

### ✅ Good Example (NQH-Bot):
```yaml
WHY: 
  F&B workforce operations chaotic → ₫15B revenue at risk
  
Problem: 
  Multi-location tracking unreliable
  
Differentiation: 
  AI + Real-time + Zero-Mock testing
  
AI Role: 
  Automate data collection, predict issues, assist decisions
```

---

## 01. PLAN & ANALYZE - WHAT?

### Câu hỏi cốt lõi:
- **Outcomes nào** cụ thể, đo được?
- **1-3 metrics** quan trọng nhất?
- **Success** trông như thế nào?
- **Timeline** thực tế là bao lâu?

### Output mong đợi:
- 1-3 measurable outcomes
- Clear success criteria
- Realistic timeline
- Resource requirements

### 🚫 Red Flags:
- "Làm nhiều features để xem sao"
- Outcomes mơ hồ, không đo được
- "Everything is priority"

### ✅ Good Example (MTEP):
```yaml
WHAT:
  Outcome 1: <30 min để tạo 1 education platform
  Outcome 2: <50ms response time
  Outcome 3: 137KB bundle size
  
Metrics:
  - Creation time (target: <30min)
  - Response time (target: <50ms)
  - Bundle size (target: <150KB)
  
Timeline: 2 months MVP
```

**⚠️ Sai lầm phổ biến #2**: Quá nhiều outcomes → diluted focus → nothing ships well

---

## 02. DESIGN & ARCH - HOW?

### Câu hỏi cốt lõi:
- **Flow** cụ thể như thế nào?
- **Ai làm gì**? (Human vs AI roles)
- **Quality gates** ở đâu?
- **Guardrails** để prevent disasters?

### Output mong đợi:
- Flow diagram (simple is better)
- RACI matrix (who does what)
- Quality gates defined
- Risk mitigation plan

### 🚫 Red Flags:
- "We'll figure it out as we build"
- Không rõ ai responsible cho gì
- No quality checkpoints
- "AI will handle everything"

### ✅ Good Example (Bflow):
```yaml
HOW:
  Flow: 
    User input → AI process → Human validate → Auto test → Deploy
    
  Roles:
    - Human: Strategic decisions, validation, edge cases
    - AI: Generation, repetitive tasks, pattern detection
    
  Quality Gates:
    - Gate 1: Design review (before code)
    - Gate 2: AI output validation (human check)
    - Gate 3: Automated tests (zero mocks)
    - Gate 4: Integration tests (real services)
    
  Guardrails:
    - Pre-commit hooks (catch violations)
    - API contracts (prevent breaks)
    - Documentation templates (ensure consistency)
```

**⚠️ Sai lầm phổ biến #3**: Thiếu guardrails → AI hallucinations ship to production

---

## 03. BUILD - DO IT

### Câu hỏi cốt lõi:
- **Incremental** hay big bang?
- **AI tools** nào cho stage nào?
- **Test & learn** loop như thế nào?
- **When to pivot** vs persevere?

### Output mong đợi:
- Working software (even if minimal)
- Lessons learned documented
- Metrics tracked
- Iterations planned

### 🚫 Red Flags:
- Build 3 tháng không demo được gì
- "We'll test sau khi done"
- Metrics không được track
- Không có feedback loop

### ✅ Good Example (All 3 Platforms):
```yaml
BUILD Approach:
  Week 1: Skeleton + 1 feature (prove concept)
  Week 2: 3-5 core features (prove value)
  Week 3: Integration + polish (prove production-ready)
  Week 4+: Iterate based on real usage
  
AI Tools:
  - Claude Code: Implementation (70%)
  - GitHub Copilot: Code assistance (15%)
  - ChatGPT/Gemini: Review & validation (15%)
  
Test & Learn:
  - Daily: What worked? What didn't?
  - Weekly: Are we hitting metrics?
  - Bi-weekly: Pivot or persevere?
```

**⚠️ Sai lầm phổ biến #4**: Overbuilding before validation → wasted effort

---

## 🔄 The Loop: Always Come Back to WHY

```
         ┌──────────────┐
         │  00. WHY?    │ ← Khi stuck, quay về đây
         └──────┬───────┘
                ↓
         ┌──────────────┐
         │  01. WHAT?   │ ← Refine outcomes based on learnings
         └──────┬───────┘
                ↓
         ┌──────────────┐
         │  02. HOW?    │ ← Adjust flow/roles as needed
         └──────┬───────┘
                ↓
         ┌──────────────┐
    ┌───│  03. BUILD   │
    │   └──────────────┘
    │          ↓
    └──── LEARN & ITERATE
```

**Key Insight**: Không phải linear, mà là iterative loop với WHY là anchor.

---

## 🎯 Quick Self-Assessment

**Đánh giá project hiện tại của bạn:**

### Stage 00 - WHY?
- [ ] Tôi có thể giải thích WHY trong 2 câu
- [ ] Team align về problem statement
- [ ] Rõ lợi thế khác biệt của mình

**Nếu chưa có đủ 3 checkboxes → STOP, quay về Stage 00**

---

### Stage 01 - WHAT?
- [ ] Có 1-3 outcomes cụ thể, đo được
- [ ] Biết success trông như thế nào
- [ ] Timeline realistic (không wishful thinking)

**Nếu chưa có đủ 3 checkboxes → Đừng lao vào design**

---

### Stage 02 - HOW?
- [ ] Flow rõ ràng, visualized được
- [ ] Vai trò Người/AI defined
- [ ] Quality gates và guardrails in place

**Nếu chưa có đủ 3 checkboxes → Đừng bắt đầu code**

---

### Stage 03 - BUILD
- [ ] Incremental approach (not big bang)
- [ ] Test & learn loop active
- [ ] Metrics tracked continuously

**Nếu chưa có đủ 3 checkboxes → Đang build wrong**

---

## 💡 Pro Tips từ 3 Platforms

### Tip 1: Start Ridiculously Small
> "Don't apply 4 stages to entire product. Apply to 1 tiny use case first."

**Example**: Thay vì "Build entire AI-powered platform", start với "AI generates 1 type of report, human validates, ship in 2 weeks".

---

### Tip 2: Document as You Go
> "If it's not documented, it didn't happen. And you can't replicate it."

**Example**: Mỗi stage, spend 15 phút write down:
- Decisions made (and why)
- Assumptions tested
- Lessons learned

---

### Tip 3: Quality Gates are Non-Negotiable
> "Speed without quality gates = technical debt accumulation machine."

**Example**: 679-Mock crisis happened vì skip quality gates. Cost: 48 giờ khủng hoảng.

---

## 🚀 Next Steps

### To Apply 4 Stages:

**Week 1**: Pick 1 small project/feature
- Spend 2 giờ answer WHY/WHAT/HOW
- Don't code yet

**Week 2**: Design HOW chi tiết
- Draw flow
- Define roles (Human/AI)
- Set quality gates

**Week 3**: BUILD incremental
- Week targets, not month targets
- Test & learn daily
- Document lessons

**Week 4**: Review & replicate
- Did 4 stages help?
- What would you change?
- Apply to next use case

---

## 🎓 Deep Dive Available

**MTS SDLC Lite is introduction.** Full SDLC 4.8 framework includes:

- Complete implementation guides
- AI role templates (Claude, Cursor, Copilot, etc.)
- Crisis response protocols
- Automation tools and scripts
- Case study details
- Pattern library

**Muốn learn more?**
- Office hours (scan QR từ slides)
- Bflow platform demo
- 1-on-1 mentoring sessions

---

**Key Takeaway**: 

> **"Ask the RIGHT questions in the RIGHT order.  
> That's more valuable than having the RIGHT tools."**

**The 4 Stages teach**:

> **"WHY grounds you. WHAT focuses you.  
> HOW structures you. BUILD validates you."**

---

**Document**: 4-Stages-Framework  
**Part of**: MTS SDLC Lite for Startups  
**Usage**: Slide 4 talking points  
**Note**: This is the startup-friendly version for thought leadership. Full SDLC 4.8 framework available through MTS partnership/mentoring.

