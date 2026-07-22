# Contributing to Higbee Associates projects

Thanks for contributing. These guidelines apply to repositories under the **higbee-associates** organization unless a repository provides its own `CONTRIBUTING.md`.

## Before you start

1. Confirm you have access to the target repository and any required environments.
2. Search existing issues and pull requests to avoid duplicates.
3. For larger changes, open an issue first so the approach can be agreed on.

## Branching

- Create branches from the repository’s default development branch (often `develop` or `main` — check the repo README).
- Prefer short, descriptive branch names, for example:
  - `feature/short-description`
  - `fix/short-description`
  - `chore/short-description`

## Commits

- Write clear commit messages that explain **why** the change exists.
- Keep commits focused; avoid mixing unrelated refactors with feature work.
- Do not commit secrets, credentials, or real `.env` files.

## Pull requests

1. Open a PR against the branch specified by the repository (see its README or PR template).
2. Fill out the pull request template completely.
3. Link related issues when applicable.
4. Ensure CI passes and request review from the appropriate CODEOWNERS or team.
5. Address review feedback promptly; mark conversations resolved when done.

## Issues

Use the provided issue templates when available:

- **Bug report** — unexpected behavior with reproduction steps
- **Feature request** — new capability or product improvement
- **Task** — tracked work that is neither a bug nor a feature

Include enough context for someone unfamiliar with your environment to act on the issue.

## Code standards

Follow the standards documented in each repository (for example `STYLE_GUIDE.md`, `README.md`, and `docs/`). When in doubt, match existing patterns in the same module.

## Security

Do **not** open public issues for security vulnerabilities. Follow [`SECURITY.md`](./SECURITY.md).

## Questions

See [`SUPPORT.md`](./SUPPORT.md) for help channels.
