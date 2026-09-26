# Canonical Urth map-imagery pipeline: XCF layers to atlas PNGs for urth-atlas.

Reads GIMP sources from [urth-rp/urthmaps](https://github.com/urth-rp/urthmaps)
(read-only — that repo needs no changes), exports the mapped layers
headlessly, and commits PNGs to `atlas/` + `assets/`. urth-atlas pulls
`atlas/*.png` via its `map-imagery.yml` workflow.

| XCF layer              | atlas file                | atlas use              |
|------------------------|---------------------------|------------------------|
| Labels/Cities          | atlas/cities.png          | city markers           |
| Labels/Sub-National    | atlas/subnational.png     | subnational markers    |
| Political              | atlas/blank-political.png | base political map     |
| Labels/National        | atlas/national.png        | nation markers         |
| Ocean                  | atlas/ocean.png           | ocean base             |

Triggers: daily schedule (picks up upstream map patches), manual
`workflow_dispatch` (first seed + re-runs), and `workflow_call` so
urth-rp/urthmaps — or anyone — can invoke the export on their own events.

Tooling lives in [xcf-git-sync](https://github.com/EmjayBot/xcf-git-sync).

Local test: pip install "git+https://github.com/EmjayBot/xcf-git-sync.git"
  xcf-git-sync --config xcf-sync.yaml --once
