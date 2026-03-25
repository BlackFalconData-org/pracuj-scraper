# Pracuj Scraper

Extract structured data from [pracuj.pl](https://pracuj.pl) — structured job listings from pracuj.pl — Poland's #1 job board. Structured salary parsing, incremental mode, 30+ output fields.

**[Run on Apify →](https://apify.com/blackfalcondata/pracuj-scraper)**

---

## Key features

🔍 **Smart search with filters**

Search by keyword, location, and multiple filters. Smart input resolution ensures you always get results.

📄 **Detail enrichment**

Fetch full job descriptions, salary data, employer profiles, and contact information for each listing.

🔄 **Incremental mode**

Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

⚡ **Compact output for AI agents**

Core-fields-only mode optimized for MCP and AI agent workflows. Description truncation to control output size.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from pracuj on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from pracuj.

**AI and LLM workflows**
Use compact mode and description truncation to feed data into AI agents, MCP servers, and LLM pipelines without exceeding token budgets.

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

| Product | Description |
|:--------|:------------|
| [StepStone Jobs API](https://github.com/BlackFalconData-org/stepstone-jobs-api) | Job listings from 18 European portals |
| [Company Jobs Tracker](https://github.com/BlackFalconData-org/company-jobs-tracker-api) | Track new/removed jobs per company |
| [Indeed Jobs Feed](https://github.com/BlackFalconData-org/indeed-jobs-feed) | Indeed job listings with salary data |
| [Glassdoor Jobs Feed](https://github.com/BlackFalconData-org/glassdoor-jobs-feed) | Glassdoor listings with company ratings |
| [Arbeitsagentur Jobs Feed](https://github.com/BlackFalconData-org/arbeitsagentur-jobs-feed) | Germany's federal job portal (1M+ listings) |
| [Naukri Jobs Feed](https://github.com/BlackFalconData-org/naukri-jobs-feed) | India's largest job portal |
| [Bilbasen Scraper](https://github.com/BlackFalconData-org/bilbasen-scraper) | Denmark's largest car marketplace |

---

*Last updated: 2026 03*
