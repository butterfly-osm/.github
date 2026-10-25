<picture>
  <source media="(prefers-color-scheme: dark)" srcset="banner-dark.svg">
  <img alt="Butterfly — a routing engine and OpenStreetMap toolkit, in Rust" src="banner-light.svg" width="100%">
</picture>

<p align="center">
  <a href="https://github.com/butterfly-osm/butterfly-osm#quickstart"><b>Quickstart</b></a> ·
  <a href="https://github.com/butterfly-osm/butterfly-osm#features">Features</a> ·
  <a href="https://github.com/butterfly-osm/butterfly-osm#performance-belgium-arrow-flight-vs-arrow-flight">Benchmarks</a> ·
  <a href="https://github.com/butterfly-osm/butterfly-osm#documentation">Docs</a> ·
  <a href="https://github.com/butterfly-osm/butterfly-osm/issues">Issues</a>
</p>

<p align="center">
  <img alt="Rust" src="https://img.shields.io/badge/rust-workspace-2a6fc4?style=flat-square&logo=rust">
  <img alt="Arrow Flight" src="https://img.shields.io/badge/Arrow_Flight-gRPC-2a6fc4?style=flat-square">
  <img alt="Deployed" src="https://img.shields.io/badge/belgium--latest-deployed-2a6fc4?style=flat-square">
  <a href="https://github.com/butterfly-osm/butterfly-osm/blob/main/LICENSE"><img alt="AGPL-3.0" src="https://img.shields.io/badge/license-AGPL--3.0-2a6fc4?style=flat-square"></a>
</p>

Routes, matrices, isochrones and multimodal transit on **one edge-based CCH** with exact turn restrictions, so every answer agrees with the others. REST for humans, **Arrow Flight gRPC** for code.

| | Project | What it is |
|---|---|---|
| 🦋 | [**butterfly-route**](https://github.com/butterfly-osm/butterfly-osm/tree/main/route) | The routing engine: car, bike, foot, truck, plus RAPTOR + ULTRA transit over merged GTFS and NeTEx feeds. |
| ⬇️ | [**butterfly-dl**](https://github.com/butterfly-osm/butterfly-osm/tree/main/dl) | OSM downloader: under 1 GB of RAM for any file, up to the 81 GB planet. 79% faster than aria2. |

#### By the numbers (Belgium, same host, wire to wire)

| | Butterfly | Reference | |
|---|---:|---:|---|
| Matrix 10k × 10k | **32.5 s** | 614 s (libosrm) | 19× faster |
| Matrix 50k × 50k | **9.6 min** | doesn't scale | — |
| Isochrone, 5 min | **6 ms** | 24 ms (Valhalla) | 4× faster |
| 1 000 real trips | **MAPE 4.0 %** | correlation 0.994 | ground truth |

We also publish [where Butterfly still trails](https://github.com/butterfly-osm/butterfly-osm#where-butterfly-currently-trails).

```python
import pyarrow.flight as fl
client = fl.connect("grpc://localhost:3002")   # REST on 3001, Flight on 3002
```

<sub>Built in Belgium for the OpenStreetMap community. Map data © OpenStreetMap contributors.</sub>
