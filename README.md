# Niger Administrative Divisions / Niger



## Overview

| Item | Details |
|------|---------|
| Region | 8 |
| Department | 67 |
| Commune | 266 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-06-01 |
| Website | [openadmindata.org/ne](https://openadmindata.org/ne/) |
| API | [openadmindata.org/api/ne](https://openadmindata.org/api/ne/) |

## Browse by Region

| # | Region | Departments | Communes | Link |
|---|----|----|----|------|
| 1 | Zinder | 11 | 55 | [Browse](divisions/zinder-ne007/) |
| 2 | Dosso | 8 | 43 | [Browse](divisions/dosso-ne003/) |
| 3 | Tillabéri | 13 | 45 | [Browse](divisions/tillabri-ne006/) |
| 4 | Tahoua | 13 | 44 | [Browse](divisions/tahoua-ne005/) |
| 5 | Agadez | 6 | 15 | [Browse](divisions/agadez-ne001/) |
| 6 | Niamey | 1 | 5 | [Browse](divisions/niamey-ne008/) |
| 7 | Diffa | 6 | 12 | [Browse](divisions/diffa-ne002/) |
| 8 | Maradi | 9 | 47 | [Browse](divisions/maradi-ne004/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-region.json](data/all-region.json) | JSON | All 8 region records |
| [all-department.json](data/all-department.json) | JSON | All 67 department records |
| [all-commune.json](data/all-commune.json) | JSON | All 266 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-region.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['department']} departments")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-region.json", "utf-8"));
console.log(`Total: ${data.length} regions`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=region, 2=department, 3=commune |
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
divisions/{region-slug}/
divisions/{region-slug}/{department-slug}/
```

Communes are listed inline in each department's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-region links
- [Per-region data](docs/llms-full/) — Full data by region

## Citation

```
Niger Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/niger-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
