# Contributing to HACA IT projects

These guidelines apply to repositories under the **higbee-associates** organization (HACA IT) unless a repository provides its own `CONTRIBUTING.md`.

We build software for **Higbee & Associates Consumer Advocacy (HACA)** and related platforms. We hold a high bar: clear design patterns, typed code, tests that protect behavior, documented APIs, and disciplined releases.

When a repository documents a stricter rule (for example Attorney Vendor Portal’s `STYLE_GUIDE.md` or `docs/RELEASE.md`), **follow that repository’s docs**.

---

## Before you start

1. Confirm access to the repository and required environments (Docker, AWS, shared `.env` from the team — never invent secrets).
2. Read the repo `README.md`, and when present: `STYLE_GUIDE.md`, `docs/`, `ONBOARDING.md`, and ADRs.
3. Search existing issues and pull requests to avoid duplicates.
4. For non-trivial work, open an issue (or align with the team) before a large implementation.

---

## Engineering standards

We expect production-quality work across stacks (Laravel/PHP, Next.js/TypeScript, FastAPI/Python, AWS).

### Design and architecture

- Prefer **clear layering** over ad-hoc logic in controllers, route handlers, or UI components.
  - **Laravel:** thin `final` controllers → **Services** (and repositories where used); Form Requests for validation; Gates/Policies for authorization; Sanctum (or the repo’s auth model) for APIs.
  - **Next.js / React:** typed components; shared design-system / shadcn patterns where the repo uses them; API access through the project’s client helpers (not one-off `fetch` sprawl).
  - **Python agents / services:** clean architecture (application / domain / infrastructure); explicit schemas (e.g. Pydantic); dependency injection.
- Apply **SOLID** and prefer iteration/reuse over copy-paste.
- Match existing module patterns before inventing a new one. When touching legacy code, migrate toward current standards where practical.
- **Never rely on the frontend alone for access control.** Enforce authorization on the server.

### Code quality

| Area | Expectation |
| --- | --- |
| Typing | PHP: `declare(strict_types=1)` and typed properties/returns (PHP 8.3+ where required). TypeScript: strict mode; avoid `any`. Python: typed public APIs and models. |
| Style | Follow the repo formatter (e.g. Laravel Pint / PSR-12, ESLint/Prettier, Ruff/Black as configured). |
| Naming | Descriptive, consistent with the codebase (PascalCase types, camelCase methods/vars in PHP/TS unless the repo uses another convention). |
| Scope | Keep PRs focused. Do not mix unrelated refactors with feature work. |
| Secrets | Never commit `.env`, credentials, tokens, or real client data. Do not log secrets. |

### Testing

- Treat tests as a **stability contract**. If tests fail after your change, **fix the code** (or deliberately update tests when the contract itself changes — and say so in the PR).
- Add or update tests for behavior you change: happy path **and** important error/edge paths.
- Prefer the repo’s test stack (PHPUnit/ParaTest, Vitest/RTL/Playwright, pytest, etc.).
- Never point tests at production databases or live production systems.

### Documentation

When behavior, APIs, env vars, or operator workflows change, update the matching docs in the same PR (`docs/`, API notes, README, ADRs). Silent behavior changes without docs are not acceptable for shared platforms.

---

## Branching

Create branches from the repository’s integration branch (often `develop` / `dev`, or `staging` / `main` — check the README).

Preferred names:

| Prefix | Use |
| --- | --- |
| `feat/…` or `feature/…` | New capability |
| `fix/…` | Bug fix |
| `chore/…` | Tooling, deps, non-user-facing maintenance |
| `docs/…` | Documentation only |
| `test/…` | Test-only work |
| `ci/…` | CI/CD |

Include a short description (and ticket/issue id when useful), e.g. `fix/1234-sse-timeout`.

---

## Commits (Conventional Commits)

Use **[Conventional Commits](https://www.conventionalcommits.org/)** on every commit. This is **required** for repositories that use semantic-release (including Attorney Vendor Portal). It is the **preferred** standard for all HACA IT repos.

```
<type>(optional-scope): <short summary>

[optional body]

[optional footer]
```

| Type | Meaning | Version impact (when semantic-release is enabled) |
| --- | --- | --- |
| `feat:` | New feature | Minor (`1.1.0` → `1.2.0`) |
| `fix:` / `perf:` | Bug fix / performance | Patch (`1.1.0` → `1.1.1`) |
| `feat!:` or `BREAKING CHANGE:` footer | Breaking change | Major (`1.1.0` → `2.0.0`) |
| `docs:`, `chore:`, `test:`, `ci:`, `refactor:`, `style:`, `build:` | Non-releasable (unless breaking) | No bump |

Examples:

```bash
feat(offers): add multi offer ID search
fix(communications): restrict CA Messaging API to Higbee roles
docs: update release instructions
feat(api)!: redesign authentication

BREAKING CHANGE: Authentication now requires OAuth2 instead of API keys
```

Rules:

- Summaries explain **what/why**, not noise.
- One logical change per commit when practical.
- **Commit author must be the human developer** configured in git — never an AI/bot identity.
- Do not commit secrets.

---

## Releases and promotion (Attorney Vendor Portal model)

AVP backend and frontend document the team’s release standard in `docs/RELEASE.md`. Other repos may use a subset (deploy-only on `staging`/`main`). When a repo has Release automation, follow that repo’s guide.

### TL;DR (semantic-release repos)

1. Use Conventional Commits on every commit.
2. Open a **PR → `staging`** for beta; after validation, **PR → `main`** for production.
3. On merge, GitHub Actions **Release** runs automatically. **Do not bump versions by hand.**
4. Find versions under **GitHub → Releases** and git tags `v*`.

### Branch → version (AVP)

| Branch | Environment | Version example |
| --- | --- | --- |
| `staging` | Pre-prod / beta | `1.2.0-beta.1` |
| `main` | Production | `1.2.0` |
| `dev` / `develop` | Dev only | No release |

Deploy (e.g. ECS) and Release are separate. Merges still deploy as configured; Release tags, changelog, and version files. Release bot commits use `chore(release): … [skip ci]` so they do **not** re-trigger deploy loops.

Frontend and backend (and other apps) keep **independent** version lines.

### Day-to-day workflow

**Bug fix / patch (preferred):**

```text
fix/<issue>-short-name
        │
        ├─► PR → staging  → merge → beta tag (e.g. 1.2.1-beta.1)
        │
        └─► PR → main     → merge → stable tag (e.g. 1.2.1)
```

Use the **same fix branch** into both `staging` and `main`. Do **not** open a blanket `staging` → `main` promotion for a single bug fix (that can drag unrelated staging work into production).

**Larger features:**

```text
feat/...  →  PR → staging  → validate  →  PR → main
```

1. Keep commits conventional.
2. Merge to **`staging`** → confirm Actions → **Release** created `v*-beta.N` (when enabled).
3. Open **PR → `main`** from the **same branch** when ready; follow the repo’s review rules (e.g. no self-merge to `main` where that policy applies).
4. After merge to **`main`**, confirm a stable `vX.Y.Z` when Release is enabled.

**Do not** cherry-pick `chore(release): …-beta.*` commits onto `main`. Stable versions are created by the Release workflow on `main`.

### If Release fails

1. Open the failed run under **Actions → Release**.
2. For transient GitHub errors, **Re-run failed jobs**.
3. Do not invent tags manually unless the team agrees on a recovery plan.

### Other repositories

| Area | Typical branches | Notes |
| --- | --- | --- |
| Compliance CRM | `staging`, `main` | Deploy-focused; still use Conventional Commits and PR review |
| Compliance AI / agent | `develop` / `staging`, `main` | Staging vs production deploys; follow each repo’s workflows |
| DIY | `staging`, `main` | CI on PRs/pushes; ADRs for architecture decisions |
| HAPI (`haca_mssql_api`) | `staging`, `main` | ECS deploy runbooks in `docs/` |

Always verify the target branch and environment in that repository’s README and workflows before merging.

---

## Pull requests

1. Target the correct branch for the change (`staging` for pre-prod, `main` for production promotion, etc.).
2. Fill out the pull request template completely (summary, test plan, checklist).
3. Link related issues.
4. Ensure CI is green; request review from CODEOWNERS / the owning team.
5. Include screenshots or API examples when UI or contracts change.
6. Address review feedback; resolve conversations when done.

PR expectations:

- [ ] Follows repository style guide / architecture patterns  
- [ ] Tests added or updated when appropriate  
- [ ] Docs updated when behavior or APIs changed  
- [ ] No secrets or sensitive data  
- [ ] Conventional commit history suitable for release notes  

---

## Issues

Use org issue templates when the repository does not define its own:

- **Bug report** — unexpected behavior with reproduction steps  
- **Feature request** — new capability or product improvement  
- **Task** — tracked work that is neither a bug nor a feature  

Include environment (local / staging / production), service name, and enough context for someone else to reproduce — without secrets or client PII.

---

## Security

Do **not** open public issues for security vulnerabilities. Follow [`SECURITY.md`](./SECURITY.md).

Additional expectations:

- Least privilege for tokens, IAM, and DB credentials  
- No production data in local fixtures unless scrubbed and approved  
- Validate and authorize on the server; sanitize outputs  

---

## Local development

- Prefer **Docker** (or the repo’s documented path) so environments match CI/deploy images.
- Obtain `.env` / secrets from the team; use `.env.example` as the contract for required variables.
- Do not commit machine-specific paths, personal tokens, or debug backdoors.

---

## Questions

See [`SUPPORT.md`](./SUPPORT.md). For release mechanics on AVP, start with that repo’s `docs/RELEASE.md` and `docs/development/semantic-release.md`.
