# AGENTS.md — Cursor Cesium Factory

This repository is a **factory**, not a lab.

Canonical contract: [cursor-kotlin-factory](https://github.com/jxtngx/cursor-kotlin-factory) and [cursor-swift-factory](https://github.com/jxtngx/cursor-swift-factory).

> **Lab** = the human writes the code. Mentors quiz and review.
> **Factory** = the human defines requirements. Chief Architect, SME, Scrum Master, and engineers **ship tickets**.

## Before the spec

Only `@init-globe` / `@launch-product-discovery`.
No Viewer, no Unreal/Unity project, no ion uploads.

## After the spec is approved

Engineers implement the ticket.
Do not send the Product Owner to type the globe themselves.

## Platform lock

`TRACK.md` is the source of truth after init:

- `js-ion`
- `js-selfhosted`
- `js-local`
- `unreal-ion`
- `unity-ion`

One product, one primary track.

Do not vendor Cesium source. Official npm / marketplace plugins only.

## Stack

CesiumJS + TypeScript + Vite on JS tracks.
Official Cesium for Unreal / Unity on native tracks.
3D Tiles. WGS84. Tokens in env.

## Markdown

No emojis. Semantic line breaks (one sentence per line).
