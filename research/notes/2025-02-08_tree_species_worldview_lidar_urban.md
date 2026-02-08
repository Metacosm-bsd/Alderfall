# Tree Species Classification Using WorldView-2 Satellite Images and Laser Scanning Data in a Natural Urban Forest

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Low-to-moderate relevance - demonstrates tree species classification in urban forest context, methods partially applicable to mixed forests but less relevant than rural forest studies.
**Relevance Rating:** Low-Medium

## Key Findings

This Croatian study tested whether combining high-resolution satellite imagery (WorldView-2) with LiDAR point cloud data could classify individual tree species in an urban forest with diverse species composition. The research site was an urban forest with 304 coniferous trees (mostly spruce and pine) and 270 deciduous trees (varied species) in varying density conditions.

The approach combined:
1. WorldView-2 satellite spectral data (8 multispectral bands)
2. LiDAR-derived 3D point clouds (providing structural information)
3. Machine learning classifiers (support vector machine)

Results:
- Overall species classification accuracy: 58%
- Accuracy for conifers separately: higher, suggesting conifers are more spectrally distinct
- Adding LiDAR data improved classification compared to spectral data alone
- The study noted that intermingled crowns (trees growing very close together with overlapping canopies) reduced classification accuracy significantly

Key finding: Species classification in dense, mixed urban forests is challenging because tree crowns often overlap and shade each other. The spectral confusion between species with similar appearance (e.g., various oak species, various maple species) limits accuracy.

## What This Means for Alderfall

The 58% overall accuracy reported in this urban forest study is lower than results from more uniform forest stands studied elsewhere. This reflects the challenge of mixed-species, high-density forests where canopy closure is complete.

Practical implications for Alderfall:
1. If Alderfall's forest is a dense, mixed hardwood-softwood stand, expect species classification accuracy to be lower (50-70%) than in more uniform stands
2. Combining satellite imagery with LiDAR helps but doesn't solve the spectral confusion problem
3. Ground-truthing (field sampling) remains necessary - automated classification should be supplemented with field validation
4. Focusing on broad species groups (conifers vs. hardwoods) may be more reliable than trying to classify individual species

The research validates that individual tree species classification remains challenging in realistic forest conditions where crowns overlap and species are spectrally similar. Alderfall should not expect high accuracy for detailed species mapping from remote sensing alone.

## Sources

Verlič, A.; Đurić, N.; Kokalj, Ž.; Marsetič, A.; Simončič, P.; Ošir, K. (2014). Tree Species Classification Using WorldView-2 Satellite Images and Laser Scanning Data in a Natural Urban Forest. Šumarski List, 9-10, 477-488.

Published in Croatian forestry journal

## Open Questions

1. How much field sampling is needed to adequately train classifiers for species identification?
2. Can deep learning approaches outperform traditional machine learning for this application?
3. How does the approach perform in rural forests with less dense canopy closure?
