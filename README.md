# 🔬 AI Business Anatomy

A suite of three AI skills for deep company analysis — covering products, IPO filings, and the intersection of both.

Model-agnostic: works with Claude, ChatGPT, Codex, Gemini, or any AI assistant.

---

## The Three Skills

| Skill | What It Does | When to Use |
|-------|-------------|-------------|
| **AI Product Tasting** | 5-phase product teardown (WHY → HOW → INTERACTION → LANDSCAPE → FRAMEWORK) | Analyzing any AI product's design, technology, and competitive position |
| **IPO Archaeology** | 6-module prospectus analysis (Track → Competition → Risk → Business Model → Governance → Capital) | Studying a public company's strategic evolution through its IPO filing |
| **Auto Analysis** | Autonomously detects listing status + product profile, dispatches to the right skill(s), synthesizes results | When you want comprehensive analysis and let the AI decide the best approach |

## Auto Analysis: How It Works

Just name a company. Auto Analysis checks two things — does it have a public filing? Does it have a notable product? — then picks the right mode:

| Mode | When | What You Get |
|------|------|-------------|
| **Product Only** | Pre-IPO + has products (e.g., Anthropic) | 5-phase product teardown |
| **IPO Only** | Listed + interest is business/strategy (e.g., Baidu's 2005 F-1) | 6-module prospectus archaeology |
| **Combined** | Listed + has products (e.g., Tesla, Unitree) | Both analyses + cross-verification synthesis |

Combined Mode is where things get interesting — it finds insights that neither framework alone can produce, like contradictions between what the prospectus promised and what the product actually became.

## Installation

### Download the full suite (recommended)

```bash
git clone https://github.com/D1One-hue/ai-business-anatomy.git
```

### Download a single skill only

If you only need one skill, you can download it individually using `curl`:

**AI Product Tasting only:**
```bash
mkdir -p ai-product-tasting && \
curl -sL https://raw.githubusercontent.com/D1One-hue/ai-business-anatomy/main/skills/ai-product-tasting/SKILL.md \
  -o ai-product-tasting/SKILL.md
```

**IPO Archaeology only:**
```bash
mkdir -p ipo-archaeology && \
curl -sL https://raw.githubusercontent.com/D1One-hue/ai-business-anatomy/main/skills/ipo-archaeology/SKILL.md \
  -o ipo-archaeology/SKILL.md
```

**Auto Analysis only** (will reference the other two skills if they're in the same `skills/` directory):
```bash
mkdir -p auto-analysis && \
curl -sL https://raw.githubusercontent.com/D1One-hue/ai-business-anatomy/main/skills/auto-analysis/SKILL.md \
  -o auto-analysis/SKILL.md
```

### Use as Claude Skills

Place the `skills/` folder (or individual skill folders) in your Claude skills directory. Auto Analysis will trigger on broad company analysis requests; the individual skills trigger on product-specific or IPO-specific requests.

### Use with any AI assistant

Copy the relevant `SKILL.md` content into a system prompt or paste at the start of a conversation. For combined analysis, include all three skills.

## Key Frameworks Inside

### Three-Dimensional Competition (from Product Tasting)

Evaluate any AI product landscape on three axes:
- **Model Capability** — reasoning, coding, analysis power
- **Context Density** — how much user/org data the AI accesses natively
- **Ecosystem Openness** — how easy to connect third-party tools

### The Missing Competitor Pattern (from IPO Archaeology)

The most dangerous competitive threats often come from companies not even named in the original prospectus. Identifying who's NOT in the filing is more revealing than who is.

### Cross-Verification (from Auto Analysis Combined Mode)

When product analysis and prospectus analysis are layered together:
- Does the product architecture actually support the stated business model?
- Did governance decisions visibly shape product choices?
- Are there product-level risks the prospectus never anticipated?

## Repo Structure

```
ai-business-anatomy/
├── README.md                                    # English
├── README_CN.md                                 # Chinese
└── skills/
    ├── ai-product-tasting/
    │   └── SKILL.md                             # Product analysis framework
    ├── ipo-archaeology/
    │   └── SKILL.md                             # IPO filing analysis framework
    ├── auto-analysis/
    │   └── SKILL.md                             # Autonomous analysis engine
    └── references/
        └── claude-tag-case-study.md             # Example: Claude Tag analysis
```

## Example Prompts

```
Analyze Anthropic — products, strategy, everything
```
```
Do an IPO archaeology on Baidu's 2005 F-1 filing
```
```
Deep dive into Claude Tag as a product
```
```
Compare Tesla's S-1 vision with what FSD actually became
```

## Origin Story

This framework suite was born from a multi-session product study of Claude Tag (Anthropic's shared AI teammate for Slack). The analysis covered Anthropic's product timeline, Claude Tag's memory/ambient/multiplayer architecture, competitive landscape, and strategic implications. The process was then generalized into reusable frameworks and combined with an IPO prospectus analysis methodology for full-spectrum company intelligence.

## License

MIT — use it however you like.

---

*Built by [D1One-hue](https://github.com/D1One-hue) · Powered by a conversation with Claude*
