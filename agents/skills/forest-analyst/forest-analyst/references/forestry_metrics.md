# Forestry Metrics Reference

This reference helps the Forest Analyst calculate, interpret, and explain key metrics. Each metric includes the formula, what it tells you, and what values are considered healthy or concerning.

## Table of Contents
1. Stand Density Metrics
2. Species Composition Metrics
3. Structural Diversity Metrics
4. Growth & Productivity Metrics
5. Health & Risk Metrics
6. Habitat Quality Metrics

---

## 1. Stand Density Metrics

These tell you how crowded the forest is — too dense means trees compete and grow poorly; too sparse means underuse of the land.

### Basal Area (BA)
**What it is:** The total cross-sectional area of all tree trunks at breast height (4.5 ft) per acre. The single most important stand density metric.

**Formula:** BA per tree = π × (DBH/2)² / 144 (gives sq ft when DBH is in inches)
Sum all trees per acre for stand BA.

**Interpretation:**
- 60–80 sq ft/acre: Typical well-stocked hardwood stand
- 80–120 sq ft/acre: Dense — may benefit from thinning
- 120+ sq ft/acre: Overstocked — competition stress likely
- Below 40 sq ft/acre: Understocked — may want to encourage regeneration
- Ideal depends heavily on species and goals

### Trees Per Acre (TPA)
**What it is:** Count of stems per acre. Important to pair with BA — 200 TPA of small trees is very different from 200 TPA of large trees.

**Interpretation (general hardwood):**
- 50–100 TPA: Mature, well-spaced stand
- 100–200 TPA: Moderately dense
- 200–400 TPA: Dense, likely young or needs thinning
- 400+ TPA: Very dense, possibly regeneration or plantation

### Stand Density Index (SDI)
**What it is:** A standardized measure that accounts for both the number and size of trees. Useful for comparing density across stands of different ages.

**Formula:** SDI = TPA × (QMD/10)^1.605
Where QMD = quadratic mean diameter

**Interpretation:**
- Below 35% of maximum SDI: Understocked
- 35–60% of maximum: Fully stocked (growth is maximized)
- 60–80%: Overstocked (self-thinning begins)
- Above 80%: Severely overstocked (mortality expected)

### Quadratic Mean Diameter (QMD)
**What it is:** The diameter of the tree with average basal area. A better "average size" than simple mean DBH because it gives more weight to larger trees.

**Formula:** QMD = √(Σ DBH² / n)

---

## 2. Species Composition Metrics

### Species Richness
**What it is:** Simply the count of distinct tree species present.

**Interpretation:**
- 1–3 species: Low diversity (plantation-like or early succession)
- 4–8 species: Moderate diversity (typical managed stand)
- 8+ species: High diversity (mature, complex forest)

### Shannon Diversity Index (H')
**What it is:** Combines richness and evenness — a forest with 5 species each at 20% is more diverse than one with 5 species where one dominates at 80%.

**Formula:** H' = -Σ (pᵢ × ln(pᵢ))
Where pᵢ = proportion of total basal area for species i

**Interpretation:**
- Below 1.0: Low diversity (one or two species dominate)
- 1.0–2.0: Moderate diversity
- 2.0–3.0: High diversity
- Above 3.0: Very high (uncommon in temperate forests)

### Species Importance Value (IV)
**What it is:** A combined measure of how dominant a species is, factoring in relative density, relative basal area, and relative frequency.

**Formula:** IV = (Relative Density + Relative BA + Relative Frequency) / 3
Each component is the species' percentage of the total.

**Scale:** 0–100%. A species with IV above 30% is a strong dominant.

---

## 3. Structural Diversity Metrics

These describe how complex the forest's physical structure is — key for wildlife habitat and ecological resilience.

### Height Class Distribution
**What it is:** How trees are distributed across height classes. A single-aged stand has trees clustered in one height range; a complex stand has trees spread across many heights.

**Classes (suggested):**
- Seedling: 0–4.5 ft
- Sapling: 4.5–15 ft
- Pole: 15–40 ft
- Sawtimber: 40–70 ft
- Large sawtimber: 70+ ft

**What to look for:** A bell curve in one class = even-aged. Reverse-J shape (many small, few large) = uneven-aged. Gaps in the distribution may indicate past disturbance or missing cohorts.

### Diameter Distribution
**What it is:** How trees are distributed across DBH classes (typically 2-inch classes).

**What to look for:**
- Reverse-J (negative exponential): Classic uneven-aged, sustainable structure
- Normal/bell: Even-aged stand
- Bimodal (two peaks): Two-aged stand
- Flat/irregular: Complex history

### Canopy Layer Index
**What it is:** How many distinct vertical layers the forest has.

**Assessment:**
- Single-layered: One main canopy, little below
- Two-layered: Overstory plus distinct understory or midstory
- Multi-layered: Three or more distinct layers — most structurally complex

---

## 4. Growth & Productivity Metrics

### Site Index (SI)
**What it is:** A measure of how productive the land is for growing trees, based on the height of dominant trees at a reference age (usually 50 years).

**Interpretation (varies by species):**
- SI 50–60: Low productivity site
- SI 60–75: Average
- SI 75–90: Good
- SI 90+: Excellent

### Volume Per Acre
**What it is:** Total wood volume, usually measured in board feet (MBF = thousand board feet) or cords.

**Rough benchmarks (hardwood):**
- 2,000–5,000 BF/acre: Young or understocked
- 5,000–10,000 BF/acre: Moderate, maturing
- 10,000–20,000 BF/acre: Well-stocked mature
- 20,000+ BF/acre: High-value mature stand

### Annual Growth Rate
**What it is:** How much wood volume the stand adds per year, usually as a percentage of standing volume.

**Interpretation:**
- 2–4% per year: Typical for mature hardwood
- 4–6%: Young, vigorously growing stand
- Below 2%: Slow growth — may benefit from thinning or indicate poor site
- Declining growth rate over time is normal as stands mature

---

## 5. Health & Risk Metrics

### Mortality Rate
**What it is:** Percentage of trees that died between measurements.

**Interpretation:**
- Below 1% per year: Normal background mortality
- 1–3%: Elevated — investigate causes
- Above 3%: Concerning — disease, drought, insects, or severe competition

### Crown Ratio
**What it is:** The percentage of total tree height that has live crown (branches with leaves).

**Interpretation:**
- Above 40%: Healthy, vigorous crown
- 30–40%: Acceptable but thinning could help
- Below 30%: Suppressed, declining vigor

### Fire Risk Assessment
**Factors to evaluate:**
- Fuel load (downed wood, leaf litter depth)
- Ladder fuels (vegetation connecting ground to canopy)
- Stand density (denser = more continuous fuel)
- Species composition (some species more fire-prone)
- Topography (south-facing slopes, ridgetops = higher risk)
- Access (can fire crews reach the area?)

### Invasive Species Threat Level
**Assessment framework:**
- None detected: Low risk (monitor annually)
- Present but sparse: Moderate — treat before spread
- Established patches: High — prioritize management
- Widespread: Severe — may need systematic plan

---

## 6. Habitat Quality Metrics

### Snag Density
**What it is:** Standing dead trees per acre. Critical habitat for cavity-nesting birds, bats, and insects.

**Targets:**
- 4–8 snags per acre (various sizes): Good for general wildlife
- Ideally mix of sizes: some 6–12" DBH, some 12"+ DBH
- Below 2 per acre: Habitat gap

### Downed Wood Volume
**What it is:** Volume of logs and woody debris on the forest floor. Important for small mammals, amphibians, fungi, and soil health.

**Targets:**
- 400–800 cubic feet per acre: Good baseline
- Mix of decay classes (fresh to well-rotted)

### Riparian Buffer Width
**What it is:** Width of undisturbed forest along streams and water features.

**Minimums:**
- 50 feet: Bare minimum for water quality
- 100 feet: Good for most ecological functions
- 150+ feet: Excellent wildlife corridor and water protection

---

## Common Conversions

| From | To | Multiply by |
|------|----|-------------|
| DBH (inches) → BA (sq ft) | Single tree BA | π × (DBH/24)² |
| Metric DBH (cm) → inches | | ÷ 2.54 |
| Height (m) → feet | | × 3.281 |
| Hectares → acres | | × 2.471 |
| Cubic meters → board feet | | × 424 (approx) |
| Cubic meters → cords | | ÷ 3.62 |
