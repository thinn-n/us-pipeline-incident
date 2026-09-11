# US Pipeline Incident Atlas

An interactive, multi-page atlas of four decades of United States pipeline incidents — oil spills, gas leaks, transmission ruptures and LNG events — built from official regulator data.

**Live site:** https://thinn-n.github.io/us-pipeline-incident/

## What it shows

Every reportable pipeline incident filed with the US Pipeline and Hazardous Materials Safety Administration (PHMSA) between 1986 and 2026, mapped and broken down by system.

- **21,428** incidents across all four pipeline systems
- **11,068** geo-located and plotted as individual dots
- **293** deaths and **1,191** injuries
- **$17.8B** in reported damage (current-year dollars)

The headline finding: **Texas alone accounts for roughly a quarter of all US pipeline incidents**, and while liquid spills are the most common type, **gas distribution lines — the mains under our streets — are by far the deadliest**, causing most of the recorded fatalities despite fewer incidents.

## The four systems

| System | Incidents | Notes |
|---|---|---|
| Hazardous liquid | 12,083 | Crude oil and petroleum spills — the largest category |
| Gas distribution | 4,922 | Local mains and service lines — the deadliest |
| Gas transmission | 4,370 | High-pressure long-distance lines |
| LNG | 53 | Liquefied natural gas facilities |

## Structure

A landing hub links out to a dedicated map for each system, plus a combined view:

```
index.html              Landing hub
├─ liquid-spills.html        Hazardous liquid map
├─ gas-transmission.html     Gas transmission map
├─ gas-distribution.html     Gas distribution map
└─ all-incidents.html        All systems, one map
```

Each map page has its own headline stats, an interactive map, a top-states breakdown and a per-year trend, plus a written insight.

## Features

- Interactive Leaflet maps with ~11,000 plotted incidents
- Hover tooltips and click-through popups on every incident
- Pulsing "alert" beacons on the largest incidents and a gently breathing dot field
- Colour coding by pipeline system, filterable on the combined map
- Animated count-up statistics and chart reveals
- Fully responsive; respects reduced-motion preferences

## Data

Source: [PHMSA Pipeline Incident Flagged Files](https://www.phmsa.dot.gov/data-and-statistics/pipeline/pipeline-incident-flagged-files), the public dataset regulators use to track 20-year pipeline-safety trends.

The raw files span three reporting eras with different schemas (68 to 668 columns each). They were merged and cleaned into a single consistent dataset. Incidents reported before 2002 lack coordinates, so they contribute to the charts and totals but do not appear as map dots — a scope note on each page makes this explicit.

**Scope:** United States only. PHMSA regulates US pipelines, and no single global dataset records individual incidents at this level of detail.

## Built with

- [Leaflet](https://leafletjs.com/) for the maps
- Esri light/dark tiles for the basemap
- Plain HTML, CSS and JavaScript — no build step, no dependencies to install
- Self-contained files that open in any browser and work offline

## Running locally

No build tools required. Clone the repo and open `index.html` in a browser:

```bash
git clone https://github.com/ollielie/pipeline-incident-atlas.git
cd pipeline-incident-atlas
open index.html
```

## Licence & attribution

Incident data is public and published by the US Department of Transportation (PHMSA). This project is a personal data-visualisation piece and is not affiliated with or endorsed by PHMSA or the US DOT.
