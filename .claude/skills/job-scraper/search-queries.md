# Search Queries for Job Scraper

<!-- Configured for Cristian Uscata: 100% remote, English-speaking Senior Java / backend roles.
     Based in Lima, Peru (UTC-5). The built-in Danish portal CLIs are NOT the primary fit;
     rely on LinkedIn (remote filter) and Google site: searches over remote job boards. -->

## Candidate constraints (apply to every result)
- **100% remote only** - reject on-site and mandatory-hybrid roles.
- **English-speaking** work environment.
- **Location eligibility:** must accept LATAM / worldwide, or explicitly "Americas". Reject roles restricted to a country/region that excludes Peru (e.g. "US-only, must be authorized to work in the US", "EU residents only").
- **Timezone:** UTC-5. Strong overlap with the Americas; partial with Europe (flag EU roles that demand full CET coverage).

## Search Sites

Primary (remote-first, English):
- **linkedin.com/jobs** - use the `linkedin-search` CLI with remote + keyword filters (best signal).
- **remoteok.com** - remote-only board, strong for backend/Java.
- **weworkremotely.com** - large remote board.
- **wellfound.com** (formerly AngelList) - startups hiring remote engineers.
- **remote.co**, **workingnomads.com**, **justremote.co** - additional remote aggregators.
- **builtin.com**, **dice.com** - US tech roles (filter "Remote"; check LATAM eligibility).

Secondary (company career pages via Google):
- Direct Google `site:` searches for remote-first companies (e.g. GitLab, Toptal, Andela, Turing, Crossover, Mercado Libre, Globant, Nubank).

### LinkedIn CLI (best structured source)

The `linkedin-search` skill is country-agnostic and handles remote/US out of the box. When `bun`
is installed, prefer it over Google `site:linkedin.com` scraping:

```bash
# Fully remote senior Java, last 14 days
bun run skills/linkedin-search/cli/src/cli.ts search -q "Senior Java" -l "Remote" --remote remote --jobage 14 --format table
# US-remote Java backend
bun run skills/linkedin-search/cli/src/cli.ts search -q "Java Backend Engineer" -l "United States" --remote remote --jobage 14 --format table
```

If `bun` is not installed, fall back to WebSearch/WebFetch (as the `job-scraper` skill does).

### Nearshore / staffing platforms (strong fit for a LATAM + English + US-timezone candidate)

These place LATAM engineers into US companies in English - register directly, they publish senior
roles continuously and pre-screen for English:
- **Revelo**, **Turing**, **Tecla**, **Toptal**, **Andela**, **Lemon.io**, **CloudDevs**.
Treat these as apply-direct channels rather than scrape targets.

## Query Categories

Queries are grouped by priority. Always combine with **"remote"** and, where useful, **"Latin America" / "Americas" / "worldwide"**.

### Priority 1: Senior Java Backend / Microservices

Strongest and most desired direction.

```
site:linkedin.com/jobs "Senior Java" remote
site:linkedin.com/jobs "Java Backend Engineer" remote "Latin America"
site:linkedin.com/jobs "Backend Engineer" Java Spring remote
site:weworkremotely.com Java Spring Boot
site:remoteok.com java backend
```

### Priority 2: Event-Driven / Cloud-Native Java (domain depth)

Leverages Kafka / AWS / microservices depth.

```
site:linkedin.com/jobs "Java" Kafka microservices remote
site:linkedin.com/jobs "Java" AWS "Spring Boot" remote worldwide
site:remoteok.com java aws kafka
site:wellfound.com Java backend remote
```

### Priority 3: Tech Lead / Software Architect (Java) - adjacent pivot

Roles growing into architecture/leadership.

```
site:linkedin.com/jobs "Java Tech Lead" remote
site:linkedin.com/jobs "Software Architect" Java remote
site:linkedin.com/jobs "Staff Software Engineer" Java remote
```

### Priority 4: Broader backend / full-stack (wider net)

```
site:linkedin.com/jobs "Software Engineer" Java remote "Americas"
site:linkedin.com/jobs "Full Stack" Java Angular remote
site:remoteok.com backend engineer
site:builtin.com Java remote
```

## Location Filter

This is a **remote** search - "location" means work-authorization/timezone eligibility, not commute:
- Worldwide / global remote: PASS
- Remote - Latin America / Americas: PASS
- Remote - US (with LATAM/contractor eligibility): PASS (verify eligibility)
- Remote - US-only (must be US-authorized): FAIL
- Remote - EU/EEA residents only: FAIL
- On-site or mandatory hybrid: FAIL

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape kafka" -> Priority 2 queries + custom Kafka/streaming-specific queries
- "/scrape architect" -> Priority 3 queries + custom architecture-focused queries
