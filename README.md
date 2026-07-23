# US Farmers Markets 2026 — record-level dataset + state statistics

The cleaned, deduplicated US farmers-market dataset — **7,951 markets, record-level**, plus
state-by-state statistics — compiled from the
[USDA AMS Local Food Portal](https://www.usdalocalfoodportal.com/) and refreshed 2026.

**Canonical landing page (downloads, methodology, license):**
https://harvestlymarkets.com/data-sources/

## What's inside

- **`us-farmers-markets-2026.csv` / `.json` — the record-level dataset (NEW in v1.2):** all
  **7,951** deduplicated farmers markets with name, address, city/state/ZIP, coordinates,
  phone, website, social links, season, products, description, and attribute flags
  (SNAP/EBT, certified-organic, CSA vendor, indoor, delivery, payments). The JSON variant
  wraps the same records in a metadata header (license, DOI, generation date, count).
- **`us-farmers-markets-by-state-2026.csv`** — one row per state: counts of farmers markets,
  CSA programs, and farm stands, plus SNAP/EBT (11.4% nationally), certified-organic (13.2%),
  and working-website (42.9%) shares.
- **`datapackage.json`** — Frictionless Data Package descriptor + field schemas.

## What "cleaned" means

The raw USDA feed is rough: ~40-char truncated names, stale records, a `state=` filter that
substring-matches state *names* (querying "WA" returns Delaware rows), and thousands of
missing websites. This dataset is deduplicated to actual farmers markets (~270 merged
entries that were single-farm stands, mobile food pantries, or retail grocers are removed),
website coverage is backfilled from the live API + state sources to 42.9%, and dead website
URLs are stripped.

**Record-level field policy:** scraped third-party content (descriptions/images from market
websites) and personal contact names/emails are excluded — only USDA-derived fields, our
website/social backfill, and attribute flags ship in the redistributable.

## Versions

- **v1.3 (2026-07-22):** national de-duplication — count moved **8,863 → 7,951**. Removed 512
  registry twins (a 2023 USDA re-registration wave re-filed markets under new IDs without
  retiring the old rows) and 400 vendor-class records (individual farms/produce stands
  mis-filed as markets). An initial name-based pass mis-flagged ~30% of suspects (178 of 596
  were genuine markets, incl. California's entire CDFA roster), so every removal was re-checked
  against the relevant state Department of Agriculture registry. Methodology:
  https://harvestlymarkets.com/data-sources/#deduplication
- **v1.2 (2026-07-14):** record-level dataset added (CSV + JSON, 8,863 markets).
- **v1.1 (2026-07-07):** website-coverage correction — a USDA live-API state-filter bug had
  left 9 states without enrichment data, understating `markets_with_website`; per-state
  `website_pct` is now accurate (national ~50%).
- **v1.0:** initial state-level release.

## Source & license

Derived from the USDA AMS Local Food Portal (public data). Published under **CC BY 4.0** — free to
reuse, share, and adapt with attribution. Archived, citable version:
[DOI 10.5281/zenodo.21138301](https://doi.org/10.5281/zenodo.21138301).

> Attribution: Harvestly Markets — US Farmers Markets 2026 (CC BY 4.0), derived from USDA AMS
> Local Food Portal. https://harvestlymarkets.com/data-sources/
