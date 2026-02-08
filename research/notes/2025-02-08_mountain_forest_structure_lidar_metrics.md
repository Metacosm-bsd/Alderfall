# Characterising Mountain Forest Structure Using Landscape Metrics on LiDAR-Based Canopy Surface Models

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Moderate relevance - while focused on mountain forests and hazard assessment, demonstrates practical use of LiDAR-derived landscape metrics for characterizing forest structure, with some applicability to complex terrain.
**Relevance Rating:** Medium

## Key Findings

This research developed methods to automatically characterize mountain forest structure using landscape metrics (spatial measurements of pattern and arrangement) applied to LiDAR-derived canopy height models. The study focused on protecting against natural hazards (avalanches, rockfall) through forest structure analysis - a protective function less relevant to Alderfall but methodologically important.

The researchers tested whether simple landscape metrics - measures of gap distribution, canopy density variation, and patch sizes - could distinguish between different forest structural types (single-layered, multi-layered, young forests, forests with large gaps). Working in Austrian Alps with Norway spruce and mixed forests, they found that landscape metrics calculated at multiple scales (patch-level and forest-level) effectively characterized structure.

Key technical finding: The Division Index (measuring canopy density variation and gap distribution) was particularly useful for distinguishing single from multi-layered forests (82% classification accuracy). The approach required no field sampling - structure was fully characterized from LiDAR alone.

The study emphasizes that landscape metrics derived from LiDAR canopy models provide objective, reproducible measures of forest structure suitable for operational monitoring. The metrics could be updated regularly as LiDAR data becomes more commonly available.

## What This Means for Alderfall

The methodological approach is directly applicable to Alderfall: use LiDAR-derived canopy models to calculate landscape metrics that objectively describe forest structure. This creates a quantitative basis for monitoring whether management is creating desired structural conditions (e.g., more structurally diverse forests, appropriate gap distribution).

For Alderfall, the most useful metrics would be:
- Canopy density at multiple height classes (structural complexity)
- Gap distribution and size (indicating disturbance history or harvesting pattern)
- Patch fragmentation (indicating forest compartmentalization)

The approach validates using LiDAR data repeatedly over time to monitor structural changes from management. Unlike traditional forest inventory plots (which sample only 1-5% of the forest), LiDAR provides complete coverage and reveals spatial patterns.

## Sources

Maier, B.; Tiede, D.; Dorren, L. (2013). Characterising mountain forest structure using landscape metrics on LiDAR-based canopy surface models. Manuscript published as Chapter 7.2 in forest monitoring handbook.

## Open Questions

1. How sensitive are landscape metrics to LiDAR point cloud density and data quality?
2. What is the minimum time interval between LiDAR acquisitions to reliably detect structural changes from management?
3. Can landscape metrics predict future forest dynamics (e.g., susceptibility to wind damage or insect outbreaks)?
