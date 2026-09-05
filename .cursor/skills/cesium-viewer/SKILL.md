---
name: cesium-viewer
description: CesiumJS Viewer / Widget and camera Adapter. Use when reviewing globe UI diffs on JS tracks.
---

# Cesium viewer

- One Viewer (or Widget) owned by the host. Do not construct a second globe.
- Camera flights are functions over domain poses (lon/lat/height/heading), not leaked Viewer state.
- Destroy the Viewer on teardown. Leaked WebGL contexts fail later tickets.
