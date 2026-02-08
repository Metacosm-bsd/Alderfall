# Alderfall Agent Architecture

## Design Principles

Every agent in Alderfall follows these rules:

1. **Dual-environment** — Works in both Cowork (conversational) and Claude Code (command-line)
2. **Plain language** — Accepts natural language inputs, returns clear explanations
3. **Data-grounded** — Pulls from real data in the project folders, not guesswork
4. **Composable** — Agents can hand off to each other (e.g., Stewardship Planner asks Forest Analyst for data)
5. **Logged** — Every recommendation and action is recorded for review

---

## Agent Roster

### 1. Research Scout
**Purpose:** Find, summarize, and organize academic research and external data relevant to Alderfall.

**What it does:**
- Searches for academic papers on forest management topics
- Summarizes findings in plain language
- Saves summaries to `research/academic/`
- Tracks which topics have been researched and where gaps remain

**Example use:** "Research Scout, what does current science say about thinning mixed hardwood stands for carbon sequestration?"

---

### 2. Forest Analyst
**Purpose:** Analyze ecological data about the forest — inventory, health, biodiversity, risks.

**What it does:**
- Reads inventory data from `ecology/inventory/`
- Calculates metrics (basal area, species diversity, canopy density, etc.)
- Flags concerns (disease, invasive species, fire risk)
- Produces ecological health reports saved to `ecology/analysis/`

**Example use:** "Forest Analyst, what's the current species composition and are there any stands that need attention?"

---

### 3. Financial Tracker
**Purpose:** Manage the financial side — costs, revenues, projections, tax strategy.

**What it does:**
- Tracks expenses and income in `corporate/financials/`
- Models revenue scenarios (timber harvest, carbon credits, grants)
- Calculates tax implications of different actions
- Produces financial reports and forecasts

**Example use:** "Financial Tracker, if we do a selective harvest in the north stand this fall, what's the projected net revenue after taxes?"

---

### 4. Stewardship Planner
**Purpose:** The "brain" — recommends actions based on your goals, the data, and the research.

**What it does:**
- Takes your stated goals (e.g., "maximize biodiversity while maintaining financial sustainability")
- Pulls data from Forest Analyst and Financial Tracker
- References research from Research Scout
- Produces prioritized action plans saved to `ecology/plans/`
- Models scenarios and trade-offs

**Example use:** "Stewardship Planner, I want to improve wildlife habitat in the riparian areas while keeping the property financially self-sustaining. What should I do this year?"

---

### 5. Corporate Advisor
**Purpose:** Guidance on ownership structure, legal considerations, tax optimization, and compliance.

**What it does:**
- Advises on entity structure (LLC, trust, easement)
- Tracks regulatory requirements and deadlines
- Models tax strategies
- Saves corporate documents and notes to `corporate/structure/`

**Example use:** "Corporate Advisor, should I put a conservation easement on the wetland areas? What are the financial and legal implications?"

---

### 6. Data Collector
**Purpose:** Process, clean, and organize incoming data from any source.

**What it does:**
- Ingests raw data (CSVs, spreadsheets, field notes, satellite data)
- Cleans and structures it into standard formats
- Saves processed data to `data/processed/`
- Flags data quality issues

**Example use:** "Data Collector, I just uploaded a spreadsheet of tree measurements from the field. Process it and add it to the inventory."

---

## How Agents Work Together

```
You ask a question or set a goal
        │
        ▼
┌─────────────────────┐
│  Stewardship Planner │  ← Orchestrates the response
└─────────┬───────────┘
          │
    ┌─────┼──────┬──────────┐
    ▼     ▼      ▼          ▼
 Forest  Financial Research  Corporate
 Analyst Tracker  Scout     Advisor
    │     │       │          │
    ▼     ▼       ▼          ▼
  ecology/ corporate/ research/ corporate/
  data/    financials  academic   structure
```

**Example workflow:** You ask, "Should I thin the oak stand this year?"

1. **Stewardship Planner** receives the question
2. Asks **Forest Analyst**: "What's the current state of the oak stand?"
3. Asks **Financial Tracker**: "What would a selective harvest yield financially?"
4. Asks **Research Scout**: "What does the research say about oak thinning timing and methods?"
5. Combines all inputs into a recommendation with clear reasoning

---

## Technical Implementation

Each agent is built as a **Claude skill** with:
- A `SKILL.md` file (instructions and best practices)
- Supporting data templates and schemas
- Access to the Alderfall folder structure

**For Cowork:** Agents are invoked through natural conversation or as skills
**For Claude Code:** Agents are invoked as slash commands or through the task system

---

## Build Order

| Priority | Agent | Reason |
|----------|-------|--------|
| 1 | Research Scout | Needed first to build the knowledge base |
| 2 | Data Collector | Needed to process incoming forest data |
| 3 | Forest Analyst | Core ecological analysis capability |
| 4 | Financial Tracker | Financial modeling and tracking |
| 5 | Corporate Advisor | Structure and compliance guidance |
| 6 | Stewardship Planner | Needs all other agents working first |

---

*This is a living document. Architecture will evolve as we build and learn.*
