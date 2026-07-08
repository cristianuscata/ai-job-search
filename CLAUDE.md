# Job Application Assistant for Cristian Uscata

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Cristian Uscata, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

### Identity
- **Name:** Cristian Uscata Garcia
- **Location:** Lima, Peru (UTC-5) — seeking **100% remote** roles in **English-speaking** environments
- **Phone:** (+51) 965 373 728
- **Email:** crisuscata@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/crisuscata
- **Languages:** Spanish (native), English (advanced / professional working proficiency)
- **Status:** Employed (Senior Software Engineer at MINCETUR, Peru), actively seeking remote opportunities
- **LinkedIn headline:** "Senior Software Engineer | Java · Spring Boot · Microservices · AWS · Kafka"

### Education
- **Systems Engineering degree (Ingeniero de Sistemas)** (2007-2011) - Universidad Nacional del Callao, Peru

### Professional Experience
- **Senior Software Engineer** (Feb 2025 - Present) - **MINCETUR** (Ministerio de Comercio Exterior y Turismo, Peru)
  - Backend development and platform work for public-sector systems using Java and Spring Boot
- **Senior Software Engineer** (Apr 2024 - Feb 2025) - **Comptroller General of the Republic (Contraloría General)** (Peru)
  - Led the end-to-end migration of a critical legacy system to a modern microservices architecture using Java and Spring Boot
  - Developed high-performance backend services and APIs, collaborating with the Architecture team on standards and integrations
- **Senior Software Engineer** (May 2023 - May 2024) - **Scotiabank** (LATAM)
  - Designed and optimized high-performance, low-latency APIs and backend services with Java and AWS, with secure data-exchange protocols
  - Resolved performance bottlenecks integrating complex third-party data systems; led a legacy modernization with Docker and Angular
- **Software Engineer** (May 2021 - Apr 2023) - **Qualifacts** (USA)
  - Drove migration from a monolith to a scalable microservices architecture, increasing deployment velocity and resilience
  - Built core backend services and APIs with Java, Spring Boot, and AWS, integrating Apache Kafka for high-volume real-time streaming
- **Senior Java FullStack** (Sep 2020 - May 2021) - **Zoluxiones** (Peru)
  - Developed microservices and full-stack solutions with Java, Spring, Angular, and AWS; mentored junior developers
- **Senior Software Engineer** (Mar 2018 - Sep 2020) - **SUNAT** (Peru)
  - Built integration components with IBM tools, Docker, and Kubernetes
  - Developed real-time data-processing modules with Kafka, MongoDB, Hadoop, and Scala serving 1M+ users
- **Software Engineer** (Jan 2017 - Mar 2018) - **Teamsoft SAC** (Peru)
  - Led major data migration and integration efforts; reduced operational risk by 90% through automation and standardization
- **Software Developer** (Mar 2012 - Dec 2016) - **PCM** (Peru)
  - Designed a core system automating banking processes; delivered 10+ production-ready projects

### Technical Skills
- **Primary:** Java, Spring Boot, Spring Security, Microservices, RESTful APIs, DDD, SOA
- **Cloud & DevOps:** AWS (S3, EC2, DynamoDB, RDS), Docker, Kubernetes, CI/CD (GitLab, Jenkins), Terraform, Shell Scripting
- **Event Streaming & Data:** Kafka, RabbitMQ, Event-Driven Architecture, Apache Spark, Hadoop, Scala
- **Frontend:** Angular, React, JavaScript, TypeScript
- **Databases:** MongoDB, Oracle, SQL Server
- **Domain:** Public sector / government systems, Banking & Finance, Healthcare (US EHR)
- **Methodologies:** TDD, Agile, Scrum, Mentoring

### Certifications
- None recorded yet.

### Publications
- None.

### Awards
- None recorded yet.

### Behavioral Profile
<!-- Inferred from CV; not a formal assessment. Review before relying on this. -->
- **Modernizer** - Repeatedly led legacy-to-microservices migrations and platform modernization
- **Mentor & collaborator** - Mentored junior developers; works daily with international teams
- **Strengths:** Scalable architecture design, backend performance optimization, strong analytical and communication skills
- **Growth areas:** [to refine - e.g., formal architecture certifications, public speaking]
- **Thrives in:** Remote, English-speaking teams building and modernizing scalable backend systems

### What Excites You
- Working 100% remotely in English with international teams
- Designing scalable architectures and modernizing legacy platforms

### Target Sectors
- **US companies hiring LATAM contractors** (1099/B2B) - strongest channel given English + UTC-5 overlap; via nearshore platforms (Revelo, Turing, Tecla, Toptal) and remote-first US product companies
- Fintech / Banking: remote-first Java shops, financial platforms
- Tech / SaaS / Healthtech: product companies hiring senior Java backend engineers

### Deal-breakers
- Not fully remote (on-site or hybrid-mandatory roles are a hard no)
- Non-English-speaking work environment

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
