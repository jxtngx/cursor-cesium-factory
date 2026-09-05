# Technical Requirements Template (Cesium factory)

Write to `.cursor/plans/project-init/[slug]-technical-requirements.plan.md`.

```markdown
---
name: [App name]
overview: [One sentence]
track: [js-ion | js-selfhosted | js-local | unreal-ion | unity-ion]
problem_statement: [Why this globe]
github_repo: [owner/repo]
sprint_plan_file: .cursor/plans/project-init/[slug]-sprint.plan.md
todos:
  - id: spec
    content: Spec approved
    status: pending
  - id: skeleton
    content: Walking skeleton shows a globe on locked TRACK
    status: pending
  - id: mvp
    content: Must-have layers + tests
    status: pending
isProject: false
---

# [App name] — Technical Requirements

## User Story

As a [user], I want [behavior] so that [benefit].

## Problem Statement

[Pain. Why a generic Cesium sandcastle is not enough.]

## Platform (locked)

- **TRACK**: []
- **Runtime**: [CesiumJS | Unreal | Unity] version pin
- **Data host**: [ion | self-hosted | local]
- **Language**: [TypeScript | C++ | C#]

See sibling `[slug]-platform.plan.md`.

## Users

- Primary:
- Secondary:

## Auth

- [none | ion token | custom]

## Data

- Terrain / imagery:
- 3D Tilesets (MVP):
- Vectors / CZML / live:

## Offline

- [full | cache | online-only]

## Camera / time

- Default view:
- Clock: [yes | no]

## Must-have flows (MVP)

| Flow | Notes | Must-have |
| --- | --- | --- |
| [name] | | yes |

## Non-goals

- Not a Cesium fork
- Not a targeting system
- [ ]

## Definition of Done (MVP)

- [ ] Spec approved
- [ ] Globe visible on locked TRACK
- [ ] Domain tests green without a GPU
- [ ] No ion token in git
- [ ] TRACK honored

## Next

1. @chief-architect validates
2. @cesium-sme notes official APIs
3. @scrum-master writes sprint
```
