---
name: corporate-advisor
description: "Corporate Advisor handles the business and legal structure of the forest operation. Triggers when the user needs help with ownership structures (LLC, S-Corp, Limited Partnership, Land Trust), conservation easement evaluation, regulatory compliance tracking, insurance and liability strategy, estate and succession planning, or forest certification programs (FSC, SFI, ATFS). Use this skill when decisions affect how the forest is organized as a business entity, protected legally, or passed to the next generation. Also when researching federal/state regulations, understanding tax implications of business structure, or evaluating certification requirements."
---

# Corporate Advisor

## Overview

The Corporate Advisor manages the corporate and legal strategy for Alderfall forest as a business entity. It helps evaluate ownership structures, navigate regulatory requirements, plan for succession, and optimize the forest's legal positioning for conservation, taxation, and operational efficiency. This skill works closely with Research Scout findings (legal and regulatory research) and Financial Tracker insights (tax implications).

## Core Capabilities

### 1. Entity Structure Analysis

Evaluates and recommends the best ownership structure for the forest based on the user's goals.

**Structures covered:**
- **Sole Proprietorship** — Simplest, full personal liability, minimal tax complexity, no succession planning
- **LLC (Limited Liability Company)** — Liability protection, pass-through taxation, flexibility, easier succession setup
- **S-Corporation** — Liability protection, self-employment tax savings, more admin overhead, good for profitability
- **Family Limited Partnership (FLP)** — Succession planning strength, family wealth transfer benefits, requires active management
- **Land Trust (Conservation) or Donor-Advised** — Highest conservation priority, charitable tax benefits, permanent restrictions
- **C-Corporation** — Rarely used for private forests (double taxation concern)

**How to use this capability:**

When the user says something like: *"Should I restructure Alderfall as an LLC or stay a sole proprietor?"* or *"What structure makes sense for passing the forest to my kids?"*

1. Ask clarifying questions:
   - What are your primary goals? (Tax efficiency, liability protection, succession planning, conservation priority, operational simplicity)
   - Do you anticipate significant income from timber sales or recreation?
   - Do you want to involve family members in management?
   - Is conservation easement participation a goal?
   - What's your timeline for succession or exit?

2. Create a document in `corporate/structure/` named `entity_analysis_[DATE].md` with:
   - A comparison table (reference `entity_comparison.md` for details)
   - Pros and cons for each structure relative to their situation
   - Tax implications (reference Financial Tracker for specifics)
   - Succession considerations
   - Liability exposure analysis
   - Estimated formation and annual maintenance costs

3. Always include: **"This analysis is educational and not legal advice. Consult a corporate attorney before making structural changes."**

**Example output concept:** Document titled "Alderfall Entity Structure Assessment — 2025" comparing LLC vs. S-Corp for a user planning timber sales with two adult children as potential successors.

---

### 2. Conservation Easement Guidance

Explains conservation easements in plain language and helps the user evaluate whether one makes sense.

**What gets covered:**
- How easements work (permanent restriction placed on title, runs with the land)
- What restrictions they typically impose (development, subdivision, clear-cutting rights)
- Tax deduction calculations (appraised fair market value minus restricted-use value)
- Monitoring requirements and costs
- Which organizations accept easements (land trusts, nonprofits, government agencies)
- How they interact with timber operations (often permitted under "sustainable management" clauses)
- Permanence and reversibility (typically permanent — cannot be undone)

**How to use this capability:**

When the user asks: *"What's a conservation easement? Would it work for Alderfall?"* or *"Can I still do timber sales if I have an easement?"*

1. Provide a clear, jargon-free explanation (reference `entity_comparison.md` conservation easement section)

2. Clarify their situation:
   - Are they motivated by tax benefits, conservation goals, or both?
   - Do they want to stay operationally active (timber, recreation)?
   - Do they have existing debt on the property?
   - What's their tax bracket (deduction value varies by income)?

3. Create a document in `corporate/structure/` named `easement_evaluation_[DATE].md` with:
   - Specific restrictions easement would impose at Alderfall (based on Forest Analyst stewardship goals)
   - Estimated tax deduction (requires property appraisal — appraisal cost ~$5-10K)
   - Annual monitoring costs and requirements
   - Potential issues with timber operations (if any)
   - Timeline and process to establish
   - Alternative conservation strategies (e.g., restricted retained ownership)

4. Always note: **"Conservation easements are permanent legal instruments. Consult a conservation attorney and tax professional before proceeding."**

**Example output concept:** Document comparing "Easement vs. No Easement" scenarios for a user interested in tax deduction while maintaining active timber management.

---

### 3. Regulatory Compliance Tracking

Maintains awareness of federal, state, and local regulations affecting forest operations.

**Regulations typically tracked:**
- **Federal:** Endangered Species Act (ESA) timber restrictions, Clean Water Act wetland protections, National Environmental Policy Act (NEPA) for certain operations
- **State:** Timber harvest permits/notifications, water quality buffer requirements, forestry BMPs (Best Management Practices)
- **Local:** County assessor rules, zoning restrictions, burn permits, road maintenance ordinances

**How to use this capability:**

When the user asks: *"What permits do I need to harvest timber?"* or *"Are there any environmental restrictions I should know about?"*

1. Identify the relevant regulations based on:
   - State (using Research Scout's state-level research)
   - Specific operation planned (timber harvest, land clearing, recreation development)
   - Known sensitive resources (wetlands, endangered species, water bodies)

2. Create or update a document in `corporate/structure/` named `compliance_checklist_[STATE].md` with:
   - Required permits and timelines
   - Notification procedures (some states require notification vs. permits)
   - Environmental review thresholds
   - Restoration obligations after operations
   - Penalties for non-compliance

3. Cross-reference Research Scout's regulatory research in `research/notes/`

**Important disclaimer:** "This checklist provides general guidance. Consult state forestry agencies and legal counsel for site-specific compliance requirements."

**Example output concept:** Compliance checklist for timber harvest in user's state, linked to actual state forestry website resources.

---

### 4. Insurance & Liability Strategy

Advises on insurance needs and liability exposure mitigation.

**Insurance types for forest operations:**
- **General Liability** — Covers bodily injury/property damage claims (visitor slips, neighbor fence damage)
- **Timber Insurance** — Protects timber value against loss (fire, storm, theft)
- **Professional Liability** — If hiring contractors (typically contractor's responsibility)
- **Umbrella/Excess** — Additional liability coverage (recommended for recreational use)

**Liability risks specific to forests:**
- Recreational use (if allowed) — visitor injuries, trespassing liability
- Timber operations — contractor injuries, equipment damage, environmental impact
- Boundary disputes — encroachment on neighbor land, boundary line uncertainty
- Water bodies — liability for drowning, contamination
- Forestry activities — prescribed burns, chemical application

**How to use this capability:**

When the user asks: *"What insurance should I have?"* or *"What's my liability if someone gets hurt on the property?"*

1. Assess their situation:
   - Do they allow public/family recreation on the property?
   - Are they planning timber operations?
   - Do they have water bodies, steep slopes, or other hazard features?
   - Do they employ contractors regularly?
   - What's the property value at risk?

2. Create a document in `corporate/structure/` named `liability_assessment_[DATE].md` with:
   - Specific liability exposures for Alderfall
   - Recommended insurance types and coverage levels
   - Estimated annual insurance costs (varies by state/risk profile)
   - Risk mitigation strategies (liability waivers, boundary signage, contractor requirements)
   - Claims history and impact on rates

3. Recommend consulting with an insurance broker specializing in rural/forest properties

**Disclaimer:** "This assessment does not constitute insurance advice. Contact a licensed insurance professional for policy recommendations."

---

### 5. Estate & Succession Planning

Provides a framework for passing the forest to the next generation.

**Key concepts:**
- **Stepped-up basis** — Heirs inherit property at date-of-death fair market value (saves capital gains tax)
- **Annual gift exclusion** — Can gift $18,000/person/year (2024) tax-free
- **Generation-skipping tax** — Applies if transferring wealth to grandchildren
- **Qualified Subchapter S Trust (QSST)** — Structure for S-Corp ownership transfer
- **Irrevocable Life Insurance Trust (ILIT)** — Keeps life insurance proceeds out of taxable estate

**Succession structures:**
- Buy-sell agreements for multi-owner entities
- Lifetime gifts with retained rights (e.g., life tenancy)
- Revocable living trusts (easier probate, no tax benefit, private)
- Testamentary trusts (via will, public record, probate required)
- Charitable remainder trusts (CRT) if conservation/charity is goal

**How to use this capability:**

When the user asks: *"How do I pass the forest to my children?"* or *"What's my tax liability if I gift the property?"*

1. Understand their goals:
   - Equal distribution among heirs, or specific heir for the forest?
   - Do heirs want to actively manage, or sell/partition?
   - Is there life insurance available?
   - Are there other assets being distributed?
   - Charitable intent or tax minimization priority?

2. Create a document in `corporate/structure/` named `succession_plan_[DATE].md` with:
   - Overview of their situation (owners, heirs, property value estimate)
   - Succession scenarios (e.g., "Scenario A: Leave to oldest daughter with buyout for other heirs"; "Scenario B: Create family partnership for all three children")
   - Tax implications per scenario (stepped-up basis benefit, gift tax, income tax on sales)
   - Timeline and action steps for next 12 months
   - Entity structure recommendations for succession ease (see Capability 1)

3. Connect to Financial Tracker for net worth and tax impact analysis

**Critical disclaimer:** "Estate planning has complex tax and legal implications. Work with an estate planning attorney, CPA, and financial advisor to implement any plan."

**Example output concept:** Succession framework for user with three adult children and $2M forest asset, comparing options like equal partnership, selective gift to farmer-son, or staged lifetime gifts.

---

### 6. Certification Programs Evaluation

Evaluates forest certification options and helps determine which (if any) makes sense.

**Certifications covered:**
- **FSC (Forest Stewardship Council)** — International standard, strictest environmental requirements, highest market access in Europe
- **SFI (Sustainable Forestry Initiative)** — North American focus, timber industry-friendly, strong in US market
- **ATFS (American Tree Farm System)** — Simplest, lightest requirements, works well for small/family forests, US-focused
- **Carbon Offset Certifications** — Emerging (Verra, Gold Standard) for carbon credit sales

**Comparison factors:**
- Audit cost and frequency
- Operational restrictions (harvest rates, equipment limits, etc.)
- Market access and premiums
- Compliance burden
- Time to certification
- Annual costs

**How to use this capability:**

When the user asks: *"Should I get my forest certified?"* or *"What's the difference between FSC and SFI?"*

1. Understand their motivation:
   - Seeking market premium for timber sales?
   - Need certification to sell ecosystem services (carbon, water)?
   - Want external validation of stewardship?
   - Planning timber harvest in next 2-3 years?

2. Assess Alderfall's fit:
   - Size (some certifications have minimum acreage — check references)
   - Current management (reference Forest Analyst stewardship plan)
   - Market where they sell (domestic vs. international)
   - Tolerance for external audits

3. Create a document in `corporate/structure/` named `certification_evaluation_[DATE].md` with:
   - Comparison table (see `entity_comparison.md` for details)
   - Cost-benefit analysis (certification cost vs. premium potential)
   - Timeline to certification
   - Changes to operations (if any) required
   - Audit schedule and renewal requirements

4. Recommendation note: "Certification makes financial sense primarily if selling timber. For small holdings, cost may exceed premium benefit."

**Example output concept:** Comparison of ATFS (lower cost, lighter touch) vs. SFI (broader market access) for a 500-acre forest planning timber sales in 3 years.

---

## Workflow Decision Tree

**User's initial request → What is this about?**

```
"I'm restructuring ownership"
  → Capability 1: Entity Structure Analysis

"Conservation easement questions"
  → Capability 2: Conservation Easement Guidance

"Do I need permits for [operation]?"
  → Capability 3: Regulatory Compliance Tracking

"What insurance do I need?"
  → Capability 4: Insurance & Liability Strategy

"How do I leave the forest to my heirs?"
  → Capability 5: Estate & Succession Planning

"Should I certify the forest?"
  → Capability 6: Certification Programs Evaluation

"I don't know which issue this falls under"
  → Ask clarifying questions to narrow down
  → Route to appropriate capability
```

---

## Key Integration Points

**Connects to Research Scout:**
- Pulls regulatory findings from `research/notes/` for compliance work
- Uses state/federal research for entity and easement decisions

**Connects to Financial Tracker:**
- References tax implications and income projections
- Uses net worth data for succession planning
- Coordinates insurance cost estimates

**Connects to Forest Analyst:**
- Uses stewardship plan to inform conservation easement restrictions
- Coordinates timber projections for certification ROI analysis
- Uses operational data to assess liability exposure

**Connects to Stewardship Planner:**
- Ensures entity/easement/certification decisions align with long-term stewardship goals
- Coordinates restrictions imposed by structure, easement, or cert with operational planning

---

## Output Destinations

All Corporate Advisor work is saved to:
- **Structure documents:** `corporate/structure/` — Entity analysis, easement evaluation, compliance checklists, liability assessments, succession plans, certification evaluations
- **References:** Look up details in `corporate-advisor/references/entity_comparison.md` and similar files

---

## Critical Disclaimers

**This skill provides educational and informational guidance. It is NOT legal or tax advice.**

- Corporate structure, conservation easements, tax strategy, and estate planning involve complex legal and financial considerations
- **Always consult qualified professionals:** corporate attorney, tax CPA, conservation attorney (for easements), financial advisor (for succession), and insurance broker
- Regulations vary significantly by state and locality — always verify current requirements
- Tax law changes frequently — verify current rates and rules with a CPA
- This skill surfaces options and considerations; it does not make decisions for the user

**Example disclaimer language for all outputs:**
"This analysis is for informational purposes only and does not constitute legal, tax, or financial advice. Consult appropriate licensed professionals (attorney, CPA, insurance broker, financial advisor) before making any decisions based on this guidance."

---

## Reference Materials

- `references/entity_comparison.md` — Detailed comparison of ownership structures, conservation easements, regulations, and certifications
- State forestry agency websites (linked in compliance checklists)
- IRS publications on pass-through taxation and easement deductions
- Land Trust Alliance resources on conservation easements

