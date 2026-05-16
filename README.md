# BrewPage (brewpage)
BrewPage is a free, no-registration instant hosting service for HTML pages, Markdown documents, AI-agent artifacts, files, and multi-file static sites. It also offers a namespaced key-value store and a JSON document store. The REST API returns short, shareable HTTPS links (https://brewpage.app/{ns}/{id}) and an owner token used to update or delete content in place. BrewPage is designed to be AI-agent friendly: it provides an MCP server (brewpage-mcp), a Claude Code skill (brewdoc:publish), and a llms.txt manifest, and it requires a self-identifying User-Agent header on every request.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/brewpage/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Hosting, Markdown, HTML, AI Artifacts, File Hosting, Developer Tools

## Timestamps

- **Created:** 2026-05-16
- **Modified:** 2026-05-16

## APIs

### BrewPage API
The BrewPage REST API. Publish HTML, Markdown, files, and multi-file sites; store key-value pairs and JSON documents; browse the public gallery; check ownership; and submit abuse reports. Endpoints live under /api/ and short links live at /{ns}/{id}. Identical functionality is also available at brewdata.app.

**Human URL:** [https://brewpage.app/api](https://brewpage.app/api)

#### Tags:

 - Hosting, HTML, Markdown, AI Artifacts, File Hosting, Developer Tools

#### Properties

- [Documentation](https://brewpage.app/api)
- [APIReference](https://kochetkov-ma.github.io/brewpage-openapi/)
- [OpenAPI](openapi/brewpage-openapi.yml)
- [Authentication](https://brewpage.app/llms-full.txt)
- [JSONSchema](json-schema/brewpage-html-page-schema.json)
- [JSONSchema](json-schema/brewpage-file-schema.json)
- [JSONSchema](json-schema/brewpage-kv-store-schema.json)
- [JSONSchema](json-schema/brewpage-json-document-schema.json)
- [JSONSchema](json-schema/brewpage-site-schema.json)
- [JSONStructure](json-structure/brewpage-html-page-structure.json)
- [JSONStructure](json-structure/brewpage-kv-store-structure.json)
- [Example](examples/brewpage-create-html-example.json)
- [Example](examples/brewpage-create-markdown-example.json)
- [Example](examples/brewpage-upload-file-example.json)
- [Example](examples/brewpage-upload-site-example.json)
- [Example](examples/brewpage-upsert-kv-example.json)

## Common Properties

- [Documentation](https://brewpage.app/api)
- [APIReference](https://kochetkov-ma.github.io/brewpage-openapi/)
- [Portal](https://brewpage.app/)
- [GettingStarted](https://brewpage.app/llms.txt)
- [Quickstart](https://brewpage.app/llms.txt)
- [Authentication](https://brewpage.app/llms-full.txt)
- [SDK](https://www.npmjs.com/package/brewpage-mcp)
- [Plans](plans/brewpage-plans-pricing.yml)
- [RateLimits](rate-limits/brewpage-rate-limits.yml)
- [FinOps](finops/brewpage-finops.yml)
- [SpectralRules](rules/brewpage-rules.yml)
- [Vocabulary](vocabulary/brewpage-vocabulary.yml)
- [NaftikoCapability](capabilities/agent-artifact-publishing.yaml)
- [NaftikoCapability](capabilities/shared/brewpage.yaml)
- [JSON-LD](json-ld/brewpage-context.jsonld)

## Features

| Name | Description |
|------|-------------|
| Instant HTML Hosting | POST raw HTML or a JSON body to /api/html and receive a 10-char short URL at /{ns}/{id} with no signup. |
| Markdown Rendering | Pass `format=markdown` to publish Markdown that BrewPage renders to styled HTML at view time. |
| Multi-File Site Hosting | Upload a ZIP archive or files+paths multipart to /api/sites; entry point auto-detected (index.html preferred); 20 MB / 100 files / 5 MB each. |
| File Hosting | Upload binary or text files via /api/files (5 MB max). Images, PDFs, video, and audio display inline; ?dl=1 forces download. |
| Key-Value Store | 1000-key namespaced KV stores via /api/kv with per-key PUT/GET/DELETE and per-store enumeration. |
| JSON Document Store | 10,000-document collections via /api/json with PUT-in-place semantics on stable short URLs. |
| Update In Place | PUT to /api/html, /api/json, and /api/kv replaces content while keeping the short URL — agents can iterate without breaking shared links. |
| Owner Token Grouping | Save the `ownerToken` returned at creation and reuse it via `X-Owner-Token` to group resources under one owner and scope list endpoints. |
| Password Protection | Set `X-Password` (min 4 chars) at creation to require the same header (or `?p=...`) for reads; passworded items are excluded from the gallery and sitemap. |
| Public Gallery | GET /api/gallery surfaces content posted to the default `public` namespace without a password — searchable, social-bot friendly, OG-image generated. |
| OpenGraph Preview Images | Per-content 1200×630 PNG at /preview/{ns}/{id}.png plus an /preview-html stub for social media unfurlers. |
| Short Link Resolver | GET /{ns}/{id} returns the hosted content; GET /{ns}/{id}/{sub} resolves sub-paths inside multi-file sites. |
| Idempotent Owner Re-POST | A byte-identical POST /api/html to `public/` within 24h returns the existing id (X-Existing-Resource header set) so retries do not duplicate gallery entries. |
| Abuse Reports | POST /api/reports lets readers report inappropriate or harmful content for moderation. |
| Random Namespace Suggestion | GET /api/namespace/random returns a fresh, collision-free kebab-case namespace suggestion. |
| Platform Stats | GET /api/stats exposes platform-wide usage statistics; GET /api/sitemap.xml exposes a dynamic sitemap of public content. |
| AI-Agent Friendly | llms.txt and llms-full.txt manifests, an MCP server, a Claude Code skill, and required identifying User-Agent headers make BrewPage first-class for autonomous agents. |

## Use Cases

| Name | Description |
|------|-------------|
| Share AI-Agent Output | Drop a Markdown report, generated HTML page, or JSON artifact and share a short URL with a teammate or end user. |
| Iterate On A Stable Link | Use PUT to refine content at the same short URL across multiple agent iterations without breaking previously shared links. |
| Stand Up A One-Off Microsite | Upload a ZIP of a static site (docs, demo, status page) and get a 30-day-max hosted URL with relative links between files. |
| Ephemeral File Drop | Send a PDF, image, or archive (≤5 MB) to a recipient who shouldn't need to sign up — URL expires automatically. |
| Scratch KV Storage For Agents | Use /api/kv as a free, server-side scratchpad for feature flags, session state, or memoized tool outputs (≤1000 keys per store). |
| Public Knowledge Drop | Post to the default `public` namespace and let the gallery + sitemap + OG image expose your content to search engines and social. |
| Password-Gated Share | Apply X-Password to a hosted page or file for lightweight access control without user accounts. |

## Integrations

| Name | Description |
|------|-------------|
| Model Context Protocol (MCP) | Official MCP server `brewpage-mcp` exposes BrewPage to any LLM/agent (Claude, Codex, Gemini, Cursor) via the Model Context Protocol. |
| Claude Code | Claude Code skill `brewdoc:publish` lets users publish from inside Claude Code via a slash command (claude-brewcode marketplace). |
| IndexNow | BrewPage submits public content to IndexNow for search engine discovery; PUT-based republish is recommended to preserve quota. |
| OpenGraph / Social Bots | Every short URL exposes `/preview/{ns}/{id}.png` (1200×630) and a `/preview-html/{ns}/{id}` OG stub for link unfurling. |
| Prism.js | Client-side syntax highlighting for known code/data file previews (JSON, XML, SVG, HTML, CSS, JS, TS, YAML, TOML, Markdown). |
| llms.txt | BrewPage publishes a /llms.txt and /llms-full.txt manifest for LLM-friendly discovery of the API surface. |

## Solutions

| Name | Description |
|------|-------------|
| Hosted Web Page | Free HTML/Markdown publishing with short URL, OG images, and password gating. |
| Hosted Files And Sites | 5 MB files and 20 MB multi-file sites with TTL up to 30 days. |
| Agent State And Documents | KV stores (1000 keys) and JSON collections (10,000 docs) for stateful agent workflows. |
| AI-Agent Integration | MCP server, Claude Code skill, llms.txt manifests, and identifying User-Agent contract. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [BrewPage API](openapi/brewpage-openapi.yml)

### JSON Schema

- [BrewPage HTML Page Schema](json-schema/brewpage-html-page-schema.json)
- [BrewPage File Schema](json-schema/brewpage-file-schema.json)
- [BrewPage KV Store Schema](json-schema/brewpage-kv-store-schema.json)
- [BrewPage JSON Document Schema](json-schema/brewpage-json-document-schema.json)
- [BrewPage Site Schema](json-schema/brewpage-site-schema.json)

### JSON Structure

- [BrewPage HTML Page Structure](json-structure/brewpage-html-page-structure.json)
- [BrewPage KV Store Structure](json-structure/brewpage-kv-store-structure.json)

### JSON-LD

- [BrewPage Context](json-ld/brewpage-context.jsonld)

### Examples

- [Create HTML Example](examples/brewpage-create-html-example.json)
- [Create Markdown Example](examples/brewpage-create-markdown-example.json)
- [Upload File Example](examples/brewpage-upload-file-example.json)
- [Upload Site Example](examples/brewpage-upload-site-example.json)
- [Upsert KV Example](examples/brewpage-upsert-kv-example.json)

### Plans, Rate Limits, FinOps

- [Plans & Pricing](plans/brewpage-plans-pricing.yml)
- [Rate Limits](rate-limits/brewpage-rate-limits.yml)
- [FinOps](finops/brewpage-finops.yml)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [BrewPage Hosting](capabilities/shared/brewpage.yaml) — REST adapter for the full BrewPage API surface (HTML, Files, Sites, KV, JSON, Discovery, Reports)

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Agent Artifact Publishing](capabilities/agent-artifact-publishing.yaml) | brewpage | 11 | AI Agent / Developer / Content Author |

## Vocabulary

- [BrewPage Vocabulary](vocabulary/brewpage-vocabulary.yml) — Unified taxonomy mapping 14 resources, 12 actions, 6 capability goals, and the BrewPage primitives (namespace, shortId, ownerToken, ttl, password, userAgent)

## Rules

- [BrewPage Spectral Rules](rules/brewpage-rules.yml) — 21 rules enforcing BrewPage title, server, path, operation, parameter, schema, response, and TTL conventions

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
