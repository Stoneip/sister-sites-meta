# sister-sites-meta

Single source of truth for cross-site metadata used across the HK info network sister sites.

## Sites covered

- techritual.com — tech blog
- points852.com — travel + credit card miles
- speedtesthk.com — speed test + OFCA monthly reports
- primaryhk.com — HK primary school admission
- simcardhk.com — HK SIM card price comparison

## Usage

Fetch at build time from each consuming site:

```bash
curl -sL https://raw.githubusercontent.com/Stoneip/sister-sites-meta/main/sites.json > src/data/sister-sites.json
```

Or via jsDelivr (CDN cached, ~12 hr propagation):

```bash
curl -sL https://cdn.jsdelivr.net/gh/Stoneip/sister-sites-meta@main/sites.json > src/data/sister-sites.json
```

## Schema

See `sites.json`. Top-level keys: `publisher`, `sites[]`, `lastUpdated`, `schemaVersion`.

## Update workflow

1. Edit `sites.json` on `main`
2. Commit + push
3. Each consuming site picks up at next build/deploy
