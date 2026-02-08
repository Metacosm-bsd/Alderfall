# A Simple Approach to Forest Structure Classification Using Airborne Laser Scanning That Can Be Adopted Across Bioregions

**Date researched:** 2025-02-08
**Domains:** Forest Inventory & Monitoring, Ecology & Silviculture
**Relevance to Alderfall:** High relevance - demonstrates a practical, region-independent method for classifying forest structural types using LiDAR, applicable across different forest types and biogeographic regions.
**Relevance Rating:** High

## Key Findings

This international research team (working across Boreal, Mediterranean, and Atlantic regions) developed a simplified method to classify forests into structural types using LiDAR-derived canopy models. Rather than using complex statistical methods, they focused on two straightforward metrics: Gini coefficient (a measure of tree size inequality) and basal area larger than mean (BALM - a measure of dominance of large trees).

The method successfully classified forests into meaningful categories: single-story stands, multi-layered stands, young stands, and mature stands. Importantly, the approach worked reliably across three very different European bioregions with different forest types (Boreal spruce forests, Mediterranean broadleaf forests, Atlantic oak-pine forests).

Accuracy was high (87% in deciduous forest, 72% in coniferous forest) for identifying structural type from LiDAR canopy models. The researchers found that canopy roughness (variation in tree height within a stand) was the most important predictor of structural type, followed by the distribution of tree sizes.

The significant finding for Alderfall: A relatively simple, data-driven classification approach can work across different forest types. The method requires only LiDAR data (not hyperspectral imagery or multiple data sources) and can be implemented in standard GIS software. The structural classifications (single-story vs. multi-layered, young vs. mature) directly relate to silvicultural management decisions.

## What This Means for Alderfall

Alderfall should consider LiDAR-based structural classification as a practical way to objectively categorize forest stands and monitor whether management activities are moving stands toward or away from desired structural conditions. The method is simple enough to update regularly (e.g., every 5-10 years with new LiDAR) and provides results that directly inform silvicultural decisions.

The approach validates using landscape-scale metrics derived from LiDAR canopy models as a tool for operational forestry. Unlike visual assessment or traditional plots, LiDAR-based methods provide objective, reproducible classifications across the entire forest, not just sampled locations.

For a mixed hardwood/softwood forest like Alderfall, the ability to automatically identify single vs. multi-layered stands is particularly valuable - this structural distinction drives different management prescriptions and is difficult to assess accurately without intensive field sampling.

## Sources

Adnan, S.; Maltamo, M.; Coomes, D.A.; García-Abril, A.; Mahi, Y.; Manzanera, J.A.; Butt, N.; Moreno, E.; Valbuena, R. (2019). A simple approach to forest structure classification using airborne laser scanning that can be adopted across bioregions. Forest Ecology and Management, 433, 111-121. https://doi.org/10.1016/j.foreco.2018.10.057

Published: 03 November 2018

## Open Questions

1. How does the method perform in very young forests (saplings and poles) where LiDAR penetration challenges arise?
2. Can the approach reliably distinguish between forests managed differently (e.g., selective harvest vs. clearcut regeneration)?
3. What is the minimum time interval between LiDAR surveys to reliably detect structural changes from management?
