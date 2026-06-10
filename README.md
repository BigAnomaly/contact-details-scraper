[Contact Details Scraper](https://apify.com/khadinakbar/contact-details-scraper?fpr=data)

# 🔍 Contact Details Scraper – Emails, Phones & Social Links

Extract verified emails, phone numbers, physical addresses, WhatsApp numbers, and 14 social media profiles from any website. The **only contact scraper on Apify that accepts both direct URLs and natural-language search queries** — go from "plumbers in Chicago" to a full contact list in one run, no prep work needed.

## What Does Contact Details Scraper Do?

Contact Details Scraper crawls websites and extracts all publicly available contact information into one clean, deduplicated record per domain. Feed it a list of URLs, or describe the businesses you want to reach and let the actor find them via DuckDuckGo automatically.

## Why Use Contact Details Scraper?

- **Zero URL prep needed** — just type your target niche and location (e.g. "HVAC companies in Dallas Texas") and get back a contact list
- **One clean record per domain** — no duplicate rows per page, no noise, one consolidated output per website
- **Cloudflare-protected emails decoded** — automatically decodes `data-cfemail` attributes that hide emails from basic scrapers
- **14 social platforms in one shot** — LinkedIn, Twitter/X, Facebook, Instagram, YouTube, TikTok, GitHub, Pinterest, Telegram, Discord, Reddit, Medium, Threads, Snapchat

## What Data Can Contact Details Scraper Extract?

| Field | Description | Example |
| --- | --- | --- |
| `domain` | Root domain of the website | `acme.com` |
| `company_name` | Business name from meta/OG/copyright/JSON-LD | `Acme Corp` |
| `emails` | All email addresses, deduplicated and junk-filtered | `["hello@acme.com", "sales@acme.com"]` |
| `phones` | Phone numbers from tel: links and body text | `["+1-312-555-0100"]` |
| `whatsapp` | WhatsApp contact numbers from wa.me links | `["+13125550199"]` |
| `social_links` | Object with 14 social platform URLs | `{"linkedin": "...", "instagram": "..."}` |
| `addresses` | Physical addresses from JSON-LD and text patterns | `["123 Main St, Chicago, IL 60601"]` |
| `pages_scraped` | How many pages were crawled for this domain | `7` |
| `source_url` | The original start URL | `https://acme.com` |
| `scraped_at` | ISO 8601 timestamp | `2026-04-13T10:30:00Z` |

## How to Use Contact Details Scraper

### Option A — Direct URLs

Paste a list of website URLs you want to extract contacts from:

```
{
    "startUrls": [
        { "url": "https://company-a.com" },
        { "url": "https://company-b.com" }
    ],
    "maxPagesPerDomain": 10,
    "maxResults": 50
}
```

### Option B — Search Queries (Most Powerful)

Describe the businesses you want to find. The actor searches DuckDuckGo, finds the top websites, and extracts contacts automatically:

```
{
    "searchQueries": [
        "dentists in Miami Florida",
        "web design agencies New York"
    ],
    "maxPagesPerDomain": 8,
    "maxResults": 30
}
```

### Option C — Both Together

Combine URLs and search queries in the same run:

```
{
    "startUrls": [
        { "url": "https://specific-company.com" }
    ],
    "searchQueries": ["roofing contractors Austin Texas"],
    "maxPagesPerDomain": 10,
    "maxResults": 25
}
```

## Input Parameters

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `startUrls` | Array | `[]` | Direct website URLs to extract contacts from |
| `searchQueries` | Array | `[]` | Natural-language search queries (e.g. "lawyers in Boston") |
| `maxPagesPerDomain` | Integer | `10` | Max pages to crawl per domain (contact/about pages crawled first) |
| `maxDepth` | Integer | `2` | How many links deep to follow from start URL |
| `maxResults` | Integer | `20` | Max number of domains to save to the dataset |
| `proxyConfig` | Object | Apify Proxy | Proxy configuration (datacenter recommended) |

## Output Example

```
{
    "domain": "acme.com",
    "company_name": "Acme Corp",
    "emails": ["hello@acme.com", "sales@acme.com", "john@acme.com"],
    "phones": ["+1-312-555-0100", "(312) 555-0101"],
    "whatsapp": ["+13125550199"],
    "social_links": {
        "linkedin": "https://www.linkedin.com/company/acme-corp",
        "twitter": "https://twitter.com/acmecorp",
        "facebook": "https://www.facebook.com/acmecorp",
        "instagram": "https://www.instagram.com/acmecorp",
        "youtube": "https://www.youtube.com/channel/UC123",
        "github": "https://github.com/acme-corp"
    },
    "addresses": ["123 Main Street, Chicago, IL 60601"],
    "pages_scraped": 7,
    "source_url": "https://acme.com",
    "scraped_at": "2026-04-13T10:30:00.000Z"
}
```

## Pricing

This actor uses **pay-per-event pricing** at **$0.003 per domain result** — the most competitive per-domain price on Apify.

| Domains | Cost |
| --- | --- |
| 10 domains | ~$0.03 |
| 100 domains | ~$0.30 |
| 500 domains | ~$1.50 |
| 1,000 domains | ~$3.00 |

Pricing is predictable: you pay per domain saved to your dataset, not per page crawled. The actor also charges the standard Apify `apify-actor-start` event on each run.

## Running via API

```
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: 'YOUR_API_TOKEN' });

const run = await client.actor('USERNAME/contact-details-scraper').call({
    searchQueries: ['dentists in Miami Florida'],
    maxPagesPerDomain: 8,
    maxResults: 25,
});

const { items } = await client.dataset(run.defaultDatasetId).listItems();
console.log(items); // Array of contact records
```

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("USERNAME/contact-details-scraper").call(run_input={
    "searchQueries": ["dentists in Miami Florida"],
    "maxPagesPerDomain": 8,
    "maxResults": 25,
})
items = client.dataset(run["defaultDatasetId"]).list_items().items
print(items)
```

## How It Works

1. **Input processing** — For search queries, the actor fetches DuckDuckGo HTML results and extracts the top website URLs. For direct URLs, they are queued immediately.
2. **Priority crawling** — Contact, About, Team, and Impressum pages are crawled first (highest priority score) since they contain the most contact info.
3. **Multi-source extraction** — Each page is mined via: `mailto:` links (most reliable), `tel:` links, JSON-LD structured data (`@type: Organization`), WhatsApp links (`wa.me`), Cloudflare email decode (`data-cfemail`), and regex-based text extraction for emails and phones.
4. **Domain-level merging** — All findings from all pages of a domain are merged and deduplicated into one clean record.
5. **Social link detection** — 14 platform patterns are matched against the full HTML of each page.
6. **Save & charge** — The consolidated record is pushed to the dataset and the `domain-result` event is charged.

## Common Use Cases

- **B2B lead generation** — Build prospect lists of companies in your target niche and location
- **Sales outreach** — Get direct emails and LinkedIn profiles before your first touch
- **CRM enrichment** — Append missing contact data to existing account records
- **Agency prospecting** — Find SMBs in specific industries or cities for agency services
- **Market research** — Gather contact data across industries or regions
- **Competitor monitoring** — Discover which social platforms competitors actively use

## FAQ

**What if a website blocks scraping?**
The actor uses Apify's datacenter proxy pool by default, which rotates IPs. Enable "Residential Proxy" in the proxy config for heavily protected sites.

**Do search queries find email addresses directly?**
No — the actor searches for websites matching your query, then crawls those websites to extract contact info. It doesn't search email databases.

**How many pages per domain should I use?**
5–8 pages covers most small business websites. Use 10–15 for larger sites with many subpages. The actor always crawls contact/about/team pages first.

**Some emails look generic — can I filter them?**
The actor already filters obvious junk patterns (noreply@, mailer-daemon@, example.com, etc.). For further filtering, export to CSV and filter by email prefix patterns.

**Does it work on JavaScript-heavy sites?**
The actor uses a fast HTTP crawler. Most contact pages are server-rendered. If a site requires JavaScript to render contact info, those specific emails may not be found.

## Legal Disclaimer

This actor is designed for extracting publicly available contact information from websites. Users are solely responsible for ensuring their use complies with applicable laws, website terms of service, GDPR, CCPA, and other data protection regulations. Do not use this tool to collect personal data without a lawful basis. Apify is not responsible for any misuse of extracted data.

---

*Export scraped data, run the scraper via API, schedule and monitor runs, or integrate with other tools using Apify's platform.*