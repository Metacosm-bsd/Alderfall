# Tree Species Composition Mapping with Dimension Reduction and Post-Classification Using Very High-Resolution Hyperspectral Imaging

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Moderate relevance - advanced method for tree species mapping in high-diversity forests using hyperspectral data, demonstrates practical data science techniques for handling complex spectral information.
**Relevance Rating:** Medium

## Key Findings

This Hungarian-led research tackled a data science challenge: hyperspectral imagery provides hundreds of spectral bands, which creates computational complexity and can lead to overfitting (models that work in training data but fail on new data). The researchers tested whether "dimension reduction" techniques - mathematical methods to compress information from hundreds of bands into a smaller set of derived variables - could improve tree species classification in a high-diversity floodplain forest.

The study compared three dimension reduction approaches:
1. Principal Component Analysis (PCA) - mathematical approach to finding patterns
2. Independent Component Analysis (ICA) - similar but using different mathematical properties
3. Minimum Noise Fraction (MNF) - specifically designed for hyperspectral data

Results showed:
- Minimum Noise Fraction provided the best overall accuracy (>80% for multiple models)
- The best-performing model (using MNF with random forest classifier) achieved 83.3% accuracy for species classification
- With careful post-classification filtering, accuracy improved to 86.1%
- Models using fewer derived components (around 10-13) performed as well as those using all available components, proving that dimension reduction was effective

Key insight: Simply throwing all hyperspectral bands at a machine learning algorithm doesn't produce the best results. Thoughtful data reduction using methods like MNF produces more robust, generalizable models.

## What This Means for Alderfall

If Alderfall were to invest in hyperspectral data for tree species mapping, this research demonstrates that achieving 80%+ accuracy is possible using current methods. However, several practical realities apply:

1. **Hyperspectral data is expensive**: Custom hyperspectral surveys typically cost $5,000-20,000+ per project area, beyond reach for most private forest owners.

2. **Data science expertise required**: Implementing dimension reduction and machine learning requires either hiring specialists or contracting with remote sensing consultants. This is not plug-and-play technology.

3. **Ground truthing is essential**: The 83-86% accuracy achieved required extensive field sampling to train the model. Plan for 20-30% of project budget going to field work.

4. **Results are good but not perfect**: Even with advanced methods, expect 10-15% misclassification. This is operationally acceptable for broad forest management planning but not sufficient for individual tree targeting.

For Alderfall's practical situation: Hyperspectral methods represent the frontier of remote sensing capability for tree species mapping but are probably overkill for typical operational needs. Combining LiDAR (for structure) with inexpensive multispectral imagery (NAIP, Sentinel-2, Landsat) plus modest field sampling will likely achieve 90%+ reliability for broad management purposes at a fraction of hyperspectral costs.

## Sources

Balázs, S.; Bekő, L.; Honkavaara, E.; Burai, P.; Holb, I.J.; Szabó, S. (2022). Tree Species Composition Mapping with Dimension Reduction and Post-Classification Using Very High-Resolution Hyperspectral Imaging. Scientific Reports, 12, 20919. https://doi.org/10.1038/s41598-022-25604-x

Published: 12 December 2022

## Open Questions

1. How much does hyperspectral classification improve over multispectral (4-band) imagery in practical forest settings?
2. Can dimension reduction methods improve the generalizability of models to other forest regions?
3. How do seasonal phenology changes affect hyperspectral classification accuracy?
