# Alderfall Data Schemas Reference

This file defines the standard data formats the Data Collector produces. All processed data should conform to these schemas so that other agents (Forest Analyst, Financial Tracker, etc.) can consume it reliably.

## Table of Contents
1. Tree Inventory Schema
2. Plot Measurement Schema
3. Species List Schema
4. Financial Transaction Schema
5. LiDAR Summary Schema
6. Soil Sample Schema
7. Wildlife Observation Schema
8. Weather/Climate Schema

---

## 1. Tree Inventory Schema

Individual tree records from field measurements or LiDAR-derived data.

**Filename pattern:** `tree_inventory_YYYY-MM-DD.csv`
**Location:** `data/processed/inventory/`

| Column | Type | Unit | Description |
|--------|------|------|-------------|
| tree_id | string | — | Unique identifier (e.g., "P01-T001" for Plot 01, Tree 001) |
| plot_id | string | — | Plot identifier where tree is located |
| species | string | — | Common name (e.g., "Red Oak") |
| species_code | string | — | USDA PLANTS code (e.g., "QURU" for Quercus rubra) |
| dbh_inches | float | inches | Diameter at breast height (4.5 ft above ground) |
| height_feet | float | feet | Total tree height |
| crown_class | string | — | Dominant / Codominant / Intermediate / Suppressed |
| health_status | string | — | Healthy / Stressed / Declining / Dead / Removed |
| notes | string | — | Free text observations |
| date_measured | date | YYYY-MM-DD | Date of measurement |
| latitude | float | degrees | GPS latitude (if available) |
| longitude | float | degrees | GPS longitude (if available) |

---

## 2. Plot Measurement Schema

Stand-level data summarized at the plot level.

**Filename pattern:** `plot_summary_YYYY-MM-DD.csv`
**Location:** `data/processed/inventory/`

| Column | Type | Unit | Description |
|--------|------|------|-------------|
| plot_id | string | — | Unique plot identifier |
| plot_type | string | — | Fixed / Variable / Transect |
| plot_radius_ft | float | feet | Plot radius (for fixed-radius plots) |
| baf | float | — | Basal area factor (for variable-radius/prism plots) |
| date_measured | date | YYYY-MM-DD | Date of measurement |
| trees_per_acre | float | trees/acre | Estimated stems per acre |
| basal_area_sqft | float | sq ft/acre | Basal area per acre |
| avg_dbh_inches | float | inches | Mean DBH of measured trees |
| dominant_species | string | — | Most common species by count |
| species_count | integer | — | Number of distinct species |
| canopy_cover_pct | float | percent | Estimated canopy closure |
| stand_age_est | integer | years | Estimated stand age |
| site_index | float | — | Site productivity index (if known) |
| latitude | float | degrees | Plot center GPS latitude |
| longitude | float | degrees | Plot center GPS longitude |
| notes | string | — | Free text observations |

---

## 3. Species List Schema

Master list of species observed on the property.

**Filename pattern:** `species_list.csv`
**Location:** `data/processed/inventory/`

| Column | Type | Description |
|--------|------|-------------|
| species_code | string | USDA PLANTS code |
| common_name | string | Common name |
| scientific_name | string | Latin binomial |
| type | string | Tree / Shrub / Herb / Grass / Fern / Moss / Fungi |
| native | boolean | Native to region (true/false) |
| invasive | boolean | Considered invasive (true/false) |
| first_observed | date | First date recorded on property |
| abundance | string | Abundant / Common / Occasional / Rare |
| notes | string | Habitat preferences, management notes |

---

## 4. Financial Transaction Schema

All income and expenses related to forest management.

**Filename pattern:** `transactions_YYYY.csv`
**Location:** `data/processed/financial/`

| Column | Type | Unit | Description |
|--------|------|------|-------------|
| transaction_id | string | — | Unique identifier |
| date | date | YYYY-MM-DD | Transaction date |
| category | string | — | See category list below |
| subcategory | string | — | More specific classification |
| description | string | — | What was this for |
| amount | float | USD | Positive = income, Negative = expense |
| vendor_or_payer | string | — | Who paid or was paid |
| tax_deductible | boolean | — | Eligible for tax deduction |
| tax_category | string | — | Section 1231 / Reforestation / Operating / Capital |
| receipt_file | string | — | Path to receipt/invoice if saved |
| notes | string | — | Additional context |

**Standard categories:**
- Timber Sales
- Carbon Credits
- Grants / Cost Share
- Recreation / Leases
- Equipment
- Labor / Contractors
- Road Maintenance
- Planting / Regeneration
- Pest / Disease Treatment
- Property Tax
- Insurance
- Professional Services (forester, accountant, lawyer)
- Monitoring / Surveys
- Other

---

## 5. LiDAR Summary Schema

Summary metrics derived from LiDAR acquisitions.

**Filename pattern:** `lidar_summary_YYYY-MM-DD.csv`
**Location:** `data/processed/remote_sensing/`

| Column | Type | Unit | Description |
|--------|------|------|-------------|
| area_id | string | — | Stand or management unit identifier |
| acquisition_date | date | YYYY-MM-DD | Date LiDAR was collected |
| season | string | — | Leaf-on / Leaf-off |
| point_density | float | pts/m² | Average point density |
| max_height_m | float | meters | Maximum canopy height |
| mean_height_m | float | meters | Mean canopy height |
| canopy_cover_pct | float | percent | Canopy cover percentage |
| height_stdev_m | float | meters | Standard deviation of heights (structural diversity) |
| understory_density | float | — | Relative density of returns below 2m |
| data_source | string | — | Provider or acquisition method |
| raw_file_path | string | — | Path to raw data file in data/raw/ |
| notes | string | — | Processing notes, quality issues |

---

## 6. Soil Sample Schema

Soil test results from field sampling.

**Filename pattern:** `soil_samples_YYYY-MM-DD.csv`
**Location:** `data/processed/ecology/`

| Column | Type | Unit | Description |
|--------|------|------|-------------|
| sample_id | string | — | Unique sample identifier |
| plot_id | string | — | Associated plot (if applicable) |
| date_collected | date | YYYY-MM-DD | Collection date |
| depth_inches | string | — | Sample depth (e.g., "0-6", "6-12") |
| ph | float | — | Soil pH |
| organic_matter_pct | float | percent | Organic matter content |
| nitrogen_ppm | float | ppm | Available nitrogen |
| phosphorus_ppm | float | ppm | Available phosphorus |
| potassium_ppm | float | ppm | Available potassium |
| texture | string | — | Sand / Loam / Clay / etc. |
| moisture_pct | float | percent | Moisture at time of sampling |
| latitude | float | degrees | Sample location |
| longitude | float | degrees | Sample location |
| lab | string | — | Testing laboratory |
| notes | string | — | Field observations |

---

## 7. Wildlife Observation Schema

Wildlife sightings, trail camera records, and habitat assessments.

**Filename pattern:** `wildlife_observations_YYYY.csv`
**Location:** `data/processed/ecology/`

| Column | Type | Description |
|--------|------|-------------|
| observation_id | string | Unique identifier |
| date | date | Observation date (YYYY-MM-DD) |
| time | time | Time of observation (HH:MM, if known) |
| species | string | Common name |
| count | integer | Number observed |
| method | string | Visual / Trail Camera / Audio / Tracks / Scat |
| location | string | Description or plot_id |
| latitude | float | GPS latitude (if available) |
| longitude | float | GPS longitude (if available) |
| behavior | string | Brief behavioral note |
| photo_file | string | Path to photo if available |
| notes | string | Additional observations |

---

## 8. Weather / Climate Schema

Weather station or downloaded climate data.

**Filename pattern:** `weather_YYYY.csv`
**Location:** `data/processed/climate/`

| Column | Type | Unit | Description |
|--------|------|------|-------------|
| date | date | YYYY-MM-DD | Date |
| temp_high_f | float | °F | Daily high temperature |
| temp_low_f | float | °F | Daily low temperature |
| precip_inches | float | inches | Precipitation |
| snow_inches | float | inches | Snowfall |
| wind_max_mph | float | mph | Maximum wind speed |
| humidity_pct | float | percent | Average relative humidity |
| source | string | — | NOAA / on-site station / other |

---

## Notes on Data Standards

**Dates:** Always YYYY-MM-DD format.

**GPS coordinates:** Decimal degrees (e.g., 42.3601, -71.0589). Use WGS 84 datum.

**Units:** Imperial for field measurements (inches, feet, acres) since that's standard in US forestry. Metric for LiDAR/remote sensing (meters) since that's the standard in that field. Always label the unit in the column name.

**Missing values:** Leave blank (not "N/A", "null", or "0"). This makes it clear the data wasn't collected vs. the value being zero.

**File format:** CSV with UTF-8 encoding. First row is always headers matching the schema column names exactly.
