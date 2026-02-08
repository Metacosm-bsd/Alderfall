# A Comparison of Methods for Determining Forest Composition from High-Spatial-Resolution Remotely Sensed Imagery

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** High relevance - directly addresses LiDAR and UAS-based methods for tree species identification and forest composition mapping at stand level, with practical comparison of tools (Google Earth, NAIP imagery, UAS).
**Relevance Rating:** High

## Key Findings

This peer-reviewed study compared three approaches to identifying forest species composition from high-resolution aerial imagery in New England mixed forests. The researchers tested three imagery sources: Google Earth (free but low resolution), NAIP imagery (National Agriculture Imagery Program - moderate resolution), and UAS (unmanned aerial system) data at extremely high resolution (3cm pixel size).

The critical finding: while visual interpretation (a human looking at images) achieved only 54% accuracy for identifying forest composition classes, automated digital classification using machine learning algorithms (random forests, support vector machines, classification trees) achieved 70% accuracy on the same plots. This represents a 16% improvement over human interpretation alone.

The study used New Hampshire forests with complex mixed species composition (oak, pine, hemlock, maple, beech) - similar ecological conditions to Alderfall's mixed hardwood/softwood stands. UAS imagery provided the most detailed information but required the most processing. NAIP data proved a good middle ground - freely available, sufficient resolution for automated classification, and requiring less collection effort than UAS.

Machine learning significantly outperformed visual methods for individual tree detection (93.9% accuracy) and tree species labeling (59-70% accuracy), even though overall forest composition classification remained moderate. The research emphasizes that automated approaches reduce observer bias and are more replicable across large areas than visual interpretation.

## What This Means for Alderfall

Alderfall should prioritize automated classification methods over visual interpretation for any forest inventory work. If pursuing LiDAR-based analysis, combine it with publicly available NAIP imagery rather than investing in custom high-resolution UAS flights initially. The moderate accuracy (59-70% for individual tree species) suggests that while automated methods work well for broad composition assessment (which species dominate), identifying individual tree species remains challenging. This is important for operational planning - the methods are reliable for determining if a stand is oak-dominated vs. pine-dominated, but less reliable for identifying every individual tree species in a mixed stand.

The study also validates that machine learning approaches require investment in training data (ground truth samples) but provide repeatable, objective results. For Alderfall, starting with existing Forest Inventory Analysis (FIA) plot data could provide the training samples needed for classification.

## Sources

Fraser, B.T.; Congalton, R.G. (2021). A Comparison of Methods for Determining Forest Composition from High-Spatial Resolution Remotely Sensed Imagery. Forests, 12(9), 1290. https://doi.org/10.3390/f12091290

Academic Editor: Giorgos Mallinis; Published: 21 September 2021

## Open Questions

1. How do these methods perform in forests with greater vertical complexity (multiple canopy layers)?
2. What is the minimum training data requirement for achieving reliable automated classification?
3. How do results vary seasonally - does leaf-off condition improve or degrade species classification?
4. Can these methods distinguish between species with similar spectral signatures in local conditions?
