# Retrieval of Forest Canopy Attributes Based on a Geometric-Optical Model Using Airborne LiDAR and Optical Remote-Sensing Data

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Moderate-to-High relevance - demonstrates methods for extracting detailed canopy structure metrics (height, canopy cover, leaf area index) by combining LiDAR with optical satellite data, applicable to operational forest monitoring.
**Relevance Rating:** Medium-High

## Key Findings

This research developed a model to retrieve forest canopy attributes by combining LiDAR data (which directly measures 3D structure) with optical remote sensing data (which measures reflectance). The key insight: LiDAR tells you "what's there" (3D structure), optical data tells you "what it looks like" (spectral properties). Together, they can estimate subtle attributes like leaf area index (LAI - the total area of leaves per unit ground area) and effective plant area index (PAI).

The approach uses a geometric-optical model - a theoretical framework that simulates how light interacts with tree crowns and understory vegetation. By adjusting model parameters to match both LiDAR observations (actual structure) and optical observations (actual reflectance), the model can infer canopy characteristics not directly measured.

Results from Chinese study sites show:
- Canopy cover estimation: R² = 0.80+ (very good correlation with field measurements)
- Leaf area index (LAI) estimation: R² = 0.67-0.75 (good but more variable)
- Effective plant area index: reasonable accuracy with combined data

The critical finding: combining two independent data sources (LiDAR structural data + optical reflectance data) produces more robust estimates than either alone. The optical data helps correct for gaps and layering that might be misinterpreted from LiDAR alone.

## What This Means for Alderfall

If Alderfall plans sophisticated forest monitoring, this research supports investing in combined LiDAR + optical satellite data (freely available Landsat or Sentinel-2) rather than LiDAR alone. The combination allows estimation of physiologically meaningful attributes (like leaf area index) that directly relate to forest productivity and carbon sequestration.

Practical applications for Alderfall:
1. **Carbon monitoring**: LAI is a key input to carbon sequestration models. Combined remote sensing can help estimate carbon sequestration rates.
2. **Productivity assessment**: LAI relates to stand productivity - areas with higher LAI are growing faster.
3. **Disturbance detection**: Changes in LAI between years can detect insect damage, drought stress, or disease before visual symptoms appear.
4. **Baseline inventory**: Rather than detailed ground plots, combined remote sensing provides wall-to-wall estimates of biophysically meaningful variables.

The method is particularly useful for monitoring across large areas where field sampling would be prohibitively expensive. Alderfall could establish a baseline inventory using LiDAR + optical data, then update using optical data alone (cheaper) in subsequent years.

## Sources

Cao, C.; Bao, Y.; Xu, M.; Chen, W.; Zhang, H.; He, Q.; Li, Z.; Guo, H.; Li, J.; Li, X.; Li, G. (2012). Retrieval of Forest Canopy Attributes Based on a Geometric-Optical Model Using Airborne LiDAR and Optical Remote-Sensing Data. International Journal of Remote Sensing, 33(3), 692-709. https://doi.org/10.1080/01431161.2011.577830

Published: 18 November 2011

## Open Questions

1. How does the model perform in forests with complex understory (dense shrub layers)?
2. Can the approach handle seasonal phenology variation (leaf-on vs. leaf-off)?
3. What is the minimum quality requirement for LiDAR data to achieve reliable LAI estimates?
