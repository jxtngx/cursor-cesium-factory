# Cursor Cesium Factory

A **factory**, not a lab.

This repo is boilerplate for a new **Cesium** geospatial product.
The default product class is a **CesiumJS TypeScript globe**.
Cesium for Unreal and Cesium for Unity are the other tracks.
Cursor's team implements from a spec you write in the first session.

> **Lab** = student writes the code. Mentors quiz and review.
> **Factory** = you define requirements. Chief Architect, SME, Scrum, and engineers ship tickets.

Sister factories: [cursor-kotlin-factory](https://github.com/jxtngx/cursor-kotlin-factory) · [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory) · [cursor-fullstack-factory](https://github.com/jxtngx/cursor-fullstack-factory).

This factory is tightly coupled to **official Cesium runtimes** and **3D Tiles**.
One generated product, one primary track.

If you wanted to *learn* Cesium by typing every primitive yourself, that would be a lab. This is not that.

Official references (do not vendor their trees):

- [CesiumJS](https://cesium.com/learn/cesiumjs/ref-doc/)
- [3D Tiles](https://www.ogc.org/standards/3DTiles/)
- [Cesium ion](https://cesium.com/learn/ion/)
- [Cesium for Unreal](https://cesium.com/learn/unreal/)
- [Cesium for Unity](https://cesium.com/learn/unity/)

Geospatial visualization and civil SA overlays only.
This factory does not implement targeting or weapons employment.

---

## First command

Open this repo in Cursor and run:

```
@init-globe
```

That command:

1. Asks **CesiumJS, Cesium for Unreal, or Cesium for Unity** (one generated product)
2. Asks **ion, self-hosted 3D Tiles, or local tiles** (JS tracks; native defaults to ion unless you override)
3. Walks the same style of **requirements interview** as [cursor-kotlin-factory](https://github.com/jxtngx/cursor-kotlin-factory)
4. Writes `.cursor/plans/project-init/<name>-technical-requirements.plan.md`
5. Writes `TRACK.md`
6. Hands off to `@chief-architect` → `@cesium-sme` → `@scrum-master` → tickets

Do not ask an engineer to "just drop a Viewer in index.html" before the spec exists.

---

## Opinionated stack (not optional)

| Layer | Choice |
| --- | --- |
| JS runtime | CesiumJS from npm, TypeScript. Vite host. React/Next only if the spec names them as a shell |
| Native | Official Cesium for Unreal or Cesium for Unity plugin. Do not fork Cesium source |
| Tiles | 3D Tiles (1.1; vector tiles when the pinned runtime supports them) |
| Globe | WGS84 / ECEF. Game-engine coords are an Adapter, not the domain |
| Ion | Token from env. Never in git. Optional; self-hosted and local tracks are first-class |
| Domain | Entities and tracks in TypeScript (or C++/C# on native) without `Viewer` types |
| Tests | Vitest (JS) / native unit tests for domain. "It rendered on my GPU" is not a test |
| Secrets | `.env` / ion token. Never in git |

You may add datasets the spec names.
You may not replace CesiumJS with Leaflet-first as the default without an ADR.
You may not vendor the Cesium GitHub tree into this repo as "the app."

---

## Team

| Agent | Job |
| --- | --- |
| Product Manager | `@init-globe` / `@launch-product-discovery` — spec only |
| Chief Architect | Feasibility, module map, TRACK, Viewer vs domain seam |
| Cesium SME | Official CesiumJS / ion / Unreal / Unity APIs, 3D Tiles |
| Scrum Master | Sprint + tickets from the spec |
| Feature Engineer | Camera, entities, UI chrome around the globe |
| Platform Engineer | Vite / Unreal/Unity project files / CI |
| Data Engineer | 3D Tiles, ion assets, GeoJSON / CZML / CoT Adapter |
| Test Engineer | Domain tests, camera invariants, tile-load fixtures |
| Reviewer | Correctness, token leaks, GPU-only "tests", TRACK drift |

Engineers **do** implement here. That is the factory contract.

---

## After init (typical)

```
@init-globe
  → approve technical requirements
@chief-architect
@cesium-sme
@scrum-master
@run-ticket-plan
@review-cesium
```

---

## Repo layout (this boilerplate)

```
.cursor/
  commands/     init-globe, launch-product-discovery, run-ticket-plan, review-cesium
  agents/       factory team
  skills/       3d-tiles, cesium-viewer
  templates/    technical-requirements, platform spec, sprint guide
  plans/project-init/
templates/
  js-ion/
  js-selfhosted/
  js-local/
  unreal-ion/
  unity-ion/
TRACK.md
```

The tracks you did **not** pick stay in `templates/` as reference and are not the product.

---

## Related repos

| Repo | Kind |
| --- | --- |
| [cursor-kotlin-factory](https://github.com/jxtngx/cursor-kotlin-factory) | Factory — ATAK-CIV / Compose |
| [cursor-fullstack-factory](https://github.com/jxtngx/cursor-fullstack-factory) | Factory — web product shell |
| [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory) | Factory — Swift / SwiftUI |
| [jxtngx/jxtngx design-philosophies.md](https://github.com/jxtngx/jxtngx/blob/master/design-philosophies.md) | Language contracts |

---

## License

Apache-2.0. See [LICENSE](LICENSE).
Not affiliated with Cesium GS, Inc.
CesiumJS and Cesium ion are separate works with their own licenses and terms.
