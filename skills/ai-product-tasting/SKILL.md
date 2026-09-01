---
name: ai-product-tasting
description: >
  AI product deep-dive and teardown framework. Conducts structured multi-dimensional analysis of any AI product,
  covering product decision drivers, core feature technical implementation, interaction design,
  competitive landscape, and business strategy.
  ALWAYS use this skill when the user wants to: analyze/review/study an AI product, do a product teardown or deep dive,
  compare AI products or agents, understand how a specific AI feature works under the hood,
  evaluate competitive landscape of AI tools. Trigger for any AI product analysis intent.
  Also trigger when the user wants to build a competitive brief or product strategy analysis
  involving AI/agent products.
---

# AI Product Tasting Framework

A structured methodology for deep analysis of AI products — especially agent products, copilots, and AI-native tools. Produces a multi-phase teardown that covers why the product exists, how it works, how users interact with it, where it sits in the competitive landscape, and what strategic lessons to draw.

This framework is model-agnostic: it works for Claude, ChatGPT, Codex, Gemini, or any AI assistant with web search capability.

---

## How to Use This Skill

### Quick Start

When the user names a target product, run through all 5 phases in order. Each phase produces a structured deliverable. Adapt depth to the user's intent:

- **Quick scan** → Run Phases 1-3 at summary depth (one conversation)
- **Deep dive** → Run all 5 phases at full depth (multi-session, with documents)
- **Comparison** → Jump to Phase 4 format, but do lightweight Phase 1-2 for each product first

### Before You Begin

1. **Identify the target product** — confirm with the user which specific product/feature to analyze
2. **Determine scope** — is this a full deep dive or a quick scan?
3. **Check user context** — are they a PM, engineer, founder, or general learner? This affects which angles to emphasize

---

## Phase 1: WHY — Product Decision Archaeology

**Goal**: Understand why this product exists, what problem it solves, and what strategic forces drove its creation.

**Research actions**:
- Search for the product's launch announcement and founding team interviews
- Search for the predecessor product (if any) and its known limitations
- Search for the parent company's product timeline and strategic context
- Search for market conditions at launch time

**Analysis structure**:

### 1.1 Company Stage & Positioning

Why is THIS company the one building this product? Analyze:
- The company's development stage and core competencies at launch time
- What structural advantages (technology, data, distribution, ecosystem) enabled this product
- How the product fits into the company's broader strategic arc

### 1.2 Predecessor Limitations

What existed before? What were its structural (not just feature-level) limitations? Focus on paradigm constraints, not missing buttons.

### 1.3 Evolution Path

Reconstruct how the product evolved — from internal prototype to public launch. Look for:
- Internal dogfooding signals (did the company use it themselves first?)
- Key inflection points (what capability or insight unlocked the product?)
- What was tried and abandoned?

### 1.4 Enabling Conditions

Why now? Three forces to check:
- **Model capability**: What model advancement made this product viable?
- **Infrastructure maturity**: What protocols, APIs, or ecosystems had to exist first?
- **Business strategy**: What commercial pressure or opportunity drove the timing?

### 1.5 Core Architecture Decision

Identify the ONE foundational design decision that everything else follows from. Every product has one. Examples: "one Claude per channel" (Claude Tag), "model-agnostic open protocol" (MCP), "embedded in every Office app" (Copilot). Trace the cascading consequences of this decision.

**Deliverable**: A narrative document or conversation covering 1.1–1.5, with citations.

---

## Phase 2: HOW — Core Feature Technical Teardown

**Goal**: Understand how the product's key capabilities actually work — not at marketing level, but at architecture and design level.

**Research actions**:
- Search for technical blog posts, engineering talks, and documentation
- Search for developer community analysis and reverse-engineering posts
- Search for the product's API/SDK documentation (reveals internal architecture)
- Read the product's official docs thoroughly

**Analysis structure**:

### 2.1 Feature Inventory

List the product's 3-5 core differentiating features. For each, answer:
- What does this feature do that others don't?
- What is the hardest technical challenge in making it work?

### 2.2 Per-Feature Deep Dive

For each core feature, analyze:

**Storage & Data Architecture**
- What data does this feature need to persist?
- How is it structured? (flat files, vector DB, knowledge graph, hybrid?)
- What is the "memory temperature" model? (hot = always loaded, warm = indexed for retrieval, cold = archived)

**Runtime Mechanism**
- How does the feature work during execution?
- What triggers it? (user action, timer, event, model judgment?)
- What is the decision flow? (rule-based, model-based, hybrid?)

**Trade-off Awareness**
- What does this feature sacrifice? (latency, cost, accuracy, privacy?)
- What are the known failure modes?
- What constraints does the harness layer impose vs. what the model decides?

### 2.3 Ecosystem Position & Internal Relationships

- Where does this product sit within its parent app or platform ecosystem?
- What is its relationship with other products/features in the same family?
- How do internal products feed into or depend on each other?

### 2.4 Feature Interdependency Map

How do the core features depend on each other? Draw the dependency graph. The insight is usually that the features form an inseparable system, not an independent feature list.

**Deliverable**: A technical analysis document with architecture diagrams (text-based is fine) and trade-off tables.

---

## Phase 3: INTERACTION — User Experience Teardown

**Goal**: Understand how users actually interact with the product — the design philosophy, interaction patterns, trust mechanisms, and edge cases.

**Research actions**:
- Search for user reviews, tutorials, and "how I use X" posts
- Search for the product's UX documentation or design guidelines
- Try the product yourself if possible, or find demo videos
- Search for criticism and complaint threads

**Analysis structure**:

### 3.1 Core Metaphor

Every AI product is built around a metaphor that shapes all interaction design:
- Tool? (open → use → close)
- Assistant? (ask → receive → done)
- Colleague? (delegate → leave → review)
- Employee? (configure → monitor → evaluate)

Identify the metaphor and trace how it constrains design decisions.

### 3.2 Interaction Modes

Map all the ways users can interact with the product:
- What triggers AI action? (explicit command, @mention, ambient, scheduled?)
- What is the feedback loop? (streaming, checklist, status updates, final delivery?)
- What are the visibility rules? (who sees what the AI is doing?)

### 3.3 Growth & Distribution Mechanics

Analyze the product's user acquisition and engagement architecture:
- What are the traffic entry points? How does the platform funnel users to this product?
- What is the activation flow from first exposure to regular use?
- What are the conversion rates at each stage (if observable)?
- What retention and engagement loops exist?

### 3.4 Sub-Feature Anatomy & Competitive Benchmarking

Break the product into its constituent sub-features and compare at granular level:
- Page architecture, UI elements, page-level functionality
- Copy, prompts, flow steps, error handling — how do these compare with competitors?
- What are the conversion and completion rates for key flows (if observable)?

### 3.5 Trust Architecture

How does the product build and maintain user trust?
- **Progressive trust**: Can users start small and escalate? What's the trust ladder?
- **Transparency**: Can users see what the AI is doing and why?
- **Intervention points**: Can users correct course mid-task?
- **Safety nets**: Is there a private/sandbox mode for low-risk experimentation?
- **Failure handling**: How does the product communicate limitations, errors, or refusals?

### 3.6 Design Taste Assessment

Evaluate subjective design quality:
- What did the team choose NOT to build? (restraint is taste)
- Does the UI add complexity or reduce it?
- Does the interaction feel native to the platform, or bolted on?
- Is the onboarding zero-learning-curve or configuration-heavy?

**Deliverable**: An interaction analysis with specific examples and design principle extractions.

---

## Phase 4: LANDSCAPE — Competitive & Strategic Analysis

**Goal**: Understand the product's position in the competitive landscape, how competitors are responding, and what strategic lessons emerge.

**Research actions**:
- Search for direct competitors and their latest announcements
- Search for analyst reports and comparison articles
- Search for the parent company's investor/earnings communications
- Search for partnership and ecosystem announcements

**Analysis structure**:

### 4.1 Competitor Mapping

Categorize competitors by their structural position:
- **Platform-native players**: Own both the workspace AND the model
- **Model-first players**: Strong model, hosted on others' platforms
- **Vertical players**: Bound to specific business systems
- **Indie/startup players**: New entrants with specific differentiation

### 4.2 Three-Dimensional Competition Framework

Evaluate every player on three axes:
- **Model Capability**: Raw reasoning, coding, analysis power
- **Context Density**: How much user/org data can the AI access natively?
- **Ecosystem Openness**: How easy is it to connect to third-party tools?

No player leads on all three. The gaps reveal each player's strategic bet.

### 4.3 Differentiated vs. Shared Capabilities

For each competitor and the target product:
- Which capabilities are unique differentiators?
- Which are table-stakes shared features?
- What underlying technology or ecosystem advantage enables each differentiator?

### 4.4 Imitation vs. Differentiation Matrix

For each competitor, answer:
- What did they copy from the target product?
- What did they deliberately do differently?
- What is their structural advantage that enables the differentiation?

### 4.5 Business Model & Moat Analysis

- How does each player monetize? (per-seat, per-token, bundled, free?)
- What is the lock-in mechanism? (data, workflow, ecosystem, switching cost?)
- What are the platform dependency risks? (who owns the distribution channel?)

### 4.6 Product Taste Comparison

Compare design philosophies across competitors:
- Who is most restrained? Most ambitious? Most pragmatic?
- Whose product feels most "inevitable" vs. most "forced"?

**Deliverable**: A competitive landscape document with comparison tables and strategic insight narrative.

---

## Phase 5: FRAMEWORK — Meta-Analysis & Transferable Insights

**Goal**: Extract generalizable lessons from the analysis that apply beyond this specific product.

### 5.1 Product Strategy Lessons

What does this product's success/approach teach about:
- Timing (when to launch, what capabilities to wait for)
- Positioning (model-first vs. platform-first vs. vertical)
- Build vs. integrate decisions

### 5.2 Design Pattern Library

What reusable interaction or architecture patterns emerged?
Examples from Claude Tag analysis:
- "Thread as work unit" — using messaging threads as task containers
- "Checklist progress" — dynamic task lists for async trust
- "Agent identity" — independent service accounts for AI
- "Ambient mode" — rule trigger + model judgment + hard constraints
- "Progressive trust ladder" — low-risk queries → complex tasks → autonomous mode

### 5.3 Supporting Systems Assessment

Beyond surface-level product features, analyze the non-functional supporting systems:
- **Risk control**: What safety, compliance, and abuse prevention mechanisms exist?
- **Operations**: What human operations and support structures are behind the product?
- **Marketing & growth**: What go-to-market strategy was used?
- **Data & analytics**: What instrumentation and measurement infrastructure exists?
- **Storage & infrastructure**: What infrastructure choices support the product at scale?

### 5.4 For the User's Own Work

Connect the analysis back to the user's own product/work context:
- What can they directly apply?
- What should they deliberately NOT copy (and why)?
- What gaps in their own product does this analysis reveal?

### 5.5 Open Questions

What did the analysis NOT resolve? What would require hands-on use, insider knowledge, or more time to understand?

**Deliverable**: A synthesis document with transferable patterns and personalized recommendations.

---

## Output Format Guidelines

- **Full deep dive**: Produce a markdown document per phase, with clear headers, tables where appropriate, and citations to sources
- **Quick scan**: Produce a single structured conversation covering all phases at summary depth
- **Comparison mode**: Produce a single document with side-by-side analysis

Adapt language to the user's preference. Default to the language the user is speaking.

When web search is available, ALWAYS search before analyzing — do not rely solely on training data, especially for recent products. AI products change rapidly; information from even 3 months ago may be outdated.

---

## Reference: Analysis Checklist

**Phase 1 — WHY**
- [ ] Company stage and positioning analyzed
- [ ] Predecessor product identified and limitations analyzed
- [ ] Company product timeline reconstructed
- [ ] Enabling conditions (model, infrastructure, business) checked
- [ ] Core architecture decision identified and consequences traced

**Phase 2 — HOW**
- [ ] 3-5 core features identified
- [ ] Each feature's storage, runtime, and trade-offs analyzed
- [ ] Ecosystem position and internal relationships mapped
- [ ] Feature interdependency map drawn
- [ ] Harness vs. model responsibility boundary clarified

**Phase 3 — INTERACTION**
- [ ] Core metaphor identified
- [ ] All interaction modes mapped
- [ ] Growth and distribution mechanics analyzed
- [ ] Sub-feature anatomy benchmarked against competitors
- [ ] Trust architecture analyzed
- [ ] Design taste assessed (what was NOT built)

**Phase 4 — LANDSCAPE**
- [ ] Competitors categorized by structural position
- [ ] Three-dimensional framework applied
- [ ] Differentiated vs. shared capabilities identified
- [ ] Imitation vs. differentiation matrix filled
- [ ] Business model and lock-in analyzed

**Phase 5 — FRAMEWORK**
- [ ] Strategy lessons extracted
- [ ] Reusable design patterns named
- [ ] Supporting systems assessed
- [ ] User's own work connected
- [ ] Open questions listed
