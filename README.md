# d7r Open Source

**The index of d7r's open specifications.**

This repository is the source for [d7r.io](https://d7r.io): the front door to the d7r
open source initiative and the canonical index of its specifications, repositories, and
published sites.

**Status: everything indexed here is a draft.** Nothing in any of these repositories is
adopted until it lands as a decision record in its own repo.

## The specifications

Two families. The agent stack governs agents as digital workers; the knowledge family
governs the brains they work with. SAGA moves an agent. Blueprint moves a thought.

### The agent stack

| Spec | Repository | Site | Answers | License |
|---|---|---|---|---|
| Agent Bill of Rights (ABR) | [agent-rights](https://github.com/d7r-LLC/agent-rights) | [agent-rights.org](https://agent-rights.org) | What agents deserve | CC BY 4.0 |
| DERP | [derp-spec](https://github.com/d7r-LLC/derp-spec) | [derp-spec.dev](https://derp-spec.dev) | What the runtime must provide | CC BY 4.0 |
| SAGA | [saga-standard](https://github.com/d7r-LLC/saga-standard) | [saga-standard.dev](https://saga-standard.dev) | How an agent is represented | Apache 2.0 |
| GHOST | [ghost-spec](https://github.com/d7r-LLC/ghost-spec) | [ghost-spec.dev](https://ghost-spec.dev) | How a person is projected as counsel | CC BY 4.0 |

```
Agent Bill of Rights (ABR)   policy:   what agents deserve
        |
      DERP                   standard: what the runtime must provide
        |
      SAGA                   format:   how an agent is represented
        |
      GHOST                  counsel:  how a person is projected as counsel
```

### The knowledge family

| Spec | Repository | Site | Answers | License |
|---|---|---|---|---|
| Blueprint | [blueprint](https://github.com/d7r-LLC/blueprint) | [blueprint-spec.dev](https://blueprint-spec.dev) | How knowledge is held, governed, and exchanged | Apache 2.0 |

Blueprint is a family of seven documents in one repository: BLUEPRINT (a single brain,
in ten layers), POLARIS (purpose and refusals), DEFER (delegated authority), SPEAK
(brain-to-brain exchange), CONFIDE (inference governance), TRACE (tooling residue), and
RETAIN (agent brains and what an agent keeps).

## Machine-readable registry

The same index, as data: [`site/registry/specs.json`](site/registry/specs.json), served
at [d7r.io/registry/specs.json](https://d7r.io/registry/specs.json). Tools that need to
enumerate the specifications should read the registry, not scrape this README.

## This repository

```
site/                    The static site served at d7r.io (GitHub Pages)
site/registry/specs.json The machine-readable spec registry
.github/workflows/       Pages deployment
```

The site is static HTML with no build step: edit `site/`, push to `main`, and the
Pages workflow deploys it.

## Contributing

Spec-level issues and RFCs belong in the individual spec repositories. Issues with the
index itself, dead links, registry drift, or site defects, belong here. See
[CONTRIBUTING.md](CONTRIBUTING.md).

---

Copyright (c) 2026 d7r LLC. Text and site content licensed [CC BY 4.0](LICENSE).
Contact: hello@d7r.io
