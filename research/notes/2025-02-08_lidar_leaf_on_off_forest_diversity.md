# The Effect of Leaf-On and Leaf-Off Forest Canopy Conditions on LiDAR-Derived Estimations of Forest Structural Diversity

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** High relevance - directly addresses a practical operational question: does the timing of LiDAR acquisition affect the reliability of structural diversity measurements? Critical for interpreting monitoring datasets.
**Relevance Rating:** High

## Key Findings

This British study examined whether LiDAR-derived estimates of forest structural diversity (a key indicator of forest health and biodiversity) change depending on whether data are collected in leaf-on (summer) or leaf-off (winter) conditions. The researchers collected LiDAR data over the same forest stands in both seasons and measured how this affected estimates of tree height diversity, crown characteristics, and stand complexity.

Key findings:
- Leaf-off LiDAR penetrates deeper into the canopy and detects understory vegetation more effectively
- Tree height estimates are similar leaf-on vs. leaf-off (within measurement error)
- Estimates of canopy cover differ seasonally (lower estimates in leaf-off condition, which is physically accurate)
- Structural diversity metrics (variation in tree heights, crown width diversity) are reasonably consistent between seasons when properly interpreted
- Crown length diversity and crown width diversity estimates are more reliable from leaf-off data (better visibility)

The critical finding: Leaf-off LiDAR provides more conservative estimates of canopy cover (accounts for deciduous trees being without foliage) and better detection of understory. Leaf-on LiDAR provides better estimates of canopy biomass (total leaf area). Both seasons have advantages; the key is understanding the difference.

For monitoring over time, the researchers recommend consistent timing - always collect in the same season to avoid interpretation confusion. Leaf-off (winter) is preferable for structural diversity monitoring because understory is more visible.

## What This Means for Alderfall

If Alderfall acquires LiDAR data, understand and document the acquisition timing:

1. **For structural diversity monitoring** (which varies with forest structure, not just canopy fullness): Use leaf-off condition. This provides clearer detection of understory and more reliable structural metrics.

2. **For canopy cover monitoring**: Document timing - leaf-on and leaf-off will give different but both valid results. The difference between years reflects both seasonal variation AND structural change.

3. **For consistent monitoring over time**: Choose a season and stick with it for multi-year comparisons. Switching from leaf-on to leaf-off acquisition will make year-to-year comparisons difficult.

4. **For mixed deciduous-conifer stands** (like Alderfall's likely forest type): Leaf-off data will show conifer structure more clearly (since deciduous trees are bare) while leaf-on shows full canopy complexity. Both are useful for different questions.

Practical implication: If Alderfall funds LiDAR acquisition, schedule it for winter/leaf-off season to optimize detection of understory and structural diversity. If historical LiDAR data were acquired in leaf-on condition, understand that seasonal comparison with leaf-off data requires careful interpretation.

## Sources

Davison, S.; Donoghue, D.N.M.; Galiatsatos, N. (2020). The Effect of Leaf-On and Leaf-Off Forest Canopy Conditions on LiDAR-Derived Estimations of Forest Structural Diversity. International Journal of Applied Earth Observation and Geoinformation, 92, 102160. https://doi.org/10.1016/j.jag.2020.102160

Published: 14 May 2020

## Open Questions

1. How does this seasonal variation affect LiDAR estimates of stand-level carbon stocks?
2. Can the differences between leaf-on and leaf-off be used to estimate leaf area index?
3. How do tropical or evergreen forests (where there's less seasonal variation) differ in this pattern?
