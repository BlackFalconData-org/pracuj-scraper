# Pracuj Scraper

Extract structured data from [pracuj.pl](https://pracuj.pl) — structured job listings from pracuj.pl — Poland's #1 job board. Structured salary parsing, incremental mode, 30+ output fields.

**[Pracuj Scraper - Poland’s #1 Job Board on Apify →](https://apify.com/blackfalcondata/pracuj-scraper?fpr=1h3gvi)**

---

## Key features






**Search with filters** — Search by keyword and location. Filter by contract type, work mode, position level, and more.

**Detail enrichment** — Fetch full job descriptions, salary data, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Change classification** — Track cross-run repost detection across runs. Build audit trails of how listings evolve over time.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings. Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases






**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from pracuj.pl on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from pracuj.pl.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Compensation benchmarking**
Aggregate salary ranges across roles, industries, and locations on pracuj.pl to inform pricing decisions, hiring plans, or candidate negotiations.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

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


## Output fields

Every listing returns the same 40-field schema. Missing values are `null` — never omitted.

- `jobId`
- `offerId`
- `title`
- `company`
- `companyId`
- `companyProfileUrl`
- `location`
- `region`
- `country`
- `coordinates`
- `salaryText`
- `salaryMin`
- `salaryMax`
- `salaryCurrency`
- `salaryPeriod`
- `employmentType`
- `contractTypes`
- `workModes`
- `workSchedules`
- `positionLevels`
- `isRemote`
- `description`
- `technologies`
- `responsibilities`
- `requirements`
- `offered`
- `aiSummary`
- `applyUrl`
- `contactPhone`
- `remoteRecruitment`
- `isOneClickApply`
- `categories`
- `url`
- `allOfferUrls`
- `postedDate`
- `expirationDate`
- `scrapedAt`
- `portalUrl`
- `source`
- `changeType`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "5968ce665b8c32ceb68942473ac0652f125dfa1eb67e4abaf9c22f6f4e7cb1a7",
  "offerId": 1004712299,
  "title": "APEX Developer",
  "company": "NATEK POLAND",
  "companyId": 20002666,
  "companyProfileUrl": "https://pracodawcy.pracuj.pl/company/20002666",
  "location": "Białystok",
  "region": "podlaskie",
  "country": "Polska",
  "coordinates": null,
  "salaryText": null,
  "salaryMin": null
}
```

*Truncated — full records contain 40 fields. See Output fields for the complete schema.*


**[Try Pracuj Scraper - Poland’s #1 Job Board now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/pracuj-scraper?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.01 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/pracuj-scraper?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data






- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board
- [Naukri Scraper](https://apify.com/blackfalcondata/naukri-scraper?fpr=1h3gvi) — India's largest job portal

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---

---

*Last updated: 2026 03*
