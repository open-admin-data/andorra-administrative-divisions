# Andorra Administrative Divisions / Andorra



## Overview

| Item | Details |
|------|---------|
| Parish | 7 |
| Locality | 56 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-07-25 |
| Website | [openadmindata.org/ad](https://openadmindata.org/ad/) |
| API | [openadmindata.org/api/ad](https://openadmindata.org/api/ad/) |

## Browse by Parish

| # | Parish | Localitys | Link |
|---|----|----|------|
| 1 | Andorra la Vella | 1 | [Browse](divisions/andorra-la-vella-ad01/) |
| 2 | La Massana | 14 | [Browse](divisions/la-massana-ad02/) |
| 3 | Ordino | 7 | [Browse](divisions/ordino-ad03/) |
| 4 | Canillo | 9 | [Browse](divisions/canillo-ad04/) |
| 5 | Encamp | 7 | [Browse](divisions/encamp-ad05/) |
| 6 | Escaldes-Engordany | 4 | [Browse](divisions/escaldes-engordany-ad06/) |
| 7 | Sant Julià de Lòria | 14 | [Browse](divisions/sant-julia-de-loria-ad07/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-parish.json](data/all-parish.json) | JSON | All 7 parish records |
| [all-locality.json](data/all-locality.json) | JSON | All 56 locality records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-parish.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['locality']} localitys")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-parish.json", "utf-8"));
console.log(`Total: ${data.length} parishs`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=parish, 2=locality |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{parish-slug}/
```

Localitys are listed inline in each parish's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-parish links
- [Per-parish data](docs/llms-full/) — Full data by parish

## Citation

```
Andorra Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/andorra-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
