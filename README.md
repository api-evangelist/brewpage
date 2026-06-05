# BrewPage (brewpage)

BrewPage is a free, no-registration instant hosting service for HTML pages, Markdown documents, AI-agent artifacts, files, and multi-file static sites. It also offers a namespaced key-value store and a JSON document store. The REST API returns short, shareable HTTPS links (https://brewpage.app/{ns}/{id}) and an owner token used to update or delete content in place. BrewPage is designed to be AI-agent friendly: it provides an MCP server (brewpage-mcp), a Claude Code skill (brewdoc:publish), and a llms.txt manifest, and it requires a self-identifying User-Agent header on every request.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/brewpage/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/brewpage/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Hosting
- Markdown
- HTML
- AI Artifacts
- File Hosting
- Developer Tools

## Timestamps

- **Created:** 2026-05-16
- **Modified:** 2026-05-19

## APIs

### BrewPage API

The BrewPage REST API. Publish HTML, Markdown, files, and multi-file sites; store key-value pairs and JSON documents; browse the public gallery; check ownership; and submit abuse reports. Endpoints live under /api/ and short links live at /{ns}/{id}. Identical functionality is also available at brewdata.app.

- **Human URL:** [https://brewpage.app/api](https://brewpage.app/api)
- **Base URL:** `https://brewpage.app`

#### Tags

- Hosting
- HTML
- Markdown
- AI Artifacts
- File Hosting
- Developer Tools

#### Properties

- [Documentation](https://brewpage.app/api)
- [API Reference](https://kochetkov-ma.github.io/brewpage-openapi/)
- [OpenAPI](openapi/brewpage-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/brewpage.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/brewpage.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](https://brewpage.app/llms-full.txt)
- [JSON Schema](json-schema/brewpage-html-page-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/brewpage-file-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/brewpage-kv-store-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/brewpage-json-document-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/brewpage-site-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/brewpage-html-page-structure.json)
- [JSON Structure](json-structure/brewpage-kv-store-structure.json)
- [Example](examples/brewpage-create-html-example.json)
- [Example](examples/brewpage-create-markdown-example.json)
- [Example](examples/brewpage-upload-file-example.json)
- [Example](examples/brewpage-upload-site-example.json)
- [Example](examples/brewpage-upsert-kv-example.json)

## Common Properties

- [Documentation](https://brewpage.app/api)
- [API Reference](https://kochetkov-ma.github.io/brewpage-openapi/)
- [Portal](https://brewpage.app/)
- [Getting Started](https://brewpage.app/llms.txt)
- [Quickstart](https://brewpage.app/llms.txt)
- [Authentication](https://brewpage.app/llms-full.txt)
- [SDK](https://www.npmjs.com/package/brewpage-mcp)
- [Plans](plans/brewpage-plans-pricing.yml)
- [Rate Limits](rate-limits/brewpage-rate-limits.yml)
- [Fin Ops](finops/brewpage-finops.yml)
- [Integrations](undefined)
- [Spectral Rules](rules/brewpage-rules.yml)
- [Vocabulary](vocabulary/brewpage-vocabulary.yml)
- [JSON-LD](json-ld/brewpage-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Features](undefined)
- [Use Cases](undefined)
- [Solutions](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
