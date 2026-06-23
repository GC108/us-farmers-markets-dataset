# US Farmers Market Statistics 2026

State-by-state statistics for farmers markets across the United States — per-state counts plus
SNAP/EBT acceptance and certified-organic share — compiled from the
[USDA AMS Local Food Portal](https://www.usdalocalfoodportal.com/) and refreshed 2026.

**Canonical landing page (methodology, license, and the full interactive table):**
https://harvestlymarkets.com/farmers-market-statistics/

## What's inside

- Per-state counts of farmers markets, CSA programs, and farm stands across all 50 states, DC, and territories (~7,056 farmers markets nationwide)
- Share of markets accepting **SNAP/EBT** benefits (~13% nationally)
- Share of markets with **certified-organic** vendors (~15%)
- Share of markets with a **working website** (~31%)

## Files

- `us-farmers-markets-by-state-2026.csv` — one row per state with the metrics above
- `datapackage.json` — Frictionless Data Package descriptor + field schema

## Fields

| Field | Description |
|-------|-------------|
| `state_name` / `state_abbr` | State name and two-letter abbreviation |
| `farmers_markets` | Number of farmers markets |
| `csa_programs` | Number of CSA programs |
| `farm_stands` | Number of farm stands |
| `snap_ebt_markets` / `snap_ebt_pct` | Markets accepting SNAP/EBT, count and percent |
| `organic_vendor_markets` / `organic_pct` | Markets with certified-organic vendors, count and percent |
| `markets_with_website` / `website_pct` | Markets with a working website, count and percent |

## Source & license

Derived from the USDA AMS Local Food Portal (public data). Published under **CC BY 4.0** — free to
reuse, share, and adapt with attribution.

> Attribution: Harvestly Markets — US Farmers Market Statistics 2026 (CC BY 4.0), derived from USDA AMS
> Local Food Portal. https://harvestlymarkets.com/farmers-market-statistics/
