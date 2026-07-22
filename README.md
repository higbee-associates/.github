# Higbee Associates — Organization defaults

This is the organization-wide [`.github`](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file) repository for **higbee-associates**.

Files here are used as **defaults** for every repository in the organization that does **not** define its own copy of the same file.

## What this repository provides

| File / path | Purpose |
| --- | --- |
| [`profile/README.md`](./profile/README.md) | Organization profile README (shown on the org Overview) |
| [`CONTRIBUTING.md`](./CONTRIBUTING.md) | How to contribute across Higbee repositories |
| [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md) | Expected standards of collaboration |
| [`SECURITY.md`](./SECURITY.md) | How to report security vulnerabilities |
| [`SUPPORT.md`](./SUPPORT.md) | Where to get help |
| [`.github/ISSUE_TEMPLATE/`](./.github/ISSUE_TEMPLATE/) | Default issue forms and chooser config |
| [`.github/pull_request_template.md`](./.github/pull_request_template.md) | Default pull request checklist |

## Precedence

For a given repository, GitHub looks for a community health file in this order:

1. The repository’s `.github/` folder
2. The repository root
3. The repository’s `docs/` folder

If none of those exist, GitHub falls back to this organization `.github` repository (same search order).

**Important:** If a repository has *any* files in its own `.github/ISSUE_TEMPLATE/` folder, the organization defaults from this repo are **not** used for that repository.

## Requirements

- This repository **must remain public** for organization-wide issue and pull request templates to apply.
- If an issue template assigns a label, that label must exist in **both** this repository and each target repository.

## Overriding defaults

To customize for a single repository, add the same filename (or your own `.github/ISSUE_TEMPLATE/` contents) in that repository. Repository-local files always win.
