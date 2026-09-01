---
name: auto-analysis
description: >
  Autonomous company analysis engine. Automatically determines a target company's listing status and product profile,
  then dispatches to the appropriate specialist framework: AI Product Tasting (product teardown),
  IPO Archaeology (prospectus analysis), or both combined with cross-verification synthesis.
  ALWAYS use this skill when the user wants to: comprehensively analyze a tech/AI company,
  understand both a company's products AND its business fundamentals, or when the scope is
  ambiguous enough that the right framework isn't obvious.
  Do NOT trigger if the user's intent is clearly only product-focused (use ai-product-tasting)
  or only IPO/financial-focused (use ipo-archaeology).
---

# Auto Analysis

An autonomous analysis engine that determines the best approach for a target company by assessing its public listing status and product profile, then dispatches to the appropriate specialist framework(s) and synthesizes the results.

This skill orchestrates two specialist skills in the same repository:
- **AI Product Tasting** (`skills/ai-product-tasting/SKILL.md`) — 5-phase product deep dive
- **IPO Archaeology** (`skills/ipo-archaeology/SKILL.md`) — 6-module prospectus analysis

---

## Step 1: Triage — Determine the Analysis Mode

When the user names a target company, FIRST gather two pieces of information before doing any analysis:

### 1.1 Listing Status Check

Search the web to determine:
- Is the company publicly listed? On which exchange?
- When was the IPO? Is there an accessible prospectus (F-1/S-1/Prospectus)?
- Is the company planning an IPO (pre-IPO)?

### 1.2 Product Profile Check

Search the web to determine:
- Does the company have notable AI/tech products worth analyzing?
- Are there specific products the user is interested in?
- Is the company primarily known for its products or its business model?

### 1.3 Route Decision

Based on the two checks, select one of three modes:

```
         ┌──────────────────┐
         │  User names a    │
         │    company       │
         └────────┬─────────┘
                  │
         ┌────────┴─────────┐
    Has IPO filing?    Notable AI product?
         │                   │
    ┌────┴────┐         ┌───┴────┐
    Yes      No         Yes     No
    │         │          │       │
    ▼         ▼          ▼       ▼
  Has        Product   Has IPO   IPO
  product?   Only      + Prod    Only
    │         Mode      Combined  Mode
  ┌─┴──┐                Mode
  Yes   No
  │     │
  ▼     ▼
Combined IPO
 Mode   Only
        Mode
```

**Mode A: Product Only** → Company has no IPO filing but has notable products
**Mode B: IPO Only** → Company is listed but interest is in business/strategy, not specific products
**Mode C: Combined** → Company is listed AND has notable products — the most powerful mode

**Announce your routing decision to the user** before proceeding. Example:

> "Company X went public on NASDAQ in 2018 (F-1 available) and has Product Y as a flagship AI product. I'll use Combined Mode — product teardown first, then IPO archaeology, then cross-verification."

---

## Step 2: Dispatch to Specialist Skills

### Mode A: Product Only

**When**: Company is not publicly listed, or has no accessible prospectus, but has notable products.

**Examples**: Anthropic (pre-IPO, Claude Tag), Perplexity (pre-IPO), early-stage AI startups.

**Action**: Read and follow the full `skills/ai-product-tasting/SKILL.md` framework (5 phases: WHY → HOW → INTERACTION → LANDSCAPE → FRAMEWORK).

**Adaptation**: In Phase 1 (WHY), since there's no IPO filing, rely on:
- Funding announcements and investor presentations
- Founder interviews and company blog posts
- Press coverage and analyst reports
- Job postings (reveal strategic priorities)

### Mode B: IPO Only

**When**: Company is publicly listed with accessible prospectus, but the user's interest is in business/strategy, not specific products.

**Examples**: Analyzing Baidu's 2005 F-1, studying Alibaba's governance structure, comparing early Tesla vs. current Tesla.

**Action**: Read and follow the full `skills/ipo-archaeology/SKILL.md` framework (6 modules: Track Definition → Competitive Perception → Risk Prophecy → Business Model → Governance → Capital Allocation).

### Mode C: Combined

**When**: Company is publicly listed AND has notable products worth analyzing. This is the most powerful mode.

**Examples**: Unitree Robotics (listed + robotics products), Tesla (listed + FSD/Optimus), Google (listed + Gemini).

**Action**: Run both frameworks, then add a unique synthesis layer.

#### Combined Mode Execution Order:

**Phase C1: Product Analysis First**
Run `ai-product-tasting` Phases 1-3 (WHY, HOW, INTERACTION) on the flagship product. This grounds the analysis in what the company actually builds.

**Phase C2: IPO Archaeology Second**
Run `ipo-archaeology` Modules 1-6 on the prospectus. This reveals the business and strategic context behind the product.

**Phase C3: Cross-Verification Synthesis**

This is the unique value of combined mode — insights that neither framework alone can produce:

**3a. Product-Strategy Alignment**
- Does the product's design philosophy match the company's stated strategy at IPO?
- Are there contradictions between "what we said we'd build" and "what we actually built"?
- Did the product evolve in line with the company's strategic drift, or independently?

**3b. Competitive Blind Spots**
- Compare the IPO's named competitors with the product-level competitive landscape
- Are there competitors the prospectus missed that are now visible at product level?
- Does the product compete in the same market the company defined at IPO?

**3c. Business Model ↔ Product Architecture Connection**
- Does the product's technical architecture support the stated business model?
- Example: If the prospectus says "platform revenue" but the product is a closed tool, there's a misalignment
- Does the cost structure implied by the product architecture (compute, API calls, human review) match the financial projections?

**3d. Governance Impact on Product**
- Did the governance structure (founder control, investor influence) visibly shape product decisions?
- Example: Dual-class shares enabling long-term bets like Google's Waymo, or investor pressure forcing short-term monetization

**3e. Risk Factors ↔ Product Vulnerabilities**
- Do the IPO's risk factors map to actual product vulnerabilities?
- Are there product-level risks that the prospectus didn't anticipate?
- Has the product created new risk categories not in the original filing?

**Deliverable for Combined Mode**: A synthesis document that weaves product analysis and business analysis together, with a dedicated "Cross-Verification" section highlighting contradictions, confirmations, and blind spots.

---

## Step 3: Output

### Format by Mode

| Mode | Output |
|------|--------|
| Product Only | 5 markdown documents (one per phase) or summary conversation |
| IPO Only | 6 markdown sections (one per module) or summary conversation |
| Combined | Product docs + IPO docs + Cross-Verification synthesis |

### Language

Default to the user's language. Support any language.

### Depth Adaptation

- **Quick scan**: One conversation, summary depth across all applicable modules
- **Deep dive**: Multi-session, with deliverable documents per phase/module
- **Comparison**: Side-by-side analysis using whichever mode fits each company

---

## Reference: Routing Cheat Sheet

| Company | Status | Mode | Notes |
|---------|--------|------|-------|
| Anthropic | Pre-IPO | Product Only | Track IPO filing when it happens |
| Unitree Robotics | Listed (HK) | Combined | Robotics products + prospectus |
| Tesla | Listed (NASDAQ) | Combined | FSD/Optimus + S-1 archaeology |
| Baidu | Listed (NASDAQ) | Combined or IPO Only | Classic F-1 case study |
| Perplexity | Pre-IPO | Product Only | Search product analysis |
| Alibaba | Listed (NYSE/HKEX) | Combined or IPO Only | Governance case study |
| OpenAI | Complex (for-profit transition) | Product Only (for now) | Monitor listing events |
| Google/Alphabet | Listed (NASDAQ) | Combined | Gemini + S-1 archaeology |
| ByteDance | Pre-IPO | Product Only | Monitor IPO rumors |
