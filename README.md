[Contact Details Scraper](https://apify.com/kawsar/contact-details-scraper?fpr=data)

# Contact Details Scraper: Professional E-mail Extractor & Lead Generation Tool

![Contact Details Scraper Cover](https://images.apifyusercontent.com/9uBtXsACLQvRDkaDKZ1EAC__jqwmvz4qGzR9Hg_rMec/w:1800/cb:1/aHR0cHM6Ly9pLmltZ3VyLmNvbS81ZlNiNG1sLnBuZw.webp)

The **Contact Details Scraper** is a high-performance **e mail extractor** and **email scraper** designed to help you automate your **lead generation** process. Whether you need a **linkedin email scraper**, an **instagram email scraper**, or a tool to **scrape website for emails**, this actor provides a reliable solution for extracting contact information at scale.

This tool acts as a **bulk email extractor** that crawls websites to find hidden email addresses, phone numbers, and social media profiles. It's the ultimate **email scraping tool** for marketers, sales teams, and recruiters who need to build high-quality contact lists without manual work.

## What data does this actor extract?

Our **email extractor from website** doesn't just stop at emails. It gathers a comprehensive suite of contact details:

- **Emails**: High-accuracy **email address extractor** for professional and personal addresses.
- **Phone Numbers**: Extracts numbers from text and `tel:` links.
- **LinkedIn Profiles**: Works as a **linkedin email extractor** to find company and personal profiles.
- **Instagram Profiles**: Integrated **instagram email scraper** logic for social discovery.
- **Facebook Pages**: **Facebook email extractor** capabilities for business pages.
- **Twitter/X, YouTube, TikTok, and Pinterest**: Full social media coverage.

## Why use this Contact Details Scraper?

If you've been looking for the **best email scraper** or a **free email extractor online**, you know how hit-or-miss they can be. This scraper is built on **python** and **playwright**, making it more robust than a simple **email extractor chrome extension**.

### Key Benefits:

- **Bulk Email Extraction**: Use it as a **web email extractor** to process hundreds of sites in one run.
- **Single Page Mode**: Drop in 100+ URLs and get contact details from each page — no unnecessary crawling.
- **Lead Generation**: Perfect for finding **business email scraper** targets and **email leads extractor** data.
- **Stay on Domain**: Unlike a generic **web mail extractor**, you can force this tool to stay within a specific site's boundaries.
- **High-Speed HTTP Mode**: Scrape thousands of pages in minutes using our optimized **python email scraper** engine.
- **Optional Browser Support**: Enable the **Playwright** browser for JavaScript-heavy sites that block simple scrapers.

## URL Input Formats

You can enter URLs in **any common format** — the scraper will automatically normalize them:

| You enter | Scraper uses |
| --- | --- |
| `https://www.example.com` | `https://www.example.com` |
| `http://www.example.com` | `http://www.example.com` |
| `www.example.com` | `https://www.example.com` |
| `example.com` | `https://example.com` |

No need to worry about adding `https://` or `www.` — just paste your list of domains and go.

## Two Crawling Modes

### 🔹 Single Page Mode (default: ON)

Only visits the **exact URLs** you provide. If you input 100 domains, the scraper visits exactly those 100 pages and extracts contact details from each one. No link following, no going deeper.

**Best for:** Bulk lead lists, processing a CSV of company websites, targeted outreach.

### 🔹 Deep Crawl Mode (Single Page OFF)

Follows links within each website up to the configured depth. Great for discovering contact pages, about pages, and team pages that aren't on the homepage.

**Best for:** Thorough research on a smaller number of websites.

## Use cases

- **Sales & Outreach**: Use it as an **email leads extractor** to find potential clients for your cold email campaigns.
- **Recruitment**: A powerful **linkedin email scraper github** alternative to find candidate contact info.
- **Marketing Research**: Scrape **facebook email scraper** data or **instagram email scraper** links to find influencers.
- **SEO & Content**: Find contact details for guest posting and backlink outreach.

## How to use the Contact Details Scraper

1. **Paste your URLs**: Enter your target websites in any format (full URLs, domains, with or without www).
2. **Choose Mode**: Keep "Single Page Only" ON for bulk lists, or turn it OFF to crawl deeper.
3. **Configure Proxies**: Essential for a **web page email extractor** to avoid being blocked.
4. **Run and Download**: Export your data in JSON, CSV, or Excel formats.

## Input Configuration

| Field | Type | Default | Description |
| --- | --- | --- | --- |
| `target_sites` | array | — | URLs to scrape. Accepts any format. |
| `single_page_only` | boolean | `true` | Only scrape the given URLs, no deeper crawling. |
| `page_limit` | number | `100` | Maximum pages to visit. |
| `crawl_depth` | number | `1` | Link depth (ignored in Single Page mode). |
| `stay_on_site` | boolean | `true` | Stay on same domain (ignored in Single Page mode). |
| `extract_from_iframes` | boolean | `false` | Extract from IFRAMEs (Browser mode only). |
| `use_browser` | boolean | `false` | Use Playwright for JS-heavy sites. |
| `proxyConfiguration` | object | Apify Proxy | Proxy settings. |

## Results

The actor stores its results into the default dataset associated with the actor run. You can then download the results in formats such as JSON, HTML, CSV, XML, or Excel. For each page crawled, the following contact information is extracted (examples shown):

![Sample Screenshot](https://images.apifyusercontent.com/SEW-m0S8K9rlslXxg0hoaQWTMl_V1GxTn0nbMVQXfKU/w:1800/cb:1/aHR0cHM6Ly9pLmltZ3VyLmNvbS9GdjRBNTlqLnBuZw.webp)

### Example Output

```
{
  "source_url": "https://apify.com/contact",
  "scrape_depth": 0,
  "initial_target": "https://apify.com/contact",
  "emails": [
    "hello@apify.com",
    "support@apify.com"
  ],
  "phones": [
    "+420 123 456 789"
  ],
  "facebook_links": [
    "https://www.facebook.com/apifytech"
  ],
  "twitter_links": [
    "https://x.com/apify"
  ],
  "instagram_links": [
    "https://www.instagram.com/apify"
  ],
  "linkedin_links": [
    "https://www.linkedin.com/company/apify"
  ],
  "youtube_links": [
    "https://www.youtube.com/apify"
  ],
  "tiktok_links": [
    "https://www.tiktok.com/@apifyoffice"
  ]
}
```

## FAQ

**Is this a free email extractor?**
You can run this on Apify using their free tier credits, making it a great **free email scraper** alternative for small batches.

**How does it compare to an email extractor chrome extension?**
Most **chrome email scraper** tools only scan the page you are currently viewing. This actor is a full-scale **web scraping for email addresses** tool that can crawl thousands of pages in the background.

**Can it scrape LinkedIn for emails?**
Yes, it identifies LinkedIn profiles and can be used as a **linkedin email scraper** for public profiles and company pages.

**Is it better than a bulk email extractor software?**
Since it's cloud-based on Apify, you don't need to **download email extractor** software or deal with installation. It's an **online email extractor** that works anywhere.

**Does it work as a facebook email extractor?**
Yes, it can find email addresses listed on public Facebook pages and groups, acting as a reliable **facebook group email extractor**.

## Contact & Support

If you need a custom **email scraping service** or have questions about this **email extractor tool**, feel free to reach out via the Apify platform.

![Contact Details Scraper CTA](https://images.apifyusercontent.com/6d4VjkMkgdGMkA8ceNR87ikSn-bQ-_1YW4U2tEw5BUA/w:1800/cb:1/aHR0cHM6Ly9pLmltZ3VyLmNvbS92aWg2UzNDLnBuZw.webp)