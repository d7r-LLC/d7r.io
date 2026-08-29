# Contributing

This repository is the index, not the specifications.

## What belongs here

- Dead links, wrong repository or site URLs, license or status drift
- Defects in the site under `site/`
- Drift between `site/registry/specs.json` and the actual state of a spec repo

Open an issue or a pull request. Keep `README.md`, `site/index.html`, and
`site/registry/specs.json` in agreement: the registry is canonical, and the other two
must match it.

## What belongs elsewhere

Spec-level feedback, proposed changes, and RFCs belong in the individual spec
repositories:

- [agent-rights](https://github.com/d7r-LLC/agent-rights)
- [derp-spec](https://github.com/d7r-LLC/derp-spec)
- [saga-standard](https://github.com/d7r-LLC/saga-standard)
- [ghost-spec](https://github.com/d7r-LLC/ghost-spec)
- [blueprint](https://github.com/d7r-LLC/blueprint)

Each spec repo has its own `CONTRIBUTING.md` and RFC process.

## Adding a specification

A new spec enters the index by pull request touching all three surfaces
(registry, site, README) in one change, once the spec repository exists and has a
LICENSE, a README, and a normative document under `spec/`.
