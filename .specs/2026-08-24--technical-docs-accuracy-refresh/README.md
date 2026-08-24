# Technical Documentation Accuracy Refresh

| Field            | Value                                    |
| ---------------- | ---------------------------------------- |
| **Status**       | implemented                              |
| **Branch**       | `docs/technical-accuracy-refresh-clean`  |
| **Created**      | 2026-08-24                               |
| **Last Updated** | 2026-08-24                               |

## Scope

Port the verified Content API reference value from candidate commit `7cb9b84c90992863e6c3c06d0901e737ef2da245` onto current docs main, then correct affected SDK, schema, locale-fallback, and CLI guidance against current implementation.

## Non-Scope

- Builder, SDK, Pilot, or other product-code changes.
- Studio/end-user guides, Hydrogen theme guides, changelog content, media, and the external site-wide audit inventory.
- Publishing, deployment, PR creation, or external-state changes.

## Authoritative Evidence

- Builder `4d1b515e4f843a2e8d18110055517df166f7a9bd`: Content API routes and helpers under `app/routes/api/{v1/content,public/v1}/` and `app/backend/content-api/`.
- Weaverse SDK `c6c680d60b5760e8612f776c68f03c3ccde540d0`: Hydrogen/schema types, schema normalization, `createSchema`, CLI behavior, and the generated public API report.
- Published packages: `@weaverse/hydrogen@5.20.2` and `@weaverse/cli@5.6.4` from the npm registry.
- Pilot `2f8a10fdb8e8bf38728ee236ebb6f79d396538fe`: component registration and Hydrogen router-context patterns.
- Candidate `7cb9b84c90992863e6c3c06d0901e737ef2da245` is source material only, not authority.

## Acceptance Criteria

- [x] New Content API pages describe current request, selector, pagination, and snapshot behavior without unsupported guarantees.
- [x] Get-page fallback order and schema-default resolution match Builder source.
- [x] SDK schema docs match current public types and development-only warning validation.
- [x] CLI guidance explicitly starts development when the command does not guarantee it.
- [x] Every added navigation entry resolves once to an MDX file.
- [x] Mintlify links and changed routes pass local validation and preview smoke checks.
- [x] The final diff contains no protected-lane or product-repository changes.

## Implemented State

Four Content API reference pages are added and registered once. Existing get-page, overview, SDK types/schema, installation, and quickstart pages now match the verified Builder, SDK, and CLI behavior. Already-correct selected-option, explicit-props, installation template/component registration, and Pilot context guidance remains unchanged. JSON/navigation checks, `mint broken-links`, and HTTP 200 preview probes for all ten changed MDX routes passed.
