---
name: financial-tracker
description: Manages all financial aspects of forest ownership - tracks expenses and income, analyzes timber value and revenue potential, evaluates management costs vs. returns, handles tax-deductible items and capital gains treatment, and produces financial reports. Use this when you need spending summaries, revenue projections, timber valuations, cost-benefit analysis of management actions, tax planning guidance, or annual financial statements. Non-technical forest owners rely on this to understand their property's financial performance and make decisions about harvests, investments, and conservation strategies.
---

# Financial Tracker

## Overview

The Financial Tracker is your forest's accountant. It manages income and expenses, estimates the monetary value of standing timber, analyzes whether management actions (like thinning or replanting) make financial sense, handles the tax side of forest ownership, and produces annual financial reports. Since forest investments often span decades, this skill helps you understand the financial trajectory of your property and make informed decisions about harvests, conservation easements, and long-term stewardship.

## Core Capabilities

### 1. Budget & Expense Tracking

Analyze all spending on forest management from the financial transaction records. You can:

- **View spending summaries** by category (labor, equipment, road maintenance, etc.) and time period
- **Compare year-over-year expenses** to identify trends or anomalies
- **Understand tax deductibility** of each expense category
- **Generate budget vs. actual reports** to track whether you're staying within planned spending

**When you'd use this:** After a season of management work, to see total spending by category. When planning next year's budget. To identify which management activities cost the most.

**Example request:** "Show me a breakdown of what I spent on road maintenance, equipment, and labor in 2024. How does that compare to 2023?"

---

### 2. Revenue Analysis

Track income from timber sales, carbon credits, grants, and recreational leases. You can:

- **Summarize revenue by source** (timber, carbon, grants, leases, other income)
- **Compare revenue across years** to identify trends in sales activity
- **Project future revenue** based on inventory data, market conditions, and management plans
- **Understand revenue timing** (when income typically arrives)

**When you'd use this:** When selling timber or applying for grants. To forecast property cash flow. To understand income potential from different sources.

**Example request:** "What revenue did we get from timber sales vs. carbon credits over the last three years? How much should I expect from a harvest in the south stand based on current volume and market prices?"

---

### 3. Timber Valuation

Estimate the dollar value of standing timber on your property. You can:

- **Calculate board feet (BF) and cords** of merchantable timber by species and stand
- **Apply regional stumpage prices** (what buyers pay for trees still in the ground)
- **Scenario-plan harvest values** (e.g., "If I thin the north stand, how much revenue could I get?")
- **Show the math transparently** so you understand what assumptions drive the numbers

**When you'd use this:** To understand how much timber wealth you own. When deciding whether a harvest makes sense. For property valuations or insurance. For conversation with a timber buyer.

**Example request:** "Based on last year's inventory data, what's the estimated stumpage value of red oak in the east stand if we harvested today? Show the calculation."

---

### 4. Cost-Benefit Analysis

When considering a management action (thinning, replanting, road work, pest treatment), weigh the costs against expected returns. You can:

- **Estimate upfront costs** (labor, equipment, materials) using standard regional benchmarks
- **Project long-term revenue increases** (e.g., faster-growing thinned trees, future harvest from a replanted area)
- **Calculate net present value (NPV)** to see if the investment makes financial sense
- **Compare scenarios** (thin now vs. wait; plant now vs. leave to natural regen)

**When you'd use this:** Before approving a management action. To justify spending to a co-owner or lender. To understand the payback period of investments.

**Example request:** "If we spend $3,000 to thin the north stand, how much extra timber value will that create by harvest in 15 years? Is it worth it?"

---

### 5. Tax Strategy Support

Forest ownership has specific tax rules. This skill helps you track and plan for them. You can:

- **Identify Section 1231 timber gains** (special lower tax rate for timber harvests when held >1 year)
- **Track reforestation costs** that can be deducted over time instead of all at once
- **Understand conservation easement benefits** (donation of development rights can reduce taxes)
- **Summarize deductible management expenses** by tax category
- **Produce a tax-year summary** to give your CPA/accountant

**Important disclaimer:** This skill provides information and organization, but is NOT a substitute for a professional accountant or tax advisor. Every forest owner's situation is different. Always consult your CPA or tax professional before making final tax decisions.

**When you'd use this:** To organize receipts and expenses before tax season. To understand whether an action might qualify for special tax treatment. To document conservation efforts for charitable deductions.

**Example request:** "Show me all deductible expenses in 2024 and organize them by whether they're operating costs, capital improvements, or reforestation. I need this for my tax return."

---

### 6. Financial Reporting

Produce professional summaries of your property's financial health. You can:

- **Generate annual financial summaries** showing total income, total expenses, and net profit/loss
- **Create cash flow statements** to understand when money comes in and goes out
- **Update property valuations** based on timber inventory and market conditions
- **Produce reports suitable for banks, title companies, or co-owners**

**When you'd use this:** For annual record-keeping. When refinancing a mortgage. To share with co-owners or heirs. For insurance purposes.

**Example request:** "Create an annual financial summary for 2024 showing all revenue, all expenses by category, and the net result. Include a brief cash flow timeline."

---

## Workflow: Common Financial Tracker Tasks

### Starting a Financial Analysis

1. **You identify a question:** "Is the south stand worth harvesting?" or "What did we spend on management this year?"
2. **Gather transaction data:** The skill reads CSV files from `data/processed/financial/` containing all transactions
3. **Get inventory context:** The skill references stand valuations from the Forest Analyst
4. **Apply regional benchmarks:** The skill uses regional stumpage prices and cost benchmarks from its reference materials
5. **Do the math:** Calculate values, compare scenarios, show results with transparent reasoning
6. **Produce output:** Save a report to `corporate/financials/` that you can share, archive, or use for planning

---

## Key Assumptions & Limitations

**This skill assumes:**
- Financial transactions are recorded in the Data Collector's standard format (`transactions_YYYY.csv`)
- Inventory data has been collected (used for timber valuations)
- You understand forest management concepts (you don't need a finance degree, but context helps)

**This skill does NOT:**
- Provide legal or tax advice (always consult professionals for tax decisions)
- Make management recommendations on its own (it provides analysis so YOU decide)
- Replace a forester's field expertise (stumpage prices and costs are estimates)
- Account for species-specific market volatility or local buyer differences

**Financial estimates are only as good as the data.** If inventory is old or costs have changed significantly, results will be less accurate.

---

## References & Resources

This skill uses detailed financial benchmarks and formulas. See `references/forest_financial_reference.md` for:

- Regional stumpage price ranges (oak, pine, maple, etc.)
- Typical harvesting and road maintenance cost benchmarks
- Reforestation and replanting costs per acre
- Forester and professional service rate ranges
- Detailed explanation of Section 1231 capital gains treatment
- Reforestation tax deduction rules
- Conservation easement basics
- Carbon credit market overview
- Key financial formulas (NPV, IRR, Land Expectation Value, compound timber growth)

---

## Example Workflow: Evaluating a Harvest Decision

**Your question:** "A timber buyer approached about harvesting the east stand. Is the price fair? Will it make financial sense?"

**Steps the skill takes:**

1. **Gets stand data** from Forest Analyst: age, species mix, volume per acre, current health
2. **Looks up regional stumpage prices** for those species in your region
3. **Calculates standing timber value** using inventory volume × stumpage price/unit
4. **Checks what the buyer offered** against current market rates
5. **Estimates harvest costs** (labor, equipment, road work) using regional benchmarks
6. **Shows the math clearly:**
   - Standing timber value: $X
   - Less harvest costs: -$Y
   - Net revenue to you: $X - Y
   - Buyer's offer: $Z
   - Your analysis: "Fair / Below market / Above market"
7. **Saves a report** to `corporate/financials/harvest_analysis_east_stand_2025.md`

---

## Data Sources & File Structure

**Input files (read from these):**
- `data/processed/financial/transactions_YYYY.csv` — All income and expenses
- Inventory CSVs from `data/processed/inventory/` — For timber valuations
- Regional market data and benchmarks — From this skill's references

**Output files (saved to):**
- `corporate/financials/` — All financial reports, valuations, analyses, and summaries

---

## Important: Disclaimer

**This skill is NOT a substitute for professional financial or tax advice.**

- For tax decisions, consult a certified public accountant (CPA) or tax professional familiar with timber and forest management
- For valuation or appraisals, consult a professional forester or real estate appraiser
- For investment decisions, consider your full financial picture, not just this property

The Financial Tracker provides analysis and organization. You make the decisions.

---

## Resources

### references/
- `forest_financial_reference.md` — Stumpage prices, cost benchmarks, tax rules, formulas, carbon market info
