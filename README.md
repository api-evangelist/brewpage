# BrewPage (brewpage)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
