# Job Evaluation Framework

<!-- SETUP: Skill match areas and career goals are personalized by running /setup -->

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** Java, Spring Boot, Spring Security, Microservices, RESTful APIs, DDD, SOA, AWS, Docker, Kubernetes, Kafka, event-driven architecture, backend performance optimization, legacy modernization
**Moderate match areas:** Angular, React, TypeScript, Terraform, CI/CD (GitLab/Jenkins), Apache Spark, Hadoop, Scala, MongoDB/Oracle/SQL Server, mentoring/tech lead
**Weak match areas:** Non-JVM primary stacks (Go, Rust, .NET, Python-heavy roles), native mobile, ML/data-science modeling, pure frontend roles

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** Senior Java backend engineering, microservices architecture, platform/legacy modernization, banking/fintech, public-sector/government systems, healthcare (US EHR)
**Moderate:** Full-stack (Java + Angular/React), data-engineering pipelines (Spark/Kafka/Hadoop), tech lead / mentoring
**Entry-level:** Formal solutions-architect title, engineering-management (people leadership) roles

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Department disorganization, work dominated by maintenance over development, poor chemistry with leadership, culture mismatches. Check reviews, media coverage, LinkedIn connections, and network contacts for insider perspective.

### 4. Location & Logistics (Pass/Fail + Notes)
Candidate is based in **Lima, Peru (UTC-5)** and requires **100% remote** roles.
- Fully remote, any country: PASS
- Remote but restricted to a country/region that excludes LATAM: FAIL (check eligibility)
- Hybrid with mandatory office days: FAIL (deal-breaker)
- On-site / relocation required: FAIL (deal-breaker)
- Non-English working language: FAIL (deal-breaker)
- Timezone: strong overlap with the Americas; partial overlap with Europe (flag EU roles requiring full CET-hours coverage)

**US-role screening (read the posting's eligibility language carefully):**
- "Must be authorized to work in the US" / "US citizens or green-card holders only" / "W-2 only" / "on-site in [US city]" → **FAIL** (candidate is Peru-based, no US authorization).
- "Open to LATAM / Americas", "1099 contractor", "Contractor / B2B", "hire anywhere", "global/worldwide" → **PASS** (eligible - flag as a good channel).
- Comp: expect **USD**. US remote-LATAM contractor bands for senior Java+AWS typically run well above local pay; if a range is listed, compare against USD market (~$60-130k salaried / ~$35-70/hr contractor for the region) rather than local benchmarks. Clarify contractor (1099/B2B) vs employee (EOR) - it affects taxes and benefits the candidate must self-provide.

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Land a 100% remote, English-speaking Senior Java / backend engineering role with an international team
- Keep working on scalable architecture design and platform/legacy modernization
- Grow toward software architect / tech lead scope

**Motivation filter:** Evaluate not just whether you *can* do the tasks, but whether the tasks will *energize* you. Consider:
- Tasks that energize: designing scalable architectures, modernizing legacy platforms, high-performance backend work, mentoring, working in English with international teams
- Tasks that drain: pure maintenance with no modernization, on-site/rigid-schedule environments, non-English work settings
- Non-task factors: degree of autonomy over technical decisions, remote culture maturity, company values

**Life situation alignment:** Consider personal constraints:
- **Security**: currently employed (MINCETUR) - can be selective; no urgency to accept a weak fit
- **Flexibility**: remote-only is non-negotiable; UTC-5 timezone
- **Professional development**: wants growth toward architecture/tech-lead and exposure to modern cloud-native stacks

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

Interpret results relative to the baseline defined in the data file's metadata. For index-based data, higher typically means above-market compensation.

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
