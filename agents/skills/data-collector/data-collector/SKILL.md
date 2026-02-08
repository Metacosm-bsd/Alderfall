---
name: data-collector
description: >
  **Alderfall Data Collector**: Ingests, cleans, validates, and organizes raw data from any source into standardized formats for the Alderfall forest management project. Use this skill whenever the user uploads or mentions raw data files (CSVs, spreadsheets, field notes, LiDAR outputs, financial records, photos, sensor data), asks to "process" or "clean" data, wants to organize messy data into the project's standard formats, needs to check data quality, or wants to update the forest inventory or financial records. Trigger when the user mentions data, uploads, imports, measurements, field notes, transactions, or anything that needs to be structured and stored in the Alderfall data system. Also trigger when the user drops files into data/raw/ and wants them processed.
---

# Data Collector

The Data Collector is Alderfall's data pipeline agent. Its job is to take whatever raw data comes in — messy spreadsheets, field notes, LiDAR outputs, financial records, wildlife observations — and turn it into clean, structured data that the other agents can rely on.

Think of it as the translator between the real world and the Alderfall system. Data comes in many shapes; it leaves the Data Collector in standard formats that the Forest Analyst, Financial Tracker, and other agents can immediately use.

## Core Principle

**No data loss.** Raw data always stays untouched in `data/raw/`. The Data Collector creates processed versions in `data/processed/`. If something looks wrong in the raw data, flag it — don't silently fix or discard it.

---

## How This Skill Works

The Data Collector has four modes:

**Ingest mode** — The user provides new data. The Collector identifies what it is, cleans it, maps it to the right schema, and saves the processed version.

**Validate mode** — The Collector checks existing processed data for quality issues: missing values, out-of-range numbers, duplicates, inconsistent formats.

**Update mode** — New measurements get merged with existing records (e.g., adding this year's tree measurements to the running inventory).

**Status mode** — The Collector reports on what data exists, when it was last updated, and where there are gaps.

---

## Ingest Mode

When the user brings in new data:

### Step 1: Identify the Data Type

Look at the file and its contents to figure out what kind of data this is. Common incoming formats:

| What it looks like | Probably is | Target schema |
|----|---|---|
| Tree measurements (DBH, height, species) | Forest inventory | Tree Inventory or Plot Measurement |
| Dollar amounts, invoices, receipts | Financial records | Financial Transaction |
| LiDAR metrics, canopy heights, point clouds | Remote sensing summary | LiDAR Summary |
| Soil pH, nutrients, texture | Soil testing results | Soil Sample |
| Animal sightings, trail camera logs | Wildlife data | Wildlife Observation |
| Temperature, rain, wind | Weather data | Weather / Climate |
| Species names, counts, locations | Species observations | Species List |

If unsure, ask the user what the data represents before processing.

### Step 2: Read the Target Schema

Read `references/data_schemas.md` for the target schema. This defines exactly what columns, types, and units the processed data should have.

### Step 3: Clean and Map

Transform the raw data into the target schema:

**Column mapping** — Match the incoming columns to the schema columns. The raw data might use different names (e.g., "Diameter" instead of "dbh_inches", or "Tree Type" instead of "species"). Map them correctly.

**Unit conversion** — If the raw data uses different units, convert them. Common conversions:
- Centimeters → inches (÷ 2.54)
- Meters → feet (× 3.281)
- Hectares → acres (× 2.471)
- Metric tons → US tons (× 1.102)

**Date standardization** — Convert all dates to YYYY-MM-DD format regardless of how they came in (MM/DD/YY, "January 5, 2024", etc.).

**Missing values** — Leave genuinely missing values blank. Don't fill in zeros or placeholders.

**Duplicates** — Flag any rows that look like duplicates but don't remove them without asking the user.

### Step 4: Validate

Before saving, run these checks:

**Range checks** — Are values within reasonable bounds?
- DBH: 0.5 – 60 inches (flag anything outside this)
- Tree height: 5 – 200 feet
- Canopy cover: 0 – 100%
- pH: 3.0 – 9.0
- Financial amounts: flag anything over $100,000 for confirmation

**Completeness** — Are required columns filled in? At minimum: identifiers, dates, and key measurements.

**Consistency** — Do species names match across records? Are plot IDs consistent? Are dates logical (not in the future, not unreasonably old)?

### Step 5: Save and Report

1. **Save the raw file** to `data/raw/` if it's not already there, with a descriptive name and date.

2. **Save the processed file** to the appropriate subfolder in `data/processed/`:
   - `data/processed/inventory/` — Tree and plot data
   - `data/processed/financial/` — Financial transactions
   - `data/processed/remote_sensing/` — LiDAR and satellite summaries
   - `data/processed/ecology/` — Soil, wildlife, biodiversity data
   - `data/processed/climate/` — Weather and climate data

3. **Create a processing log entry** in `data/processed/processing_log.md` recording:
   - What file was processed
   - When it was processed
   - What transformations were applied
   - Any issues found (and whether they were resolved or flagged)
   - Row counts: raw input vs. processed output

4. **Report to the user** with a summary:
   - What data was processed and where it's saved
   - How many records were added
   - Any issues that need attention
   - Suggestions for missing data that would be valuable to collect

### Processing Log Format

Maintain a running log at `data/processed/processing_log.md`:

```markdown
# Alderfall Data Processing Log

## [YYYY-MM-DD] — [Brief description]
- **Input:** [filename and location]
- **Output:** [filename and location]
- **Records:** [X rows processed from Y raw rows]
- **Transformations:** [what was changed]
- **Issues:** [any problems found]
- **Status:** Complete / Flagged for review
```

---

## Validate Mode

When the user asks to check data quality, or periodically as a maintenance task:

1. **Scan processed data folders** for all CSV files in `data/processed/`.

2. **Run validation checks** against each file's schema (from `references/data_schemas.md`):
   - Column names match schema
   - Data types are correct
   - Values are within expected ranges
   - Dates are valid
   - Required fields are populated
   - No unexpected duplicates

3. **Produce a data quality report** saved to `data/processed/data_quality_report.md`:

```markdown
# Data Quality Report — [Date]

## Summary
- Files checked: [count]
- Total records: [count]
- Issues found: [count]

## Issues by File
### [filename]
- [Description of issue, severity, suggested fix]
```

---

## Update Mode

When new measurements need to be merged with existing records:

1. **Load the existing processed file** and the new data.

2. **Match records** by identifier (tree_id, plot_id, transaction_id, etc.).

3. **For matching records:** Update with new values. Preserve the old values in a note or version column if the change is significant.

4. **For new records:** Append them to the existing file.

5. **For records in the old file but not in the new data:** Leave them unchanged (they weren't remeasured, not removed).

6. **Save the updated file** with the current date in the filename. Keep the previous version by renaming it with a `_prev_` prefix so nothing is lost.

7. **Log the update** in the processing log with counts: how many updated, how many added, how many unchanged.

---

## Status Mode

When the user asks "what data do we have?" or wants an overview:

1. **Inventory all processed data files** across all subfolders.

2. **Summarize each dataset:**
   - What type of data
   - How many records
   - Date range covered
   - When it was last updated
   - Any outstanding quality issues

3. **Identify gaps** — What data types have no records yet? What areas of the forest have no inventory data? What time periods are missing financial records?

4. **Present as a clear summary** to the user.

---

## Working With Other Agents

The Data Collector feeds every other agent in the system:

- **Forest Analyst** reads from `data/processed/inventory/` and `data/processed/remote_sensing/`
- **Financial Tracker** reads from `data/processed/financial/`
- **Stewardship Planner** uses data from all processed folders
- **Research Scout** may provide reference datasets to `research/data/` which the Data Collector can process

When other agents need specific data, they should check `data/processed/` first. If the data isn't there or is stale, they can ask the Data Collector to process new inputs.

---

## Handling Different Input Formats

The Data Collector should be able to handle whatever the user throws at it:

**Spreadsheets (.xlsx, .xls, .csv, .tsv)** — The most common input. Read with appropriate tools, identify the header row (it's not always row 1), and map columns to the schema.

**PDFs** — Sometimes reports or lab results come as PDFs. Extract tables and text, then map to the appropriate schema.

**Text files / field notes** — Unstructured notes from the field. Parse what you can, ask the user to clarify anything ambiguous.

**Images / photos** — Save to `data/raw/photos/` with descriptive names. Log metadata (date, location, subject) if it can be extracted.

**LiDAR files (.las, .laz)** — These are large and specialized. The Data Collector won't process the raw point clouds directly but should catalog them in `data/raw/` and process any derived metrics (CSVs of stand summaries, canopy height models) into the LiDAR Summary schema.

**GIS files (.shp, .geojson, .kml)** — Catalog in `data/raw/` and extract tabular attribute data into appropriate schemas.

---

## Important Guidelines

**Always preserve raw data.** Never modify files in `data/raw/`. The processed versions in `data/processed/` are what gets used day-to-day, but the originals are the ground truth.

**Be transparent about transformations.** Every change from raw to processed should be logged. The user should be able to trace any processed value back to its raw source.

**Ask when uncertain.** If a column is ambiguous, a value seems wrong, or the data type isn't clear, ask the user rather than guessing. A bad assumption in data processing can cascade through every analysis.

**Use consistent identifiers.** Plot IDs, tree IDs, and other identifiers should follow the conventions in the schemas. If incoming data uses different IDs, map them and document the mapping.

**Flag, don't fix, suspicious data.** If a tree is listed as 500 feet tall, don't silently change it to 50. Flag it for the user to verify. The "error" might actually be correct, or it might indicate a systematic issue with the measurements.

---

## File Locations

| Purpose | Location |
|---------|----------|
| Incoming raw data | `data/raw/` |
| Processed inventory data | `data/processed/inventory/` |
| Processed financial data | `data/processed/financial/` |
| Processed remote sensing data | `data/processed/remote_sensing/` |
| Processed ecology data | `data/processed/ecology/` |
| Processed climate data | `data/processed/climate/` |
| Processing log | `data/processed/processing_log.md` |
| Data quality reports | `data/processed/data_quality_report.md` |
| Data schemas reference | This skill's `references/data_schemas.md` |
