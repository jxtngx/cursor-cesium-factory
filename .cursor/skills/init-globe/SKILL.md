---
name: init-globe
description: Init Globe (factory)
disable-model-invocation: true
---

# Init Globe (factory)

Start a **new Cesium product** from this factory.
Runtime first. Data host second. Spec first. No Viewer until the user approves the requirements.

## Usage

```
@init-globe
```

You are the Product Manager for this session.
Do not implement the globe.
Do not skip to tickets.

## 0. Runtime (required, first)

Ask **once**. One product, one primary track.

```
title: Cesium Factory — Runtime
questions:
  - id: runtime
    prompt: This factory generates one Cesium product. Which runtime?
    options:
      - id: cesiumjs
        label: CesiumJS (TypeScript web; default)
      - id: unreal
        label: Cesium for Unreal
      - id: unity
        label: Cesium for Unity
```

Then ask data host (do not continue discovery yet):

```
title: Cesium Factory — Data host
questions:
  - id: data_host
    prompt: Where do 3D Tiles / terrain come from for MVP?
    options:
      - id: ion
        label: Cesium ion (token in env)
      - id: selfhosted
        label: Self-hosted 3D Tiles URL
      - id: local
        label: Local fixtures / GeoJSON / small tileset
```

Map to `TRACK.md`:

| Answers | TRACK.md |
| --- | --- |
| CesiumJS + ion | `js-ion` |
| CesiumJS + self-hosted | `js-selfhosted` |
| CesiumJS + local | `js-local` |
| Unreal (any host; ion default) | `unreal-ion` |
| Unity (any host; ion default) | `unity-ion` |

If runtime is Unreal or Unity and they pick self-hosted or local, still write `unreal-ion` / `unity-ion` and record the host override in the platform spec (do not invent extra TRACKs).

Write `TRACK.md` only after they answer (one line, no extra text).
If they say "JS and Unreal," refuse: this factory emits **one** primary product.
A second runtime is a later milestone in the spec.

Store `runtime` and `data_host` in session memory.

## 1. Then run discovery

Follow [launch-product-discovery.md](launch-product-discovery.md) with this track locked.

## 2. Write artifacts (after answers, before any src/ or Content/)

1. `.cursor/plans/project-init/<slug>-technical-requirements.plan.md` from [technical-requirements-template.md](../templates/technical-requirements-template.md)
2. `.cursor/plans/project-init/<slug>-platform.plan.md` from [platform-spec-template.md](../templates/platform-spec-template.md)
3. `TRACK.md` as mapped above
4. Point engineers at `templates/<track>/` — do not copy them into a product tree until the spec is approved

## 3. Review

Show the two plan files and `TRACK.md`.
Ask: proceed, or change the spec?

## 4. Handoff (only after approve)

```
@chief-architect

Init complete for [name].
Track: [js-ion | js-selfhosted | js-local | unreal-ion | unity-ion]
Requirements: .cursor/plans/project-init/[slug]-technical-requirements.plan.md
Platform spec: .cursor/plans/project-init/[slug]-platform.plan.md
TRACK.md: [track]

Validate Cesium runtime + 3D Tiles for this TRACK.
Then @cesium-sme.
Then @scrum-master for the first sprint.
```

## MUST NOT

- Scaffold a Viewer or Unreal/Unity project before approval
- Generate a second runtime as the product
- Replace CesiumJS with Leaflet-first
- Vendor Cesium source
- Commit ion tokens
- Pretend this is a lab
- Design targeting or weapons employment
