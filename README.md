# gunnison-housing-snapshots
Interactive snapshots of Gunnison County’s housing market pre- vs post-COVID (2017–18 vs 2022–23) using cleaned assessor sales, with affordability and national context.

# Gunnison County Pre/Post COVID Housing Snapshots

Interactive, public-facing dashboard comparing **2017–2018 (pre-COVID)** with **2022–2023 (post-COVID)** housing sales in Gunnison County, CO.

VIEW HERE ->  **https://eesterlein.github.io/gunnison-housing-snapshots/** 
---

## What’s inside

- **Interactive dashboard** (`index.html`) with:
  - Toggle between **All property types** and a **Residential proxy (≥800 sq ft)**.
  - “Typical sale (median)” cards with price, size, and sales counts.
  - **Affordability** shown as **% of U.S. households able to afford**  
    *(assumes 20% down, 30% payment-to-income threshold, prevailing mortgage rates, and national median household income)*.
  - **Quarterly** median price & sales charts with a dashed **pre/post divider**.
  - **National context** chart (U.S. median vs Gunnison median).
  - Local context notes (Crested Butte condos, ranch transfers, mobile homes).

---

## Data & cleaning

**Source:** Gunnison County Assessor sales dataset.

**Cleaning steps:**
- Removed **$0 transfers** and **obvious non–arm’s-length** records (e.g., *grantor = grantee*).
- Dropped duplicate `(ACCOUNTNO, SALEDATE, SALEPRICE)` rows.
- **Included transactions at or below $15M**; **excluded sales over $15M** to omit trophy/estate outliers while retaining local luxury homes.
- Medians are computed for the snapshots: **2017–2018** and **2022–2023**.
- The **Residential proxy** lens filters to records with **IMPNETSF ≥ 800 sq ft** as a simple single-family-style proxy.

> ⚠ Figures reflect **assessor data medians** and may differ from **MLS-only** publications. The middle years (2019–2021) are omitted to keep the focus on pre vs post snapshots.

---

## Notes & limitations

- **Property mix:** “All property types” includes mobile homes, ranch parcels, condos, and vacant land. Use the **Residential proxy (≥800 sq ft)** for a closer single-family lens.  
- **Affordability metric:** Shown as the **% of U.S. households able to afford** the typical Gunnison sale, assuming **20% down**, **30% payment-to-income**, **prevailing mortgage rates**, and **national median household income**. This is a national benchmark for comparability, not a local underwriting decision.  
- **Snapshot medians:** Figures are **medians for 2017–2018** (pre-COVID) and **2022–2023** (post-COVID). Middle years (2019–2021) are intentionally omitted to emphasize before/after. Use the **quarterly charts** for within-window trends.  
- **Dataset vs MLS:** Source is the **Gunnison County Assessor** dataset; results may differ from **MLS-only** statistics because the assessor data includes a broader set of recorded transfers.  
- **Cleaning rules:** Removed **$0 transfers** and **obvious non–arm’s-length** records; deduplicated by `(ACCOUNTNO, SALEDATE, SALEPRICE)`. **Sales over $15M are excluded**; transactions **at or below $15M are included** to retain local luxury while trimming trophy outliers.  
- **Method caveat:** Results are descriptive analytics for public communication. They are **not appraisals or valuations** and shouldn’t substitute for professional lending or appraisal standards.
 

## How to view

- **Live Report** https://eesterlein.github.io/gunnison-housing-snapshots/

- **Locally:** open `index.html` in any browser (no build step required).

---

## Repo layout

```text
index.html   # the dashboard 
README.md    # this file

