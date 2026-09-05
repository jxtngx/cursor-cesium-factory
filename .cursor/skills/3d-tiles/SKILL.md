---
name: 3d-tiles
description: 3D Tiles and Cesium ion / self-hosted tileset seams. Use when TRACK involves tilesets, terrain, or vector tiles.
---

# 3D Tiles

- Pin tileset JSON URL or ion asset id in the spec, not in source as a secret.
- Domain describes layers; runtime loads them in an Adapter.
- Prefer fixtures for tests. Do not hit ion in CI.
- Vector tiles only if the pinned CesiumJS / Unreal version supports them.
