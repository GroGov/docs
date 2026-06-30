# PC_PartnerDocs

Mintlify documentation site for the **Partner Payments API** (`/api/partner/v1/*`).

## Run locally

```bash
cd PC_PartnerDocs
mint dev             # serves on http://localhost:3000
```

## Check for broken links

```bash
mint broken-links
```

## Structure

- `docs.json` — site config + navigation (current Mintlify `docs.json` schema).
- `openapi.json` — copy of `PC_Backend/src/docs/partner-payments-openapi.json`,
  powering the auto-generated **API Reference** tab. Re-copy when the source spec changes:
  `cp ../PC_Backend/src/docs/partner-payments-openapi.json openapi.json`
  **Local edit to preserve on re-copy:** the `servers` list is intentionally
  trimmed to staging only (`https://apistagepc.grogov.us`) so the API Reference
  playground targets the same environment the guides use. After re-copying, remove
  the local/dev/prod server entries again (or the playground will offer
  environments the docs don't document).
- `guides/*.mdx` — hand-written conceptual guides.

## Source of truth

The OpenAPI spec and the partner Playwright suite
(`PC_Testing/tests/partner/F-300..F-306`) are authoritative for request/response
shapes and error codes. The `docs/plans/partner-api/discovery.md` doc is background
only — its draft error codes are obsolete.
