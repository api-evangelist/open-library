# Open Library (open-library)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Open Library offers a suite of APIs to help developers get up and running with its data. This includes RESTful APIs that make Open Library data available in JSON, YAML, and RDF/XML formats, plus a Search Inside full-text search service, cover image endpoints, and read-protocol library lookup APIs. Most resources also expose machine-readable representations by appending .json, .yml, or .rdf to any Open Library URL.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/open-library/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/open-library/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Authors
- Books
- Catalog
- Covers
- Libraries
- Open Data
- Reading Lists
- Search
- Subjects

## Timestamps

- **Created:** 2025-02-06
- **Modified:** 2026-04-28

## APIs

### Open Library Search API

Search Open Library's catalog of books, authors, lists, and subjects. Returns JSON results for full-text and faceted queries, with options for pagination, field selection, and language filtering.

- **Human URL:** [https://openlibrary.org/dev/docs/api/search](https://openlibrary.org/dev/docs/api/search)

#### Tags

- Books
- Catalog
- Search

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/search)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Search Inside API

Full-text search across the millions of digitized books in the Internet Archive's collection, returning matching passages and book identifiers.

- **Human URL:** [https://openlibrary.org/dev/docs/api/search_inside](https://openlibrary.org/dev/docs/api/search_inside)

#### Tags

- Books
- Full Text
- Search

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/search_inside)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Works API

Retrieve work-level records (the abstract concept of a book independent of edition) by Open Library Work ID. Returns JSON, YAML, or RDF/XML.

- **Human URL:** [https://openlibrary.org/dev/docs/api/books](https://openlibrary.org/dev/docs/api/books)

#### Tags

- Books
- Catalog
- Works

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/books)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Editions API

Retrieve edition-level records (specific printings, ISBNs, formats) by Open Library Edition ID, ISBN-10, ISBN-13, OCLC, or LCCN.

- **Human URL:** [https://openlibrary.org/dev/docs/api/books](https://openlibrary.org/dev/docs/api/books)

#### Tags

- Books
- Catalog
- Editions
- ISBN

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/books)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Authors API

Fetch author records and their works by Open Library Author ID. Supports JSON, YAML, and RDF/XML representations.

- **Human URL:** [https://openlibrary.org/dev/docs/api/authors](https://openlibrary.org/dev/docs/api/authors)

#### Tags

- Authors
- Catalog

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/authors)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Subjects API

Retrieve books, works, and metadata grouped by subject (genre, topic, place, time, person) with paging and faceting.

- **Human URL:** [https://openlibrary.org/dev/docs/api/subjects](https://openlibrary.org/dev/docs/api/subjects)

#### Tags

- Catalog
- Subjects
- Taxonomy

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/subjects)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Covers API

Retrieve book and author cover images by Open Library ID, ISBN, OCLC, LCCN, or Goodreads ID, in small, medium, and large sizes.

- **Human URL:** [https://openlibrary.org/dev/docs/api/covers](https://openlibrary.org/dev/docs/api/covers)

#### Tags

- Covers
- Images
- Media

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/covers)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Lists API

Read and manage user-curated reading lists. Authenticated patrons can create lists and add or remove works, editions, and subjects.

- **Human URL:** [https://openlibrary.org/dev/docs/api/lists](https://openlibrary.org/dev/docs/api/lists)

#### Tags

- Lists
- Reading Lists
- User Data

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/lists)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library My Books API

Access a patron's public reading log: Want to Read, Currently Reading, and Already Read shelves for a given Open Library account.

- **Human URL:** [https://openlibrary.org/dev/docs/api/mybooks](https://openlibrary.org/dev/docs/api/mybooks)

#### Tags

- Reading Log
- User Data

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/mybooks)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Recent Changes API

Stream recent edits across the Open Library catalog including works, editions, authors, lists, and subjects, with filtering by kind and time range.

- **Human URL:** [https://openlibrary.org/dev/docs/api/recentchanges](https://openlibrary.org/dev/docs/api/recentchanges)

#### Tags

- Activity
- Changes
- Feed

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/recentchanges)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Open Library Read API

Legacy partner API that returns availability and read URLs for books matched by ISBN, OCLC, LCCN, or OLID identifiers across libraries and the Internet Archive.

- **Human URL:** [https://openlibrary.org/dev/docs/api/read](https://openlibrary.org/dev/docs/api/read)

#### Tags

- Availability
- Libraries
- Lookup

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/read)
- [Postman Collection](collections/open-library.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/open-library.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://openlibrary.org/)
- [Developer  Documentation](https://openlibrary.org/developers/api)
- [Bulk  Data  Dumps](https://openlibrary.org/developers/dumps)
- [GitHub Organization](https://github.com/internetarchive/openlibrary)
- [Issues](https://github.com/internetarchive/openlibrary/issues)
- [Blog](https://blog.openlibrary.org/)
- [Terms of Service](https://archive.org/about/terms.php)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
