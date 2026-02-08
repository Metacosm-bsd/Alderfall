# A Comparison of Two Tree Detection Methods for Estimation of Forest Stand and Ecological Variables from Airborne LiDAR Data in Central European Forests

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** High relevance - compares two operational LiDAR processing methods (multisource-based vs. raster-based) for extracting forest metrics directly from LiDAR point clouds.
**Relevance Rating:** High

## Key Findings

This study tested two different computer methods for processing airborne LiDAR data to extract forest stand metrics in Central European mixed forests. Method 1 (multisource-based, implemented in reFLex software) works directly with the 3D point cloud of LiDAR data. Method 2 (raster-based, implemented in OPALS software) converts the point cloud into grid-based models.

Both methods successfully estimated key forest variables with similar accuracy:
- Mean height: 7.2-8.6% error
- Mean diameter: 8.6-21.4% error
- Stand density: variation within acceptable range
- Shannon diversity index: 7.2% error

The multisource-based method was faster and required less user interpretation of intermediate steps, while the raster-based method provided more detailed estimates of individual variables but involved more processing steps. Both methods identified individual trees (tree detection) with reasonable success but missed understory trees and suppressed vegetation more consistently than the multisource approach.

The research demonstrates that modern LiDAR processing can reliably extract the core stand metrics (height, diameter, density) needed for forest management, with accuracy within operational tolerances. The choice between methods depends on project needs - if speed and simplicity matter, use multisource methods; if detailed individual-variable estimates matter, use raster-based approaches.

## What This Means for Alderfall

If Alderfall obtains airborne LiDAR data, understand that multiple processing pathways exist, each with different accuracy characteristics. The good news: both major approaches (multisource and raster-based) achieve similar overall accuracy for stand-level metrics. This means choice of processing software is less critical than having good-quality LiDAR data to begin with.

The results suggest that LiDAR-derived estimates will be reliable for monitoring stand average height and density over time, and reasonably reliable for diameter estimates. The moderate accuracy for Shannon diversity index suggests that using LiDAR alone to assess species diversity is possible but not as precise as ground sampling.

For Alderfall's specific interest in forest metrics, the critical finding is that both methods perform similarly for the metrics that matter most to management (height, density, basic composition). Plan for LiDAR processing to require professional interpretation; the software tools are not fully automated.

## Sources

Sackov, I.; Kulla, L.; Bucha, T. (2019). A Comparison of Two Tree Detection Methods for Estimation of Forest Stand and Ecological Variables from Airborne LiDAR Data in Central European Forests. Remote Sensing, 11(11), 1431. https://doi.org/10.3390/rs11121431

Published: 16 June 2019

## Open Questions

1. How do these methods perform in very dense, multi-layered stands vs. simple two-story forests?
2. What is the impact of LiDAR point cloud density on the accuracy of these methods?
3. Can temporal LiDAR data (multiple years) improve estimates of individual tree growth rates?
