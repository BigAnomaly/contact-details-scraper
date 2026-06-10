[Contact Details Scraper](https://apify.com/rp_openpro.ai/contact-details-scraper?fpr=data)

# Website Contact Scraper — Emails, Phones, 14 Social Platforms, Lead Scoring & Business Intelligence

**Apify website contact extractor:** paste **company domains** → get **emails, phones, 14 social platforms, lead score, tech stack, WHOIS**. Parallel multi-page crawl — built for scale. *SEO: website email scraper, bulk contact enrichment, b2b email finder api.*

> **Apollo charges $99/mo for 1,000 contacts. ZoomInfo charges $15,000+/year. This Actor does it for $2.50 per 1,000 domains — with more data fields than either.**

The most complete website contact scraper on Apify. Extract **emails, phone numbers, named contacts with job titles**, social media profiles across **14 platforms** (including WhatsApp, Telegram, Discord), **tech stack, industry, WHOIS**, and a **0–100 lead quality score** from any list of company websites. Multi-page crawling with **email verification** and **email pattern detection** — all in a single run.

Paste domains → get **structured, scored, verified contact data** ready for your CRM, outreach tool, or spreadsheet. **40+ data fields per company.**

## What contact data can you extract?

| Data type | Details |
| --- | --- |
| **Email addresses** | All discoverable emails with on-domain priority |
| **Phone numbers** | International and local formats, validated and formatted to international standard |
| **Named contacts** | People with job titles extracted from JSON-LD, microdata, and team page HTML |
| **WhatsApp** | wa.me links and WhatsApp business numbers |
| **Telegram** | t.me profiles and group links |
| **Discord** | Server invite links |
| **Snapchat** | Profile links |
| **Threads** | Profile links |
| **Reddit** | Subreddit and user profile links |
| **Facebook** | Pages and profiles |
| **Instagram** | Profiles |
| **LinkedIn** | Company and personal profiles |
| **Twitter / X** | Profiles |
| **YouTube** | Channels |
| **Pinterest** | Profiles |
| **GitHub** | Organization and user profiles |
| **TikTok** | Profiles |
| **Physical address** | Business address from structured data and microdata |
| **Email patterns** | Detected naming convention (first.last@, flast@, first@) |
| **Generated emails** | Predicted emails for contacts without public addresses |
| **Email verification** | MX record check + SMTP probe for each email |
| **Lead score** | 0-100 quality score across 5 categories with letter grade A-F |
| **Business industry** | Automatic classification into 30 industries |
| **Business keywords** | Top keywords extracted from page content |
| **Tech stack** | CMS, frameworks, analytics, chat tools, and marketing tech |
| **Tracking tags** | Google Analytics, Google Tag Manager, Facebook Pixel IDs |
| **WHOIS data** | Registrar, creation date, expiration, name servers, registrant |

## Why choose this over competitors?

| Feature | This actor | Basic contact scraper | Places scraper |
| --- | --- | --- | --- |
| **Price per 1,000** | **$2.50** | ~$4.00 | ~$5.00 |
| Social platforms | **14** | 4-6 | 6 |
| WhatsApp & Telegram | **Yes** | No | No |
| Discord, Snapchat, Threads, Reddit | **Yes** | No | No |
| Multi-page crawling | Up to 20 pages/domain | 1 page | N/A |
| Email verification (MX + SMTP) | **Yes** | No | No |
| Email pattern detection + generation | **Yes** | No | No |
| Lead scoring & grading (0-100, A-F) | **Yes** | No | No |
| Named contacts with job titles | **Yes (JSON-LD + HTML)** | Basic | No |
| Business industry classification | **Yes (30 industries)** | No | No |
| Business keywords | **Yes** | No | No |
| Tech stack detection (25+ tools) | **Yes** | No | No |
| WHOIS domain data | **Yes** | No | No |
| Phone validation & formatting | **Yes (international standard)** | Basic | Basic |
| Address extraction | **Yes** | No | Yes |
| Tracking tag extraction | **Yes** | No | No |

**More data. Lower price. Every feature included.**

## Output example

Every domain produces one enriched lead record with all fields populated:

```
{
    "domain": "apify.com",
    "url": "https://apify.com",
    "emails": ["info@apify.com", "support@apify.com", "jan@apify.com"],
    "phones": ["+420 255 000 222"],
    "contacts": [
        { "name": "Jan Curn", "title": "CEO & Co-founder", "email": "jan@apify.com" },
        { "name": "Ondra Urban", "title": "CTO & Co-founder" }
    ],
    "socialLinks": {
        "facebook": null,
        "instagram": null,
        "linkedin": "https://www.linkedin.com/company/apifytech",
        "twitter": "https://twitter.com/apify",
        "youtube": "https://www.youtube.com/apify",
        "pinterest": null,
        "github": "https://github.com/apify",
        "tiktok": "https://www.tiktok.com/@apifytech",
        "whatsapp": null,
        "telegram": null,
        "snapchat": null,
        "discord": "https://discord.gg/jyEM2PRvMU",
        "reddit": null,
        "threads": null
    },
    "emailPattern": "first@apify.com",
    "emailPatternConfidence": 0.85,
    "generatedEmails": [
        { "name": "Ondra Urban", "email": "ondra@apify.com" }
    ],
    "emailVerification": [
        { "email": "info@apify.com", "status": "valid", "mxValid": true },
        { "email": "support@apify.com", "status": "valid", "mxValid": true }
    ],
    "score": 88,
    "grade": "A",
    "scoreBreakdown": {
        "contactReachability": 22,
        "businessLegitimacy": 20,
        "onlinePresence": 18,
        "websiteQuality": 16,
        "teamTransparency": 12
    },
    "signals": [
        { "signal": "Multiple email addresses", "category": "contactReachability", "points": 10, "detail": "3 emails" },
        { "signal": "Phone number found", "category": "contactReachability", "points": 8, "detail": "+420 255 000 222" },
        { "signal": "Strong social media presence", "category": "onlinePresence", "points": 12, "detail": "4 platforms" }
    ],
    "address": "Vodickova 704/36, 110 00 Prague, Czech Republic",
    "businessIndustry": "technology",
    "businessKeywords": ["web scraping", "automation", "data extraction", "api", "cloud"],
    "cmsDetected": "Next.js",
    "techSignals": ["React", "Next.js", "Google Analytics", "Intercom", "Segment"],
    "trackingTags": {
        "googleAnalytics": "G-ABC123XYZ",
        "googleTagManager": "GTM-ABC123",
        "facebookPixel": null
    },
    "whois": {
        "registrar": "GoDaddy",
        "createdDate": "2015-03-01",
        "expiresDate": "2027-03-01",
        "nameServers": ["ns1.example.com", "ns2.example.com"],
        "registrantOrg": "Apify Technologies s.r.o."
    },
    "pagesCrawled": 5,
    "succeeded": true,
    "error": null,
    "processedAt": "2026-03-18T14:30:00.000Z"
}
```

## How it works — 7-step pipeline

The actor runs a fully automated enrichment pipeline for each domain:

1. **Multi-page crawl** — Crawls the homepage and discovers internal pages (/about, /contact, /team, /people, etc.) up to your configured limit. High-value paths are crawled first for maximum contact yield.
2. **Data extraction** — Extracts emails, phones, named contacts (from JSON-LD, microdata, and team page HTML), social media links across 14 platforms, messaging links (WhatsApp, Telegram, Discord), tracking tags, physical address, and tech stack from all crawled pages. Results are merged and deduplicated automatically.
3. **Business intelligence** — Classifies the company into one of 30 industries and extracts the top business keywords from page content using semantic HTML extraction.
4. **Email verification** — Validates each discovered email for deliverability via MX record lookup and SMTP probe. Returns status: valid, invalid, unknown, or no-mx.
5. **Email pattern detection** — Identifies the company's email naming convention (e.g., first.last@, flast@, first@) and generates predicted email addresses for team members without public emails.
6. **WHOIS lookup** — Retrieves domain registration data including registrar, creation/expiration dates, name servers, and registrant organization.
7. **Lead scoring** — Scores 0-100 across five weighted categories including messaging channel availability and assigns a letter grade A-F. Each signal is tracked with point values for full transparency.

## Input parameters

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `urls` | string[] | *required* | Company website URLs or bare domains to enrich |
| `maxPagesPerDomain` | integer | `5` | Pages to crawl per domain (1-20). Higher = more contacts found |
| `maxConcurrency` | integer | `15` | Domains to process in parallel. Higher = faster but more memory |
| `verifyEmails` | boolean | `true` | Verify discovered emails for deliverability |
| `skipLeadScoring` | boolean | `false` | Skip scoring and grading |
| `skipWhois` | boolean | `false` | Skip WHOIS domain lookup |
| `minScore` | integer | `0` | Exclude leads below this score threshold |
| `proxyConfiguration` | object | Apify Proxy | Proxy settings for reliable scraping |

## Input examples

**Full pipeline with quality filter (most common):**

```
{
    "urls": ["stripe.com", "hubspot.com", "notion.so", "linear.app"],
    "maxPagesPerDomain": 8,
    "minScore": 50
}
```

**Fast contact scraping only (cheapest, fastest):**

```
{
    "urls": ["example.com", "acme.co"],
    "maxPagesPerDomain": 3,
    "verifyEmails": false,
    "skipLeadScoring": true,
    "skipWhois": true
}
```

**Large batch with proxy:**

```
{
    "urls": ["stripe.com", "hubspot.com", "notion.so", "linear.app", "cal.com", "vercel.com"],
    "maxPagesPerDomain": 5,
    "minScore": 40,
    "proxyConfiguration": { "useApifyProxy": true }
}
```

## Lead scoring reference

| Category | Max Points | What it measures |
| --- | --- | --- |
| Contact Reachability | 30 | Email addresses, phone numbers, contact form, messaging channels (WhatsApp, Telegram, Discord) |
| Business Legitimacy | 25 | Physical address, about page, privacy policy, industry identified |
| Online Presence | 20 | Social media profiles across 14 platforms |
| Website Quality | 15 | SSL/HTTPS, analytics, live chat, modern website |
| Team Transparency | 10 | Named contacts with job titles |

**Grade scale:** A (90-100), B (75-89), C (60-74), D (40-59), F (0-39)

## Pricing

**$2.50 per 1,000 URLs** (standard rate) — with automatic volume discounts as your usage grows.

| Tier | Per lead | Per 1,000 leads | Qualifies at |
| --- | --- | --- | --- |
| Standard | $0.0025 | **$2.50** | Default |
| Bronze | $0.0020 | **$2.00** | Apify Bronze plan |
| Silver | $0.0018 | **$1.80** | Apify Silver plan |
| Gold | $0.0015 | **$1.50** | Apify Gold plan |

Free users can process **10 URLs per run** to test the actor before subscribing.

| Configuration | Approx. cost per lead | Typical run time |
| --- | --- | --- |
| Full pipeline (all steps) | $0.0025 | 3-8 seconds |
| Skip WHOIS + scoring | $0.0020 | 2-5 seconds |
| Contact scraping only | $0.0015 | 1-3 seconds |

## Integrations

This actor works with the full Apify ecosystem and popular automation platforms:

- **Apify API** — Trigger runs programmatically and retrieve enriched leads as JSON. Build automated prospecting workflows.
- **Zapier** — Connect to 5,000+ apps. Trigger enrichment when a new company is added to your CRM, then push scored results into Salesforce, HubSpot, or Pipedrive.
- **Make (Integromat)** — Build multi-step workflows that take prospect lists from Google Sheets, enrich them, filter by score, and route qualified leads into outreach sequences.
- **Google Sheets** — Export the enriched dataset directly. Key fields like domain, emails, score, grade, and contacts map cleanly into spreadsheet columns.
- **Webhooks** — Receive enriched leads as soon as the run completes for real-time lead routing.
- **Scheduled Runs** — Process new batches of prospect domains daily or weekly with the Apify Scheduler.
- **MCP Server** — Use this actor with AI agents through the Apify MCP server for automated lead enrichment pipelines.

## Programmatic access

**Python:**

```
from apify_client import ApifyClient

client = ApifyClient("YOUR_API_TOKEN")
run = client.actor("leadsit/contact-details-scraper").call(run_input={
    "urls": ["stripe.com", "hubspot.com"],
    "maxPagesPerDomain": 8,
    "minScore": 50,
})

for lead in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(f'{lead["domain"]} [{lead["grade"]} {lead["score"]}] — {", ".join(lead["emails"])}')
```

**JavaScript:**

```
import { ApifyClient } from "apify-client";

const client = new ApifyClient({ token: "YOUR_API_TOKEN" });
const run = await client.actor("leadsit/contact-details-scraper").call({
    urls: ["stripe.com", "hubspot.com"],
    maxPagesPerDomain: 8,
    minScore: 50,
});

const { items } = await client.dataset(run.defaultDatasetId).listItems();
for (const lead of items) {
    console.log(`${lead.domain} [${lead.grade} ${lead.score}] — ${lead.emails.join(", ")}`);
}
```

**cURL:**

```
curl -X POST "https://api.apify.com/v2/acts/leadsit~contact-details-scraper/runs?token=YOUR_API_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"urls": ["stripe.com", "hubspot.com"], "maxPagesPerDomain": 8, "minScore": 50}'
```

## Use cases

- **Sales prospecting** — Enrich a list of target company domains with verified emails, phone numbers, WhatsApp links, and quality scores to prioritize outreach.
- **Lead qualification** — Automatically score and grade leads based on 30+ website signals before adding them to your pipeline.
- **Competitive intelligence** — Map competitors' tech stacks, analytics tools, and social media presence across 14 platforms at scale.
- **Market research** — Classify thousands of companies by industry and extract business keywords for segmentation.
- **CRM enrichment** — Fill in missing contact details, social links, messaging channels, tech stack, and company data in your CRM.
- **Agency audits** — Check clients' tracking tag setup, tech stack, social presence, and messaging availability in one run.
- **Email outreach** — Find company email patterns and generate predicted email addresses for decision makers.
- **Omnichannel contact discovery** — Find every way to reach a company: email, phone, WhatsApp, Telegram, Discord, and all major social platforms.

## FAQ

**How many pages should I crawl per domain?**
Default of 5 works well for most company websites. Increase to 10-15 for large enterprise sites where contacts may be on deep pages. Set to 1 for maximum speed if you only need homepage data.

**What social platforms are supported?**
14 platforms: Facebook, Instagram, LinkedIn, Twitter/X, YouTube, Pinterest, GitHub, TikTok, WhatsApp, Telegram, Snapchat, Discord, Reddit, and Threads. Links are extracted from hrefs across all crawled pages and validated to exclude share/embed URLs.

**How are phone numbers validated?**
Every phone number candidate is validated using Google's libphonenumber standard. Only numbers that pass format and length validation are included. All phones are formatted in international format (e.g., +33 1 23 45 67 89) for consistency. Country is auto-detected from the website's TLD when no country code is present.

**Is email verification accurate?**
Verification checks whether the email domain accepts mail and whether the specific address exists on the mail server. Some servers always accept (catch-all), which shows as "unknown" status. Verification accuracy is typically 80-90%.

**What industries are detected?**
30 industries including technology, healthcare, finance, real-estate, education, retail, manufacturing, legal, marketing, consulting, construction, food-beverage, automotive, energy, logistics, media, telecom, hospitality, and more.

**How does contact extraction work?**
Named contacts are extracted from three sources: JSON-LD structured data, HTML microdata (itemprop="name"/itemprop="jobTitle"), and team page HTML patterns (elements with team/member/staff/leadership classes). Job titles are validated against known title keywords.

**What if a website blocks the request?**
The actor uses rotating user agents and supports Apify Proxy. Failed domains are marked with `succeeded: false` and an error message — they don't stop the rest of the run.

**Can I skip steps to save cost and time?**
Yes. Set `skipLeadScoring: true` and `skipWhois: true` for contact-only extraction at roughly half the cost. Disable `verifyEmails` to further speed up runs when you don't need email validation.

**How does email pattern detection work?**
The actor analyzes discovered emails and cross-references them with named contacts found on the website. It identifies the naming convention (e.g., first.last@, flast@, first@) and generates predicted email addresses for team members whose emails weren't publicly listed.

**What data is in the WHOIS lookup?**
Domain registrar, creation date, expiration date, last updated date, name servers, registrant organization, and registrant country (when available from public WHOIS records).

**How long does it take per domain?**
With default settings (5 pages, all features enabled), each domain takes 3-8 seconds. Network-dependent steps run in parallel to minimize latency.

**Can I process hundreds of domains?**
Yes. The actor processes domains in parallel (up to 15 concurrent by default). Processing 100 domains with the full pipeline typically takes 2-5 minutes.

## Responsible use

This actor collects publicly visible information from company websites. Follow these guidelines:

- **Comply with applicable laws.** Check GDPR, CAN-SPAM, CCPA, and local regulations before using collected data for outreach. Presence of contact information on a website does not constitute consent to receive marketing communications.
- **Respect robots.txt and rate limits.** Default settings are conservative. Consider lowering crawl depth for websites that explicitly restrict scraping.
- **Generated emails are predictions.** Emails produced by the pattern detection are algorithmic guesses based on detected naming conventions. They should be verified before use and should never be used for bulk unsolicited messaging.
- **Do not scrape sensitive sites.** Avoid using this tool on government agencies, healthcare providers, or organizations where automated data collection may violate terms of service.

## Related actors

- [Google Maps Scraper with Emails & Social Media](https://apify.com/leadsit/google-maps-scraper-with-emails-social-media) — Search Google Maps by keyword and location, get enriched business data
- [Trustpilot Reviews Scraper](https://apify.com/leadsit/trustpilot-reviews-scraper) — Extract reviews, ratings, and company data from Trustpilot

---

> **Don't have company URLs yet?** Use [**B2B Company URL Finder**](https://apify.com/leadsit/b2b-url-finder) to discover domains by keyword — or use [**Ultimate Leads**](https://console.apify.com/actors/5XYUiihBAg0sn8sBy) which runs B2B + Google Maps + this contact scraper in **one Actor, one dataset, zero manual work**.

---

*Built by [Leadsit.eu](https://www.leadsit.eu) — B2B lead generation tools for modern sales teams.*

*Keywords: website contact scraper, extract emails from websites, bulk email finder, company contact extractor, b2b lead enrichment, website email extractor, phone number extractor, social media scraper, lead scoring tool, website scraper with emails, extract linkedin from website, whatsapp extractor, business contact finder, apify contact scraper, email verification tool, tech stack detector, website intelligence, b2b data enrichment api*