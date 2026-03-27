---
layout: project-dark
title: Red Kites
kicker: "Wildlife & Data"
hero_image: /assets/images/red-kites-timeline.png
hero_alt: "Timeline of red kite sightings across the UK, 1988–2023"

intro: >
  From near-extinction in the 1980s to one of Europe's great wildlife recovery stories.
  This project maps the reintroduction and spread of red kites across Britain using
  occurrence records from the NBN Atlas, combined with manually
  sourced reintroduction data from conservation literature.

cards:
  - icon: "🗺"
    label: Interactive
    title: Explore the Map
    href: /projects/red-kite/red_kite_spread.html
    desc: >
      Step through the reintroduction of the red kite, from the last Welsh survivors to today's
      flourishing population — with reintroduction routes and sighting density overlaid.
    arrow: Open map

  - icon: "📊"
    label: Data source
    title: NBN Atlas Records
    href: https://nbnatlas.org
    desc: >
      *Milvus milvus* occurrence download from the National Biodiversity Network Atlas,
      accessed 13 January 2026. Data contributed by the British Trust for Ornithology
      across ten datasets (BTO Atlases, BirdTrack, and WeBS).
    arrow: Visit NBN Atlas

  - icon: "⌥"
    label: "Source code & data"
    title: GitHub Repository
    href: https://github.com/anapier/red-kites
    desc: >
      Python processing script, reintroduction data with full source citations,
      and the map template.
    arrow: View on GitHub

steps:
  - title: Occurrence data from the NBN Atlas
    body: >
      I downloaded all *Milvus milvus* records from the
      [National Biodiversity Network Atlas](https://nbnatlas.org)
      on 13 January 2026. The download spans ten BTO datasets — bird atlases
      (1968–72, 1981–84, 1988–91), BirdTrack, and the Wetland Bird Survey —
      giving coverage from the 1960s through to 2024.

  - title: Reintroduction data compiled from primary sources
    body: >
      There's no single authoritative database of red kite release sites, so I
      assembled the reintroduction records by hand from conservation literature:
      Evans et al. (1999) in *Bird Study*, Natural England and NatureScot
      commissioned reports, RSPB archives, and local wildlife groups. Each site
      is cited in the
      [sources file](https://github.com/anapier/red-kites/blob/main/reintroductions_sources.md)
      in the repository.

  - title: Normalising to 10km grid squares
    body: >
      All sightings are normalised to their 10km parent OSGB grid square regardless
      of the original record precision. This lets the map show population *spread*
      over time without being skewed by the patchy density of modern fine-grained records
      versus older coarser ones.

  - title: Coordinate conversion and polygon generation
    body: >
      The Python script uses [pyproj](https://pyproj4.github.io/pyproj/)
      to convert OSGB36 National Grid coordinates to WGS84 latitude/longitude, then
      [Shapely](https://shapely.readthedocs.io/) to construct the polygon boundary
      for each 10km square. This is pre-computed once and baked into the output HTML
      to keep the map fast.

  - title: Map rendering with Leaflet and Jinja2
    body: >
      An html template wraps a [Leaflet.js](https://leafletjs.com/) map, embedding
      all the pre-computed polygon data and era narratives as JSON. The script renders
      the template to a single self-contained HTML file — no server required, no
      runtime API calls.

pills:
  - Python
  - pandas
  - Shapely
  - pyproj
  - Leaflet.js
  - NBN Atlas
  - OSGB National Grid

attribution_intro: >
  NBN Atlas occurrence download accessed 13 January 2026.
  Data contributed by the British Trust for Ornithology under
  Creative Commons Attribution Non-Commercial (CC BY-NC 4.0) and Open Government Licence (OGL).

attribution:
  - name: "British Trust for Ornithology. BTO First Atlas of Wintering Birds in Britain and Ireland: 1981/82–1983/84."
    id: dr1237
    url: https://registry.nbnatlas.org/public/show/dr1237
    licence: CC BY-NC

  - name: "Records provided by BTO (BirdTrack)."
    id: dr2380
    url: https://registry.nbnatlas.org/public/show/dr2380
    licence: CC BY-NC

  - name: "Records provided by BTO (BirdTrack)."
    id: dr528
    url: https://registry.nbnatlas.org/public/show/dr528
    licence: CC BY-NC

  - name: "British Trust for Ornithology. BTO First Atlas of Breeding Birds in Britain and Ireland: 1968–1972."
    id: dr1372
    url: https://registry.nbnatlas.org/public/show/dr1372
    licence: CC BY-NC

  - name: "Records provided by BTO."
    id: dr2370
    url: https://registry.nbnatlas.org/public/show/dr2370
    licence: OGL

  - name: "Records provided by BTO (BirdTrack)."
    id: dr2381
    url: https://registry.nbnatlas.org/public/show/dr2381
    licence: CC BY-NC

  - name: "Records provided by BTO."
    id: dr3162
    url: https://registry.nbnatlas.org/public/show/dr3162
    licence: CC BY-NC

  - name: "Records provided by BTO (BirdTrack)."
    id: dr2382
    url: https://registry.nbnatlas.org/public/show/dr2382
    licence: CC BY-NC

  - name: "Records provided by British Trust for Ornithology."
    id: dp29
    url: https://registry.nbnatlas.org/public/show/dp29

  - name: "British Trust for Ornithology. BTO Second Atlas of Breeding Birds in Britain and Ireland: 1988–1991."
    id: dr1156
    url: https://registry.nbnatlas.org/public/show/dr1156
    licence: CC BY-NC
---
