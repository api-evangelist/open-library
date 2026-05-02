# Open Library (open-library)

Open Library offers a suite of APIs to help developers get up and running with its data. This includes RESTful APIs that make Open Library data available in JSON, YAML, and RDF/XML formats, plus a Search Inside full-text search service, cover image endpoints, and read-protocol library lookup APIs. Most resources also expose machine-readable representations by appending `.json`, `.yml`, or `.rdf` to any Open Library URL.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/open-library/refs/heads/main/apis.yml)

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

**Human URL:** [https://openlibrary.org/dev/docs/api/search](https://openlibrary.org/dev/docs/api/search)

#### Tags

- Books, Catalog, Search

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/search)

### Open Library Search Inside API

Full-text search across the millions of digitized books in the Internet Archive's collection, returning matching passages and book identifiers.

**Human URL:** [https://openlibrary.org/dev/docs/api/search_inside](https://openlibrary.org/dev/docs/api/search_inside)

#### Tags

- Books, Full Text, Search

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/search_inside)

### Open Library Works API

Retrieve work-level records (the abstract concept of a book independent of edition) by Open Library Work ID. Returns JSON, YAML, or RDF/XML.

**Human URL:** [https://openlibrary.org/dev/docs/api/books](https://openlibrary.org/dev/docs/api/books)

#### Tags

- Books, Catalog, Works

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/books)

### Open Library Editions API

Retrieve edition-level records (specific printings, ISBNs, formats) by Open Library Edition ID, ISBN-10, ISBN-13, OCLC, or LCCN.

**Human URL:** [https://openlibrary.org/dev/docs/api/books](https://openlibrary.org/dev/docs/api/books)

#### Tags

- Books, Catalog, Editions, ISBN

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/books)

### Open Library Authors API

Fetch author records and their works by Open Library Author ID. Supports JSON, YAML, and RDF/XML representations.

**Human URL:** [https://openlibrary.org/dev/docs/api/authors](https://openlibrary.org/dev/docs/api/authors)

#### Tags

- Authors, Catalog

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/authors)

### Open Library Subjects API

Retrieve books, works, and metadata grouped by subject (genre, topic, place, time, person) with paging and faceting.

**Human URL:** [https://openlibrary.org/dev/docs/api/subjects](https://openlibrary.org/dev/docs/api/subjects)

#### Tags

- Catalog, Subjects, Taxonomy

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/subjects)

### Open Library Covers API

Retrieve book and author cover images by Open Library ID, ISBN, OCLC, LCCN, or Goodreads ID, in small, medium, and large sizes.

**Human URL:** [https://openlibrary.org/dev/docs/api/covers](https://openlibrary.org/dev/docs/api/covers)

#### Tags

- Covers, Images, Media

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/covers)

### Open Library Lists API

Read and manage user-curated reading lists. Authenticated patrons can create lists and add or remove works, editions, and subjects.

**Human URL:** [https://openlibrary.org/dev/docs/api/lists](https://openlibrary.org/dev/docs/api/lists)

#### Tags

- Lists, Reading Lists, User Data

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/lists)

### Open Library My Books API

Access a patron's public reading log: Want to Read, Currently Reading, and Already Read shelves for a given Open Library account.

**Human URL:** [https://openlibrary.org/dev/docs/api/mybooks](https://openlibrary.org/dev/docs/api/mybooks)

#### Tags

- Reading Log, User Data

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/mybooks)

### Open Library Recent Changes API

Stream recent edits across the Open Library catalog including works, editions, authors, lists, and subjects, with filtering by kind and time range.

**Human URL:** [https://openlibrary.org/dev/docs/api/recentchanges](https://openlibrary.org/dev/docs/api/recentchanges)

#### Tags

- Activity, Changes, Feed

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/recentchanges)

### Open Library Read API

Legacy partner API that returns availability and read URLs for books matched by ISBN, OCLC, LCCN, or OLID identifiers across libraries and the Internet Archive.

**Human URL:** [https://openlibrary.org/dev/docs/api/read](https://openlibrary.org/dev/docs/api/read)

#### Tags

- Availability, Libraries, Lookup

#### Properties

- [Documentation](https://openlibrary.org/dev/docs/api/read)

## Common Properties

- [Website](https://openlibrary.org/)
- [Developer Documentation](https://openlibrary.org/developers/api)
- [Bulk Data Dumps](https://openlibrary.org/developers/dumps)
- [GitHub Organization](https://github.com/internetarchive/openlibrary)
- [Issues](https://github.com/internetarchive/openlibrary/issues)
- [Blog](https://blog.openlibrary.org/)
- [Terms of Service](https://archive.org/about/terms.php)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
