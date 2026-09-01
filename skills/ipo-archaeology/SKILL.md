---
name: ipo-archaeology
description: >
  IPO prospectus archaeology and business judgment training framework. Analyzes public company IPO filings
  (F-1/S-1/Prospectus) to compare management's self-assessment at listing time with what actually happened
  years later, training strategic foresight and business judgment.
  ALWAYS use this skill when the user wants to: analyze an IPO prospectus or filing, study a company's S-1/F-1,
  compare what a company said at IPO vs what actually happened, analyze business model from SEC filings,
  understand a company's founding strategy through its listing documents.
  Trigger for any IPO document analysis intent. Also trigger when the user wants to understand a public company's
  strategic evolution by anchoring to its IPO moment.
---

# IPO Archaeology Framework

A structured methodology for analyzing IPO prospectuses (F-1/S-1/Prospectus) to train business judgment. The core method: treat the prospectus as a "time capsule" — the management team's most serious, legally-binding self-assessment at a specific moment — then use hindsight to verify what they got right, wrong, and what they completely missed.

This framework is model-agnostic: it works for Claude, ChatGPT, Codex, Gemini, or any AI assistant with web search capability.

---

## How to Use This Skill

### Quick Start

When the user names a company, follow this workflow:

1. **Locate the filing**: Search SEC EDGAR (sec.gov/cgi-bin/browse-edgar) for US-listed companies, or the relevant exchange's filing system for other markets.
2. **Identify the IPO date**: Confirm the exact listing date and exchange.
3. **Run the 6-module analysis** in order, each producing structured insights.
4. **Cross-reference with current state**: For each module, compare the IPO-era description with the company's actual situation today.

### Adapt to Scope

- **Quick scan** → Modules 1-3 at summary depth
- **Deep dive** → All 6 modules at full depth, with document references and verification
- **Comparison** → Side-by-side analysis of two companies' IPO filings

### Key Filing Types

| Filing | When | Where |
|--------|------|-------|
| F-1 | Foreign company IPO in US (e.g., Baidu, Alibaba) | SEC EDGAR |
| S-1 | US domestic company IPO (e.g., Google, Uber) | SEC EDGAR |
| Prospectus (A-share) | Listing in mainland China | CSRC / cninfo.com.cn |
| Prospectus (HK) | Listing in Hong Kong | HKEX |

### Notable Examples Worth Studying

- **Baidu (2005-07-12)**: F-1 filing. Pioneered VIE architecture — became the template for nearly all US-listed Chinese companies.
- **Alibaba (2014-09-19)**: F-1 filing. Partnership structure directly shaped all subsequent strategic decisions.
- **Pinduoduo (2018-07-26)**: F-1 filing. Redefined e-commerce category boundaries.
- **Google (2004-08-19)**: S-1 filing. Famous founders' letter and dual-class share structure.
- **Tesla (2010-06-29)**: S-1 filing. Compare the original EV vision with actual business evolution.

---

## Module 1: Track Definition & Strategic Drift

**Goal**: Understand how the company defined its playing field at IPO, and how that definition evolved.

### Analysis Steps

**1.1 Self-Definition at IPO**
- How did the company describe its business in the prospectus summary?
- What industry/sector did it place itself in?
- What was the stated mission or vision?
- What market size (TAM/SAM/SOM) did it claim?

**1.2 Boundary Drawing**
- What did the company explicitly say it does NOT do?
- What adjacent markets did it acknowledge but exclude?
- Were there geographic, demographic, or product boundaries?

**1.3 Strategic Drift Verification**
- Compare the IPO-era definition with the company's actual business 5/10/15 years later
- Did it stay in the defined track or drift? If drifted, was it expansion, pivot, or retreat?
- Was the drift intentional (strategic evolution) or reactive (forced by market)?

**Key insight to extract**: The gap between "what we said we are" and "what we became" reveals whether the management had genuine strategic foresight or was reacting to circumstances.

---

## Module 2: Competitive Perception

**Goal**: Understand who the company thought its competitors were, and verify against reality.

### Analysis Steps

**2.1 Named Competitors**
- Who did the prospectus explicitly name as competitors?
- How did it describe the competitive landscape?
- What was the claimed differentiation against each named competitor?

**2.2 The Missing Competitors**
- Which companies that later became major threats were NOT mentioned?
- Were they too small at the time, or in an adjacent space?
- Could the management reasonably have foreseen them?

**2.3 Competitive Outcome Verification**
- Of the named competitors, how many still exist? How many became irrelevant?
- Of the unnamed threats, which ones actually disrupted the company?
- Did the company's claimed differentiation hold up?

**Key insight to extract**: The "missing competitor" pattern — the most dangerous threats often come from companies not even in the original competitive frame. This trains you to look beyond the obvious competitive set.

---

## Module 3: Risk Prophecy Verification

**Goal**: Analyze the risk factors section — what management was most worried about, and what actually happened.

### Analysis Steps

**3.1 Stated Risk Inventory**
- List all major risk factors from the prospectus
- Categorize them: regulatory, competitive, operational, financial, technological, geopolitical
- Which risks got the most prominent/detailed treatment? (indicates management's true concerns)

**3.2 Hindsight Verification**
- Which stated risks actually materialized? How severe were they?
- Which stated risks never happened? Were they genuine concerns or boilerplate?
- What was the BIGGEST actual risk the company faced that was NOT in the prospectus?

**3.3 Risk Awareness Quality Score**
- Were the risk descriptions specific and thoughtful, or generic legal boilerplate?
- Did the company show genuine self-awareness about its vulnerabilities?
- Compare risk awareness quality across companies in the same cohort

**Key insight to extract**: The risks that aren't listed are more revealing than the ones that are. Generic boilerplate vs. specific, honest risk disclosure tells you about management quality.

---

## Module 4: Business Model Anatomy

**Goal**: Understand the company's money-making logic at IPO and verify whether it held up.

### Analysis Steps

**4.1 Revenue Architecture**
- What were the revenue streams at IPO? What percentage from each?
- What was the stated growth strategy for revenue?
- Was there revenue concentration risk? (top customers, single product)

**4.2 Cost Structure & Unit Economics**
- What were the major cost categories?
- What was the gross margin? Operating margin?
- Was the company profitable? If not, what was the path to profitability?
- Were there structural cost advantages or disadvantages?

**4.3 Cash Flow Quality**
- Was the company cash flow positive from operations?
- What was the cash conversion cycle?
- Were there significant differences between reported profit and actual cash generation?

**4.4 Business Model Evolution Verification**
- Compare IPO-era revenue mix with current revenue mix
- Did the money-making logic stay the same or fundamentally change?
- Which revenue streams grew, shrank, or were abandoned?
- Did the company find new revenue streams not mentioned in the prospectus?

**Key insight to extract**: The gap between "how we make money" at IPO and "how we actually make money" years later reveals whether the original business model was robust or the company had to reinvent itself.

---

## Module 5: Governance & Decision Space

**Goal**: Understand how the ownership and governance structure shapes what the company CAN do.

### Analysis Steps

**5.1 Founder Control**
- What is the founder's ownership percentage?
- Is there a dual-class share structure? If so, what's the voting power ratio?
- Are there any special governance mechanisms? (e.g., Alibaba's partnership system)

**5.2 Investor Structure**
- Who are the major pre-IPO investors?
- What are their lock-up periods?
- Do any investors have board seats, veto rights, or other control mechanisms?
- Are there strategic investors (vs. purely financial) that might influence direction?

**5.3 Option Pool & Incentive Design**
- What percentage is reserved for employee options?
- How is the option pool structured? (cliff, vesting, strike price)
- Does the incentive design align with long-term or short-term behavior?

**5.4 Governance Impact Verification**
- How did the governance structure actually affect major decisions post-IPO?
- Were there founder-investor conflicts? Board battles?
- Did the governance structure enable or constrain strategic pivots?

**Key insight to extract**: Governance is not boring legal detail — it directly determines what decisions a company can make. Alibaba's partnership system, Google's dual-class shares, and Snap's no-vote public shares all had profound strategic consequences.

---

## Module 6: Capital Allocation Verification

**Goal**: Compare how the company said it would use IPO proceeds with what it actually did.

### Analysis Steps

**6.1 Stated Use of Proceeds**
- How did the prospectus say the IPO funds would be used?
- Were the allocations specific or vague? ("general corporate purposes" is a red flag for lack of plan)
- What percentage was earmarked for R&D, sales, acquisitions, debt repayment?

**6.2 Actual Capital Deployment**
- Track major expenditures, acquisitions, and investments in the 3-5 years post-IPO
- Compare actual spending patterns with stated intentions
- Were there significant unplanned expenditures or abandoned plans?

**6.3 Plan-Driven vs. Opportunity-Driven Assessment**
- Did the company follow its stated plan, or pivot opportunistically?
- Is the management team more "plan and execute" or "sense and respond"?
- Neither is inherently better — but the gap between stated and actual reveals management style

**Key insight to extract**: "General corporate purposes" means "we'll figure it out." Specific allocation that actually gets followed means disciplined execution. Specific allocation that gets abandoned might mean rigid thinking or market shift. Each pattern tells a story about management quality.

---

## Output Format Guidelines

- **Full archaeology**: Produce a markdown document covering all 6 modules, with specific references from the prospectus (paraphrased, with section references) and verification data
- **Quick scan**: Summary conversation covering modules 1-3
- **Comparison mode**: Side-by-side analysis of two companies' IPO filings

Always note the IPO date prominently — all analysis is anchored to that moment in time.

When web search is available, ALWAYS search for:
1. The actual filing on SEC EDGAR or equivalent
2. Current company status for verification
3. Major post-IPO events for context

---

## Reference: Analysis Checklist

**Module 1 — Track Definition**
- [ ] Company's self-definition at IPO extracted
- [ ] Explicit boundaries and exclusions noted
- [ ] Strategic drift verified against current state

**Module 2 — Competitive Perception**
- [ ] Named competitors listed
- [ ] "Missing competitors" identified (later threats not mentioned)
- [ ] Competitive outcome verified

**Module 3 — Risk Prophecy**
- [ ] Major risk factors catalogued and categorized
- [ ] Each risk verified: materialized, didn't happen, or still pending
- [ ] Biggest unlisted risk identified

**Module 4 — Business Model**
- [ ] Revenue streams and percentages at IPO mapped
- [ ] Cost structure and margins analyzed
- [ ] Cash flow quality assessed
- [ ] Current revenue mix compared with IPO-era

**Module 5 — Governance**
- [ ] Founder control mechanisms identified
- [ ] Investor structure and influence mapped
- [ ] Governance impact on post-IPO decisions traced

**Module 6 — Capital Allocation**
- [ ] Stated use of proceeds extracted
- [ ] Actual deployment tracked
- [ ] Management style assessed (plan-driven vs. opportunity-driven)
