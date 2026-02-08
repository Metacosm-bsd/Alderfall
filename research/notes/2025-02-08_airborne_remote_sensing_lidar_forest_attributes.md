# Potential and Limits of Airborne Remote Sensing Data for Extraction of Fractional Canopy Cover and Forest Stand and Detection of Tree Species

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** High relevance - comprehensive evaluation of what airborne remote sensing (LiDAR, aerial photography, hyperspectral data) can and cannot reliably extract for forest management planning.
**Relevance Rating:** High

## Key Findings

This Swiss research program evaluated the practical capabilities and limitations of three types of airborne remote sensing data for extracting forest attributes: LiDAR, digital stereo-photogrammetry (3D models from overlapping photos), and hyperspectral imagery. The study tested methods on representative Swiss forests (mixed coniferous-deciduous, mountain and lowland sites).

Key findings on what works well:
- Canopy cover estimation: All three methods achieve good results (80%+ accuracy)
- Tree height estimation: LiDAR and photogrammetry both reliable (within 1-2 m of field measurements)
- Canopy height models (3D representation of forest surface): Both LiDAR and photogrammetry effective
- Detection of main tree species (5 dominant species): Hyperspectral data achieves 70-90% accuracy when combined with structural data

Key limitations identified:
- Understory trees are consistently under-detected or missed by all methods (not visible through dense overstory)
- Individual tree delineation is challenging in dense, mixed forests (algorithms struggle to separate neighboring crowns)
- Distinguishing among similar species spectrally (especially among oaks or among conifer species) remains difficult
- All methods produce better results in simple stand structures than complex multi-layered forests

Practical insight: The methods are complementary. LiDAR excels at structural characterization; hyperspectral imagery excels at species composition IF combined with structure. Neither works perfectly alone. For full operational capability, combine data types.

## What This Means for Alderfall

This research validates that modern airborne remote sensing is genuinely useful for forest inventory but has real limitations Alderfall should understand:

1. **Canopy cover and structure**: Remote sensing methods are reliable. Alderfall should expect 80%+ accuracy for mapping canopy extent and estimating average stand height.

2. **Species composition**: Methods work reasonably well (70-90% accuracy) for the dominant species or species groups, IF you have good species-specific training data. Accuracy degrades for rare species or when species are spectrally similar.

3. **Understory**: Remote sensing cannot reliably characterize what's growing under the canopy. If understory condition matters to Alderfall's management goals, field sampling is necessary.

4. **Complex stands**: In dense, multi-layered forests, remote sensing produces less reliable individual tree information. Landscape-scale metrics (overall structure, diversity) are more reliable than individual-tree data.

5. **Data integration**: The best results come from combining multiple data types. Hyperspectral + LiDAR will outperform either alone. Combined with modest field sampling, very reliable inventory is achievable.

For Alderfall specifically: if obtaining any remote sensing data, use a complementary approach - LiDAR for structure, moderate-resolution multispectral imagery (NAIP) combined with field sampling for species composition. This balances cost and accuracy better than pursuing perfect automated species classification.

## Sources

Waser, L.T.; Eisenbeiss, H.; Küchler, M.; Baltsavias, E. (2008). Potential and Limits of Airborne Remote Sensing Data for Extraction of Fractional Canopy Cover and Forest Stand and Detection of Tree Species. Commission VIII, ThS-21. International Archives of Photogrammetry, Remote Sensing and Spatial Information Sciences, Vol. XXXVII, Part B8, Beijing 2008.

## Open Questions

1. How much field sampling is needed to adequately train remote sensing classifiers for species composition?
2. Can temporal remote sensing data (multiple dates through growing season) improve species and structure identification?
3. How do results change with different illumination conditions (sun angle, cloud cover, seasonal phenology)?
