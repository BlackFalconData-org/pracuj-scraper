# Pracuj Scraper

Extract structured data from [pracuj.pl](https://pracuj.pl) — structured job listings from pracuj.pl — Poland's #1 job board. Structured salary parsing, incremental mode, 30+ output fields.

**[Pracuj Scraper - Poland’s #1 Job Board on Apify →](https://apify.com/blackfalcondata/pracuj-scraper)**

---

## Key features




**Search with filters** — Search by keyword and location. Filter by contract type, work mode, position level, and more.

**Detail enrichment** — Fetch full job descriptions, salary data, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

---

## Use cases




**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from pracuj.pl on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from pracuj.pl.

---

## Quick start

```json
{
  "query": "software engineer",
  "maxResults": 50,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `query` | string | — | Job search keywords (e.g. 'software engineer', 'python developer'). |
| `location` | string | — | City or region (e.g. 'Warszawa', 'Kraków', 'Wrocław'). |
| `contractType` | enum | `""` | Filter by contract type (API parameter ct). |
| `workMode` | enum | `""` | Filter by work mode. |
| `positionLevel` | enum | `""` | Filter by seniority level (API parameter et). |
| `region` | enum | `""` | Filter by Polish region. |
| `withSalary` | boolean | `false` | Only return offers that show salary. |
| `period` | enum | `""` | Only return offers posted within this period. |
| `maxResults` | integer | `50` | Maximum total results. 0 = unlimited. |
| `includeDetails` | boolean | `true` | Fetch full job details (description, technologies, apply URL). Slower but richer data. |
| `descriptionMaxLength` | integer | `0` | Truncate description to N characters. 0 = no truncation. |
| `compact` | boolean | `false` | Return core fields only (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Only return new or changed listings since the last run. |
| `stateKey` | string | — | Unique identifier for this tracked universe. Different stateKeys maintain independent state. |

---

## FAQ

**How to scrape pracuj?**
Use this actor on Apify to extract structured data from pracuj.pl. Set your search query and filters in the input, then run — no coding needed.

**Is there a pracuj API?**
pracuj.pl does not offer a structured data export. This actor works as an unofficial API, returning structured JSON data from pracuj.

**Is it legal to scrape pracuj.pl?**
Web scraping of publicly available data is generally legal. This actor only accesses publicly visible information. Always check the target site's terms of service for your specific use case.

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->

---

## Related products by Black Falcon Data




- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 03*
