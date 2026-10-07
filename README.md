# SPIFFE `.project`

`.project` (dot-project) is a CNCF initiative to centralize and automate metadata management for all CNCF projects.
This repository holds the canonical metadata for the CNCF projects maintained in the `spiffe` organization ([SPIFFE](https://spiffe.io/) and [SPIRE](https://spiffe.io/spire/)), and is maintained by the CNCF automation tooling.

## What's in this repo

| File | Purpose |
|------|---------|
| `org.yaml` | Index of the CNCF projects maintained in this organization |
| `<project>/project.yaml` | Canonical metadata for one project (name, maturity, repositories, governance links, …) |
| `<project>/maintainers.yaml` | Maintainer and reviewer roster for one project |
| `CODEOWNERS` | Ensures PRs to this repo require maintainer approval |
| `.github/workflows/validate.yaml` | CI — validates `project.yaml` and `maintainers.yaml` on every PR |
| `.github/workflows/update-landscape.yml` | Automatically proposes landscape updates when `project.yaml` changes |

## Projects in this repository

This GitHub organization maintains more than one CNCF project. Each is a
separate project from CNCF's point of view — its own maturity, its own
landscape entry — so each owns a directory with its own metadata, and
`org.yaml` indexes them:

| Project | Directory |
|---------|-----------|
| SPIFFE | `spiffe/` |
| SPIRE | `spire/` |

Add or remove a project by editing `org.yaml` and its directory together;
validation fails if the two disagree. See the
[repository layouts reference](https://github.com/cncf/automation/tree/main/utilities/dot-project#repository-layouts).

## Keeping metadata up to date

Open a pull request against this repository to update any metadata field.
The validate workflow will check schema correctness and block merge if validation fails.

> **Note:** This repository was bootstrapped automatically from public sources (CNCF landscape, CLOMonitor, GitHub governance files).
> Some fields are best-effort guesses marked with `# TODO: AUTO-DETECTED — please verify` in the YAML files and should be confirmed by the project maintainers.

## Resources

- [`.project` documentation](https://github.com/cncf/automation/tree/main/utilities/dot-project)
- [Schema reference](https://github.com/cncf/automation/blob/main/utilities/dot-project/SCHEMA.md)
- [CNCF Automation repository](https://github.com/cncf/automation)
