# Assessment of Classifiers and Remote Sensing Features of Hyperspectral Imagery and Stereo-Photogrammetric Point Clouds for Recognition of Tree Species in a Forest Area of High Species Diversity

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Moderate-to-High relevance - evaluates advanced remote sensing methods (hyperspectral imagery + drone photogrammetry + LiDAR-like 3D data) for individual tree species identification in high-diversity forests.
**Relevance Rating:** Medium-High

## Key Findings

This study tested whether combining multiple remote sensing data types could reliably identify individual tree species in a boreal forest arboretum with very high species diversity (nearly 100 conifer species and 200+ broadleaf species). The researchers combined:

1. Hyperspectral imagery (captures reflectance across hundreds of narrow wavelength bands)
2. RGB photogrammetric point clouds from drones (creates 3D models of tree crowns)
3. Machine learning classifiers (k-nearest neighbor, random forests)

Key results:
- Using hyperspectral data alone: 82.3% accuracy for tree species
- Using hyperspectral + 3D point cloud data: 82.3% accuracy for genus (group of species) classification and 86.9% for broad species categories
- The best-performing data combination was calibrated hyperspectral reflectance (accounting for illumination variation) plus 3D structural features

The hyperspectral approach outperformed the photogrammetric point clouds alone, but combining both types of data produced the most robust results. The study emphasizes that reflectance calibration (correcting for sun angle and shadows) significantly improves classification accuracy.

Important finding: achieving high accuracy (>80%) for individual tree species requires either hyperspectral data or a combination of standard RGB imagery with 3D structure. Standard multispectral data (like NAIP) alone is insufficient for detailed species identification.

## What This Means for Alderfall

Alderfall faces a decision point: if individual tree species identification is critical for management planning, standard multispectral imagery (NAIP, Landsat, Sentinel-2) will not be sufficient. Options are:

1. Invest in hyperspectral data collection (expensive, requires specialized sensors)
2. Combine standard multispectral imagery with LiDAR for 3D structure (more practical)
3. Supplement remote sensing with field sampling for species composition (least expensive but most labor-intensive)

For mixed hardwood/softwood forests with moderate species diversity, the study suggests that combining freely available multispectral imagery (like NAIP) with good-quality LiDAR data might achieve acceptable accuracy (70%+) for species groups, if not individual species.

The research also highlights that data preprocessing and calibration matter significantly - raw reflectance values without correction for illumination produce poor results.

## Sources

Tuominen, S.; Näsi, R.; Honkavaara, E.; Balazs, A.; Hakala, T.; Viljanen, N.; Pölönen, I.; Saari, H.; Ojanen, H. (2018). Assessment of Classifiers and Remote Sensing Features of Hyperspectral Imagery and Stereo-Photogrammetric Point Clouds for Recognition of Tree Species in a Forest Area of High Species Diversity. Remote Sensing, 10(5), 714. https://doi.org/10.3390/rs10050714

Published: 5 May 2018

## Open Questions

1. How does hyperspectral classification performance degrade with seasonal variation in foliage color?
2. What is the practical cost-benefit analysis between investing in hyperspectral data vs. ground sampling for species composition?
3. Can deep learning approaches (neural networks) outperform traditional machine learning classifiers for this application?
