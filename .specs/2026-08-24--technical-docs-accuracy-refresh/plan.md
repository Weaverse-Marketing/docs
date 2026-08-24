# Implementation Plan — Technical Documentation Accuracy Refresh

## Problem

The stale candidate contains useful Content API references, but several claims conflict with current Builder, SDK, CLI, and Pilot behavior. Current main also retains inaccurate locale-fallback, schema-validation, and CLI startup wording.

## Decision

Use current implementation and published package state as authority. Port only four verified Content API reference pages, link them from the existing Content API navigation and overview, and make narrow corrections to existing technical pages. Leave already-correct selected-option, explicit-props, installation template/component registration, and context guidance unchanged.

## Files

| File | Change |
| --- | --- |
| `content-api/delete-pages.mdx` | Add accurate selector precedence and deletion safety. |
| `content-api/public-custom-pages.mdx` | Add `cursor`/`nextCursor` pagination and publication-state warning. |
| `content-api/update-project.mdx` | Document the supported name-only update. |
| `content-api/update-theme-settings.mdx` | Document shallow merge and best-effort deduplicated snapshots. |
| `content-api/get-page.mdx` | Add schema-default resolution and exact fallback order. |
| `content-api/overview.mdx` | Register new references and remove unconditional snapshot/live-timing claims. |
| `api-reference/types.mdx` | Clarify `createSchema` typing and asynchronous warning validation. |
| `development-guide/component-schema.mdx` | Replace build-time/throwing validation claims and mark `settings` optional. |
| `intro/quickstart.mdx` | Make `npm run dev` the deterministic CLI next step. |
| `getting-started/installation.mdx` | Clarify interactive prompts, non-interactive `--dev`, and the deterministic `npm run dev` step. |
| `docs.json` | Add the four new Content API pages once. |
| `.specs/2026-08-24--technical-docs-accuracy-refresh/{README.md,plan.md}` | Record scope, evidence, acceptance, and final state. |

## Validation

1. Inspect the full final diff and all changed files.
2. Run `git diff --check` and parse `docs.json` with Python stdlib.
3. Verify every navigation page resolves to a file, with no duplicate or unreachable new entry.
4. Compare `mint broken-links` with the clean-base result.
5. Run `mint dev --no-open`, request every changed MDX route, and confirm HTTP 200 with no compile/render error.
6. Scan added lines for secrets and prohibited internal artifacts.
7. Confirm product repositories and protected documentation lanes are unchanged.
8. Complete correctness and scope self-reviews before the single local commit.

## Out of Scope

- Product fixes for mixed delete selectors, public custom-page publication filtering, or snapshot guarantees.
- Changes to already-correct selected-product-option naming, `InferInput` removal, installation templates/component registration, or Pilot context guidance.
- New tooling, dependencies, generated artifacts, publishing, deployment, PRs, or external updates.
