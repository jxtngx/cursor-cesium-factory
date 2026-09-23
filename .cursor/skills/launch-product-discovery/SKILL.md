---
name: launch-product-discovery
description: Launch Product Discovery (Cesium factory)
disable-model-invocation: true
---

# Launch Product Discovery (Cesium factory)

Same *shape* as [cursor-kotlin-factory](https://github.com/jxtngx/cursor-kotlin-factory) discovery.
Questions are about a **Cesium globe**, not a generic web app.

Called from `@init-globe` after TRACK is locked. If `TRACK.md` is missing, run `@init-globe` instead.

## Question sequence

### Q1 — Job

- One-sentence description
- Problem statement
- Product name

Give two examples first:

- "A wildfire command globe: stream a photogrammetry tileset, plot water-source entities, replay a 4-hour clock."
- "An offline survey viewer: local GeoJSON footprints on ellipsoid, no ion."

### Q2 — Users

```
- Analyst (desktop web)
- Field operator (tablet web)
- Simulation / Unreal operator
- Mixed
```

### Q3 — Auth / ion

```
- None (public tileset)
- Cesium ion token (env)
- Custom backend (name it)
```

### Q4 — Data

Name 3–7 layers. For each: terrain / imagery / 3D Tiles / vector / CZML / live feed.
On JS tracks, name whether vector tiles are MVP or later.

### Q5 — Offline

```
- Must work fully offline (local TRACK default)
- Cache tiles, network when available
- Online-only (ion default)
```

### Q6 — Camera and time

- Default view (place or dataset)
- Clock / time-dynamic (yes/no)
- First-person vs orbit vs geofence

### Q7 — Capabilities (track-aware)

Ask only what TRACK can do. Examples:

- JS: entity picking, measurement, clipping polygons, vector-tile style
- Unreal/Unity: pawn, physics, Sequencer / Timeline
- Live overlay: CoT / GeoJSON websocket (Adapter; later unless MVP)

### Q8 — Non-goals

At least three. Always include: not a Cesium fork; not a targeting system.

### Q9 — Repo

- GitHub `owner/repo` for the generated product
- Sprint plan filename
- Do not invent an ion account

## Write the spec

Use [technical-requirements-template.md](../templates/technical-requirements-template.md) and [platform-spec-template.md](../templates/platform-spec-template.md).

Do not implement.
Hand back to `@init-globe` step 3 if invoked from there; otherwise hand off to `@chief-architect`.
