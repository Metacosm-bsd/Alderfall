# Automatic Forest Area Extraction from Imaging Spectroscopy Data Using an Extended NDVI

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Moderate relevance - describes automated methods for distinguishing forested from non-forested areas using spectral imagery, useful for updating land-cover maps and validating forest extent.
**Relevance Rating:** Medium

## Key Findings

This study presents a method to automatically extract forest areas from hyperspectral imagery data using a modified Normalized Difference Vegetation Index (NDVI). The technique was tested on multiple datasets including HyMap (hyperspectral airborne imagery) and simulated satellite data.

Key technical insight: Standard NDVI (which uses only red and near-infrared bands) performs adequately, but adding information from additional spectral bands (particularly the short-wave infrared region around 2400nm) improves forest/non-forest classification. The researchers found that combining multiple spectral indices rather than relying on a single index produced more reliable forest boundaries.

The method was applied to 19 different hyperspectral scenes across Germany with varying terrain and vegetation types. Overall classification accuracy for forest vs. non-forest ranged from 92% to 96.6%, with only 3-8% of classified samples being misclassified.

Importantly, the approach can handle various environmental conditions: shadows, steep terrain, and mixed landscapes where forest patches are small. The method requires calibration to account for atmospheric effects but is otherwise relatively straightforward to implement.

## What This Means for Alderfall

If Alderfall needs to update boundaries of forested vs. non-forested areas, automated spectral classification methods are reliable and practical. This is particularly useful if Alderfall's boundaries have changed due to harvesting, land sales, or acquisitions.

The research validates that freely available imagery (or inexpensive hyperspectral data) can be used to monitor forest extent over time. However, for operational forestry where detailed species composition matters more than simply "is this area forested?", this method is less useful.

The practical value for Alderfall: use automated forest/non-forest classification to update GIS boundaries and monitor conversions of forest to non-forest land uses, but supplement with more detailed methods (LiDAR, field sampling) for species composition and stand structure.

## Sources

Fässnacht, F.; Weinacker, H.; Koch, B. (2011). Automatic Forest Area Extraction from Imaging Spectroscopy Data Using an Extended NDVI. 7th EARSeL Workshop on Imaging Spectroscopy, Edinburgh, Scotland, 11-13 April 2011.

Published in Workshop Proceedings

## Open Questions

1. How well does this method work for detecting partial forest conversion (e.g., partial harvesting where tree cover remains >50%)?
2. Can the method reliably distinguish between young natural regeneration and maintained herbaceous areas?
3. How does the approach perform in transitional forest/woodland areas where the boundary is ecologically gradual?
