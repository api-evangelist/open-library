# Open Library

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

Open Library offers a suite of APIs to help developers get up and running with its data. This includes RESTful APIs that make Open Library data available in JSON, YAML, and RDF/XML formats, plus a Search Inside full-text search service, cover image endpoints, and read-protocol library lookup APIs. Most resources also expose machine-readable representations by appending .json, .yml, or .rdf to any Open Library URL.

**Areas:** Authors · Books · Catalog · Covers · Library · Open Data · Reading Lists · Search · Subjects

## Open Library on APIs.io

Everything profiled for Open Library is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/open-library/](https://apis.io/providers/open-library/)** — or go straight to one of the APIs or properties below.

### APIs (13)

- [Open Library Search Inside API](https://apis.io/apis/open-library/open-library-search-inside-api/) — Full-text search across the millions of digitized books in the Internet Archive's collection, returning matching passages and book identifiers.
- [Open Library Covers API](https://apis.io/apis/open-library/open-library-covers-api/) — Retrieve book and author cover images by Open Library ID, ISBN, OCLC, LCCN, or Goodreads ID, in small, medium, and large sizes.
- [Open Library My Books API](https://apis.io/apis/open-library/open-library-mybooks-api/) — Access a patron's public reading log: Want to Read, Currently Reading, and Already Read shelves for a given Open Library account.
- [Open Library Recent Changes API](https://apis.io/apis/open-library/open-library-recent-changes-api/) — Stream recent edits across the Open Library catalog including works, editions, authors, lists, and subjects, with filtering by kind and time range.
- [Open Library Read API](https://apis.io/apis/open-library/open-library-read-api/) — Legacy partner API that returns availability and read URLs for books matched by ISBN, OCLC, LCCN, or OLID identifiers across libraries and the Internet Archive.
- [Open Library Authors API](https://apis.io/apis/open-library/open-library-authors-api/) — Fetch author records and their works by Open Library Author ID. Supports JSON, YAML, and RDF/XML representations.
- [Open Library Editions API](https://apis.io/apis/open-library/open-library-editions-api/) — Retrieve edition-level records (specific printings, ISBNs, formats) by Open Library Edition ID, ISBN-10, ISBN-13, OCLC, or LCCN.
- [Open Library Lists API](https://apis.io/apis/open-library/open-library-lists-api/) — Read and manage user-curated reading lists. Authenticated patrons can create lists and add or remove works, editions, and subjects.
- [Open Library Recentchanges.json API](https://apis.io/apis/open-library/open-library-recentchanges-json-api/) — The Recentchanges.json API from Open Library — 1 operation(s) for recentchanges.json.
- [Open Library Search API](https://apis.io/apis/open-library/open-library-search-api/) — Search Open Library's catalog of books, authors, lists, and subjects. Returns JSON results for full-text and faceted queries, with options for pagination,…
- [Open Library Search.json API](https://apis.io/apis/open-library/open-library-search-json-api/) — The Search.json API from Open Library — 1 operation(s) for search.json.
- [Open Library Subjects API](https://apis.io/apis/open-library/open-library-subjects-api/) — Retrieve books, works, and metadata grouped by subject (genre, topic, place, time, person) with paging and faceting.
- [Open Library Works API](https://apis.io/apis/open-library/open-library-works-api/) — Retrieve work-level records (the abstract concept of a book independent of edition) by Open Library Work ID. Returns JSON, YAML, or RDF/XML.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Open Library Agentic Access](https://apis.io/agentic-access/open-library/open-library-agentic-access/)

#### Collections (9)

Postman and Open Collection request collections.

- [Open Library API](https://apis.io/collections/open-library/open-open-library/)
- [Open Library Authors API](https://apis.io/collections/open-library/open-open-library-authors-api/)
- [Open Library Authors Editions API](https://apis.io/collections/open-library/open-open-library-editions-api/)
- [Open Library Authors Lists API](https://apis.io/collections/open-library/open-open-library-lists-api/)
- [Open Library Authors Recentchanges.json API](https://apis.io/collections/open-library/open-open-library-recentchanges-json-api/)
- [Open Library Authors Search API](https://apis.io/collections/open-library/open-open-library-search-api/)
- [Open Library Authors Search.json API](https://apis.io/collections/open-library/open-open-library-search-json-api/)
- [Open Library Authors Subjects API](https://apis.io/collections/open-library/open-open-library-subjects-api/)
- [Open Library Authors Works API](https://apis.io/collections/open-library/open-open-library-works-api/)

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Open Library Domain Security](https://apis.io/security/open-library/open-library-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Open Library Plans Pricing](https://apis.io/plans/open-library/open-library-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Open Library Rate Limits](https://apis.io/rate-limits/open-library/open-library-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Open Library Finops](https://apis.io/finops/open-library/open-library-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://openlibrary.org/)
- [Documentation](https://openlibrary.org/developers/api)
- [Blog](https://blog.openlibrary.org/)
- [Terms of service](https://archive.org/about/terms.php)
- [GitHub](https://github.com/internetarchive/openlibrary)

## API Evangelist rating

**Kin Score 22.2** — emerging · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 41.5 |
| Contract governance | 0.0 |
| Operational transparency | 10.5 |
| Developer ergonomics | 11.9 |
| Access clarity | 18.4 |

**Agent readiness 17.8** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | na |
| Error Semantics | — |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 9.8** — Education & Research

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/open-library/](https://apis.io/providers/open-library/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Open Library: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/open-library/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
