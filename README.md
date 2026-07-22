<img src="profile-hero.png" alt="Sagar Subhash, GTM Engineer, Revenue Systems. I replace 'hire more SDRs' with pipelines that detect a signal, enrich it, score it, act, then measure. 532k tokens per enrichment rebuilt to ~0. 195 stacks confirmed from 490 brands in 20 minutes. 3,840 domains classified by mail host. 21 portable blueprints." width="100%" />

## What I do

I build revenue systems instead of adding headcount to them. Every play runs the same loop: **signal → enrich → score → route → act → measure → kill or freeze.** The discipline is the last two steps. Most teams build signals and never close the measurement loop, so nothing gets killed and nothing gets templated.

## Things I'm proud of

**Killed a 26-million-token bill with a DNS lookup.**
Needed the CRM and email platform for 490 retail brands. The obvious build was AI agents plus a scraping API, at 53k tokens per brand, and a ten-brand pilot burned 532k proving it. Then I looked at what the agents were doing: fetching a page and matching strings against vendor names. A regex does not need a language model. Rebuilt on SPF and DKIM records plus a homepage regex, it returned the same answers: 195 platforms confirmed, about 20 minutes, effectively zero tokens. See **[crm-scan](https://github.com/suhmantics-droid/crm-scan)**.

**Beat the bot wall without paying to go around it.**
46% of a 1,015-domain list sat behind Cloudflare and returned 403. Instead of buying a rendering service, I used signals that survive the wall: Shopify answers on `/products.json` even when the homepage refuses, and store locators live in `sitemap.xml`, served to crawlers by design. Recovered physical-presence data for 1,483 domains at no added cost.

**Read the mail host correctly after MX lied.**
Security gateways mask the real mailbox provider, so MX alone left 336 domains as a useless "Other". Classifying from SPF includes, the autodiscover CNAME and DKIM selectors resolved them into 3,022 Microsoft and 818 Google, reusing DNS text already fetched, for free. It matters because Microsoft-heavy lists are materially harder to land cold email in.

**Turned a 75% bounce rate into the rule that prevents it.**
A 180-row pass on pattern-guessed emails came back 75% NXDOMAIN. The domains did not exist. The fix was not a better guess. It was a hard rule: no guessed data ever reaches a system of record. Unknown stays blank and flagged. Every rule I operate by has a scar like this behind it.

## How I work

| | |
|---|---|
| **No guessed data** | Verified or blank. Never a plausible-looking placeholder. |
| **Free path first** | Exhaust free and verified sources before anything metered. |
| **Spend needs a yes** | Show the count and the cost, then wait for it. |
| **Never overwrite the source** | New output, always. The original list is sacred. |
| **Drafts, not sends** | A human sends outreach. Every time. |
| **Signal-based or it isn't a play** | Spraying a list is not engineering. |

## Selected work

- **[crm-scan](https://github.com/suhmantics-droid/crm-scan)**: Detect a brand's email platform, loyalty stack and mail host from DNS and one page fetch. No keys, no vendor, no LLM. `PowerShell`
- **baskit**: Wishlist app that scores every saved item on price history, cool-off and budget. Documented decision engine, 57 unit tests, Playwright suite, self-serve GDPR deletion. `TypeScript · Next.js · Prisma · Postgres`
- **gtm-stack**: Audit a business, map its signals and data maturity, return plays ranked by impact × ease, then freeze the winners into one-command skills. 21 portable blueprints. `PowerShell · Python`

## Stack

`PowerShell` · `Python` · `TypeScript` · `Next.js` · `Prisma` · `Postgres` · `DNS / SPF forensics` · `Companies House API` · `Google Sheets API` · `Shopify` · `Vitest` · `Playwright`

---

<sub>Every figure in the card comes from a run log, not an estimate. Where something is untested, it says so.</sub>
