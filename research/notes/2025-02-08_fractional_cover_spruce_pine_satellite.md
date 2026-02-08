# Fractional Cover Mapping of Spruce and Pine at 1 ha Resolution Combining Very High and Medium Spatial Resolution Satellite Imagery

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Data Science & Technology
**Relevance to Alderfall:** Moderate relevance - demonstrates methods for mapping fractional tree species coverage (what percentage of a stand is spruce vs. pine) using satellite imagery at operational scales, applicable to any conifer-dominated forest.
**Relevance Rating:** Medium

## Key Findings

This research addressed a practical problem: How to create high-resolution maps of where specific tree species dominate across large regions, using freely or inexpensively available satellite data? The study combined two satellite data sources: very high-resolution WorldView-2 imagery (2m pixels) and moderate-resolution Landsat data (30m pixels), using a two-step approach.

Step 1: Used WorldView-2 over a small training area to develop a machine learning model that maps spruce and pine coverage at fine resolution (based on spectral signatures).

Step 2: Applied the trained model to Landsat data covering a much larger region (entire state of Bavaria, Germany) to upscale the mapping.

Results were promising: The researchers achieved 84% accuracy for mapping spruce vs. pine at 1-hectare resolution (operationally useful for forest management) across 26,000 km² of the German state. The method successfully handled the reality that many stands contain mixtures of species - outputting percentages rather than simple classification (e.g., "60% spruce, 40% pine" rather than "spruce stand").

The fractional cover approach (outputting percentages of each species) proved more accurate and operationally useful than simple classification ("this cell is spruce or pine"). The study also demonstrated that using temporal information (multiple satellite images through growing season) improved accuracy slightly.

## What This Means for Alderfall

If Alderfall operates a mixed conifer-deciduous forest or has areas dominated by specific conifer species, this approach offers a practical path to mapping species composition at operational scales without expensive custom data collection. The method:

1. Uses freely available or low-cost satellite data (WorldView-2 requires licensing but is not prohibitively expensive; Landsat is free)
2. Produces output at meaningful scale for management (1-hectare resolution)
3. Provides fractional cover estimates, not just categories, which better reflects forest reality
4. Is replicable and updatable

For Alderfall specifically: if the forest contains significant pure or mixed spruce/pine stands, this approach could create annual or biennial species composition maps. The investment would be in data licensing and model development (one-time), then low-cost updates using free Landsat data.

The practical limitation: the method works best for spectrally distinct species or species groups. Mixed hardwood stands are more challenging (oaks, maples, birches are spectrally similar). Conifers are ideal for this approach due to their distinctive spectral signatures.

## Sources

Immitzer, M.; Böck, S.; Einzmann, K.; Vuolo, F.; Pinnel, N.; Wallner, A.; Atzberger, C. (2017). Fractional cover mapping of spruce and pine at 1 ha resolution combining very high and medium spatial resolution satellite imagery. Remote Sensing of Environment, 204, 690-703. https://doi.org/10.1016/j.rse.2017.09.031

Published: 12 September 2017

## Open Questions

1. How does the method perform in forests with significant vertical structure variation (e.g., where understory species differ from overstory)?
2. Can the approach distinguish between species with more similar spectral signatures (e.g., different oak species)?
3. How does cloud cover and seasonal variation affect mapping accuracy over time?
