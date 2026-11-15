# Can the People Who Run the County Live in the County?
**8th Annual Datathon for Social Good**

## Project Links
- **Live Tableau Public Dashboard:** https://public.tableau.com/app/profile/adam.myat6508/viz/Datathon2026CanCountyWorkersAffordtoLiveHere/FLIPPAYSLIDE
- **Slideshow Presentation:** https://canva.link/jnfzet5qxbsypy8
- **Video Overview (≤ 5 min):** https://www.youtube.com/watch?v=H1Uh1BHjdo0

## Essential Question
Can Bay Area public-sector workers—teachers, nurses, sheriff's deputies/law enforcement, bus/transit operators, social workers, librarians, and 911 dispatchers—afford to live in the communities they serve?

## Key Findings
- **All 59 reliable Bay Area cities exceed $35/hr needed:** At the 30% gross-income rule (12 hours of a 40-hour week), median 1BR asking rent ranges from **$1,825/mo in Vallejo ($35.10/hr needed)** to **$4,076.50/mo in San Carlos ($78.39/hr needed)**.
- **Essential roles priced out at Bay Area median posted pay:**
  - **Teachers ($30.02/hr):** 0 of 59 cities affordable
  - **Bus/Transit Operators ($31.25/hr):** 0 of 59 cities affordable
  - **Librarians ($34.78/hr):** 0 of 59 cities affordable
  - **Social Workers ($39.83/hr):** 6 of 59 cities affordable
  - **911 Dispatchers ($41.99/hr):** 12 of 59 cities affordable
  - **Law Enforcement ($58.40/hr):** 40 of 59 cities affordable
  - **Nurses ($70.41/hr):** 53 of 59 cities affordable
- **All-jobs averages hide public-sector strain:** High-wage corporate/tech postings pull overall city medians below the 30% threshold in hubs like San Francisco and Mountain View, while county workers in those same cities face 32%–78% 1BR rent burdens.
- **Pay transparency gap (SB 1162):** **29.0%** of job postings across the 59 cities omit salary information despite California's SB 1162 pay-disclosure requirement.
- **Commute displacement:** Across 63 role × county-seat pairs, **18 have no affordable city** anywhere in the 59-city dataset.

## Repository Structure
- `notebooks/datathon_posted_forever.ipynb` — End-to-end cleaning, normalization, join, and affordability calculation pipeline.
- `data/` — City-level, county-level, and role-level aggregated outputs:
  - `city_rent_tableau_v2.csv`, `zillow_1br_rent_listings_by_city.csv`, `city_essentials.csv`, `city_jobs_summary.csv`
  - `persona_benchmarks.csv`, `persona_affordability_summary.csv`, `persona_city_matrix.csv`, `persona_county_v2.csv`
  - `role_city_v2.csv`, `hardest_hit_v2.csv`, `leaderboard_reposts_v2.csv`, `county_summary_v2.csv`, `commute_shadow_lines.csv`
- `visuals/` — Exported Tableau workbook views used in the presentation.

## Reproducibility &amp; Data Notes
- Raw datasets (Zillow Housing, Indeed Jobs, and Google Maps Places from the 8th Annual Datathon shared drive) are excluded due to file size and privacy rules.
- Zillow records were filtered strictly to `FOR_RENT` 1-bedroom listings across 59 cities with `n >= 30` listings, and all housing outputs are aggregated at the city level (no street addresses).
- Indeed reposts were deduplicated and salary strings converted to hourly/annual equivalents (`hourly × 2,080`), while preserving missing-salary flags for SB 1162 auditing.
- Google Maps Places records were filtered to open locations (`permanently_closed == False`) within the 9 Bay Area counties.
