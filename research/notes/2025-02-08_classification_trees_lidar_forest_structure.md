# Using Classification Trees to Predict Forest Structure Types from LiDAR Data

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** High relevance - practical demonstration of using classification trees (a standard machine learning method) to predict forest structural types from LiDAR metrics, directly applicable to operational forest monitoring.
**Relevance Rating:** High

## Key Findings

This Italian research developed classification tree models to predict forest structural types from LiDAR-derived metrics in a mixed, uneven-aged forest in northern Italy. The approach is methodologically straightforward: use LiDAR to calculate structural metrics (tree height variation, canopy density in different height classes, etc.), then use these metrics to predict which forest structural category a stand belongs to.

The researchers identified five forest structural types based on field observations:
1. Pole-stage forests (70% of canopy, simple structure)
2. Young forests (15%)
3. Adult forests (24%)
4. Mature forests (24%)
5. Old forests (30%)

Using classification tree analysis on 11 LiDAR-derived metrics, they achieved a model that correctly identified forest structural type with 76.5% accuracy in validation data. The model misclassified 45% of some types but achieved near-perfect classification (>80%) for others.

Key finding: A small set of LiDAR metrics (basal area, proportion of mid-story trees, standard deviation and mode of canopy heights) were most important for predicting structural type. Complex multi-metric models didn't substantially outperform simple two-or-three-metric approaches.

The practical value: Forest managers can calculate a handful of LiDAR metrics and use simple decision rules to classify stand structure, without needing sophisticated modeling.

## What This Means for Alderfall

This research demonstrates that LiDAR-based structural classification is practical and accessible:

1. **Operational simplicity**: Classification trees are simpler to implement than many machine learning methods. Results can be explained to non-technical audiences.

2. **Direct management relevance**: The structural types identified (pole-stage, mature, old forest, etc.) directly correspond to silvicultural management categories.

3. **Metric selection matters**: Rather than using all possible LiDAR-derived metrics, focusing on a few key ones (height distribution metrics, basal area, canopy density) produces robust results.

4. **Accuracy sufficient for planning**: 76% accuracy is operationally adequate for stand-level management planning (some misclassification is acceptable).

For Alderfall: if LiDAR data become available, use classification tree methods to automatically categorize stands by structural type. This provides an objective basis for determining which silvicultural treatments are appropriate for different stand types, replacing subjective visual assessment.

The workflow would be:
1. Acquire or access LiDAR data for Alderfall
2. Calculate structural metrics from LiDAR (height distribution, canopy density)
3. Use classification tree rules to predict structural type for each stand
4. Use structural type to guide management prescription selection
5. Monitor changes in structural type over time as proxy for management effectiveness

This approach scales to all of Alderfall without requiring field visits to every stand.

## Sources

Torresan, C.; Corona, P.; Scrinzi, G.; Marsial, J.V. (2016). Using Classification Trees to Predict Forest Structure Types from LiDAR Data. Annals of Forest Research, 59(1), 281-298. https://doi.org/10.15287/afr.2016.423

Published: 2016

## Open Questions

1. How does model accuracy change if classification rules are developed in one forest type and applied to different forest regions?
2. Can temporal changes in LiDAR-predicted structure type accurately track management effects and natural dynamics?
3. How sensitive is the classification to variation in LiDAR data quality and acquisition parameters?
