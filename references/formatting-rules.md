# Formatting Rules

Detailed formatting specifications for resume-tailor skill output.

---

## Page Setup

| Setting | Value |
|---------|-------|
| Paper size | US Letter (8.5 × 11 inches) |
| Margins (all sides) | **0.5 inches = 720 DXA** |
| Content width | 8.5 - 1.0 = **7.5 inches = 10800 DXA** |
| Max pages | **1 page — hard limit** |
| Max lines | **53 lines total** (including blank separator lines) |

### Header Layout (Both Languages)

- **Line 1:** Full name — font size 14, bold, centered
- **Line 2:** Contact info (phone | city | email | LinkedIn | GitHub etc.) — 10pt, centered
- A blank line after the contact line before the first section heading

### Experience / Project Entry Header Layout

Each entry uses exactly two lines:

- **Line 1:** `Company Name | City, State` (tab) `Mon YYYY – Mon YYYY`
  - **Bold, normal casing** (NOT all caps), dates right-aligned via tab stop
  - e.g. `Smartly | New York, NY` ............... `June 2025 – Aug 2025`
  - e.g. `American Family Insurance Group (AmFam) | Madison, WI` ... `Sept 2024 – Dec 2024`
- **Line 2:** Job title or role — normal casing, regular weight, **NOT italic**
  - e.g. `Growth Marketing Intern | Marketing Department`
  - e.g. `Media Planning Intern | Strategy Department`

### Entry Spacing Rule

A **blank line** must appear between each experience or research entry.
Do NOT add blank lines between bullets within the same entry.

### Resume Section Order

1. Name + Contact (lines 1–2)
2. Education
3. Summary (if user said YES)
4. Work Experience (N entries as requested by user)
5. Project Experience (if user said YES, after Work Experience)
6. Skills

### 1-Page Enforcement Strategy

Before writing, estimate line budget:
- Name + contact + blank = 3 lines
- Education section = ~4 lines
- Summary (if included) = ~3–4 lines
- Each work entry = header + title + bullets + blank = ~5–7 lines depending on bullet count
- Each project entry = header + bullets + blank = ~4–6 lines
- Skills = ~3 lines

If total estimated lines > 53:
- **DO NOT auto-trim or auto-delete anything**
- Tell the user the exact count: "The draft is X lines, which is Y lines over the 53-line limit."
- Recommend the specific entry to remove (least JD-relevant), e.g.:
  > "I recommend removing [Entry Name] as it has the lowest relevance to this JD. Would you like to remove it, or would you prefer a different adjustment?"
- Wait for user confirmation before regenerating the resume

---

## English Resume

### Typography

| Element | Font | Size | Style |
|---------|------|------|-------|
| Name (H1) | Arial | 16pt | Bold |
| Section headings (H2) | Arial | 11pt | Bold, with bottom border |
| Job title + company | Arial | 10pt | Bold |
| Date range | Arial | 10pt | Italic, right-aligned |
| Body / bullets | Arial | **10pt** | Regular |
| Skills, Education | Arial | 10pt | Regular |

### Bullet Character Limits (English)

Every bullet fits in exactly one of two formats. Mix 1-line and 2-line freely within the same entry.

| Format | Character count (with spaces) | When to use |
|--------|-------------------------------|-------------|
| **1 line** | **≤ 112 chars** | Content fits cleanly and concisely |
| **2 lines** | **214–220 chars** (target: fill both lines cleanly) | More context or detail needed |

**Hard rules:**
- 1-line bullets: ≤ 112 chars
- 2-line bullets: **214–220 chars** (with spaces)
- NEVER write a bullet between 113–213 chars — this leaves the 2nd line awkwardly short
- NEVER exceed 220 characters — wraps to 3 lines, which is forbidden
- No requirement to match formats within an entry — mix 1-line and 2-line freely
- Count every character including spaces and punctuation

**Decision logic for every bullet:**
1. Write the bullet content
2. Count characters
3. ≤ 112 → 1-line ✅
4. 214–220 → 2-line ✅
5. 113–213 → INVALID — either trim to ≤ 112, or expand to 214–220
6. > 220 → trim to 214–220

**Examples:**
```
"Boosted CTR by 47% and CVR by 7% by executing A/B tests across 6 TikTok creative variants."
 ↑ 92 chars → 1-line ✅

"Managed €665K+ quarterly media budgets across 20+ vendors and DSPs, building Excel dashboards to track spend, forecast performance, and benchmark ROI and ROAS across all placements."
 ↑ 181 chars → INVALID (113–218 range) → expand to 219+ or trim to ≤112 ❌

"Managed €665K+ quarterly media budgets across 20+ vendors and DSPs, building Excel dashboards to track spend, forecast performance, benchmark ROI and ROAS, and support cross-channel attribution."
 ↑ 195 chars → still INVALID → keep expanding ❌

"Managed €665K+ quarterly media budgets across 20+ vendors and DSPs, building Excel dashboards to track spend, forecast performance, benchmark ROI and ROAS, and support cross-channel attribution modeling."
 ↑ 203 chars → still INVALID → keep expanding ❌

"Managed €665K+ quarterly media budgets across 20+ vendors and DSPs, building Excel dashboards to track spend, forecast performance, and benchmark ROI across display and video placements."
 ↑ aim for 219–220 chars → 2-line ✅
```

### Non-Bullet Paragraph Limits (English)

For sections without bullets — **Summary, Profile, Objective, and Skills** — use these line limits:

| Lines | Characters (with spaces) | Target range |
|-------|--------------------------|--------------|
| 1 line | ~130 | 125–130 |
| 2 lines | ~250 | 245–252 |
| 3 lines | ~380 | 373–382 |

**Rule:** Each line ≈ 130 chars. Stay slightly **below** the multiple (e.g. 250 not 260, 380 not 390).
NEVER exceed 3 lines for any single non-bullet paragraph. Summary should be 2–3 lines.

**Skills section specifically:**
- Each skill category (Technical, Business, etc.) is one line of text — no bullets
- Keep each line ≤ 130 chars; if skills list is long, split into two category lines
- e.g. `Technical: Excel (Advanced), Python (Pandas, NumPy), R, SQL, Tableau, Google Analytics, GA4`  ← count before writing
- If a line would exceed 130 chars, break into a second category or trim less-relevant skills

### Summary / Personal Statement Rules (English)

**Summary is OPTIONAL.** During Step 0, ask the user:
> "Would you like a Personal Summary section? (recommended but optional)"

If the user says NO — skip the section entirely, do not include it.

**If included, writing rules:**
- MUST be complete sentences (subject + verb + object) — NOT fragments
- MUST start with a full noun phrase, NOT a verb or participle
- ✅ `Xinwei is a data-driven analyst with...`
- ✅ `With 3+ years of experience in budget management, Xinwei brings...`
- ✅ `A results-oriented Business Operations Analyst, Xinwei has...`
- ❌ `Data-driven analyst with experience in...` (fragment — no subject)
- ❌ `Managed budgets and coordinated cross-functional...` (starts with verb)
- ❌ `Proficient in Excel and Python...` (fragment)

### Spacing

- Before section heading: 12pt spacing
- After section heading: 4pt spacing
- Between bullet items: 2pt spacing
- Between experience entries: 8pt spacing

---

## Chinese Resume (中文简历)

### Typography

| Element | Font | Size | Style |
|---------|------|------|-------|
| Name (H1) | 宋体 (SimSun) | 14pt | Bold |
| Section headings (H2) | 宋体 (SimSun) | 11pt | Bold |
| Job title + company | 宋体 (SimSun) | 10pt | Bold |
| Date range | 宋体 (SimSun) | 10pt | Regular, right-aligned |
| Body / bullets | **宋体 (SimSun)** | **10pt** | Regular |
| Skills, Education | 宋体 (SimSun) | 10pt | Regular |

### Bullet Character Limits (Chinese)

| Lines | Characters (含空格) | Usage guidance |
|-------|---------------------|----------------|
| 1 line | **~50 characters** (target 46–50) | Preferred |
| 2 lines | **~96 characters** (target 90–96) | Use when needed |

**Hard rules:**
- NEVER exceed 96 characters
- NEVER write a bullet that wraps to 3 lines
- 2-line bullets must be at least 90 characters (don't leave 2nd line almost empty)
- Chinese characters count as 1 character each
- Mixed Chinese + English: English letters count individually (e.g., "Python" = 6 chars)
- Punctuation counts as 1 character

### Non-Bullet Paragraph Limits (Chinese)

For sections without bullets — 个人简介、自我评价 — use these line limits:

| Lines | Characters (含空格) | Target range |
|-------|---------------------|--------------|
| 1 line | ~53 | 50–53 |
| 2 lines | ~103 | 100–105 |
| 3 lines | ~156 | 150–158 |

**Rule:** Each line ≈ 53 chars. Stay slightly below each multiple.
NEVER exceed 3 lines for a single non-bullet paragraph. 个人简介 should be 2–3 lines.

**Example:**
```
将部署周期缩短[X]%，通过重构CI/CD流水线并覆盖[N]个核心业务模块
↑ count = 34 chars → fits 1-line ✅

推动企业端年度续费率提升[X]%，通过建立客户健康度评分体系并联动CS团队开展精准干预，覆盖[N]个头部账户
↑ count = 49 chars → fits 1-line ✅ (just under 50)
```

### Chinese Bullet Format

Chinese bullets follow the same STAR achievement-first pattern but adapted:

```
[成果/结果] + 通过/借助/以 + [行动 + 情境]
```

Examples:
- ✅ `将用户留存率提升18%，通过为企业客户设计个性化新手引导流程`
- ✅ `缩短[X%]研发周期，借助引入敏捷开发流程并统一跨团队协作标准`
- ❌ `负责优化部署流程` (no achievement, no metric)

### Chinese Verb Bank

Diverse achievement-first verbs for Chinese bullets:

| Category | Verbs |
|----------|-------|
| 提升类 | 提升、增长、扩大、加速、优化 |
| 降低类 | 缩短、降低、减少、压缩、削减 |
| 建设类 | 搭建、构建、设计、开发、建立 |
| 推动类 | 推动、主导、带领、驱动、统筹 |
| 达成类 | 实现、达成、完成、落地、交付 |
| 创新类 | 创新、引入、探索、突破、重构 |

---

## docx Implementation Notes

### Margin in DXA
```javascript
// 0.5 inches × 1440 DXA/inch = 720 DXA
margin: { top: 720, right: 720, bottom: 720, left: 720 }
```

### Font sizes in half-points
```javascript
// English 10pt  = size: 20
// English 11pt  = size: 22
// English 16pt  = size: 32
// Chinese 10pt  = size: 20
// Chinese 11pt  = size: 22
// Chinese 14pt  = size: 28
```

### Section heading divider line
```javascript
// Use paragraph bottom border instead of a table/rule
border: {
  bottom: { style: BorderStyle.SINGLE, size: 6, color: "2E75B6", space: 1 }
}
```
