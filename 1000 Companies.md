Proposal: How I Would Build a List of 1000 ICP-Qualified Companies in One Month

Goal

The goal is not to create a bulk dump of 1000 company names. The goal is to build a verified list of 1000 ICP-qualified companies that are genuinely relevant for DeepThought’s target segment. I would treat this as a funnel problem: start with a large raw universe, automate the first layer of filtering and scoring, then use human quality control for the final judgment.

My approach would be:

Raw Universe → Pre-filter → Automated Enrichment → AI-assisted Scoring → Human QA → Final 1000 ICP-qualified Companies

## 1. Where I Would Source the Initial Universe

To get 1000 genuinely qualified companies, I would not start with 1000 companies. I would start with around 4000–5000 companies because many will get rejected during verification.

I would source the initial universe from multiple high-quality sources:

1. Industry Association Directories

These are useful because they already contain companies from specific industries.

Examples:

* ACMA for auto components
* CII and FICCI member directories
* EEPC India for engineering exporters
* Pharmexcil for pharma exporters
* Chemexcil for chemical exporters
* IMTMA for machine tools
* AIFI and other manufacturing associations

These sources help because the companies are more likely to be real operating businesses, not random directory listings.

### 2. Government and Semi-Government Databases

These would help identify serious manufacturers and companies with stronger credibility.

Examples:

* DSIR recognized in-house R&D units
* MCA / CIN-based company data
* MSME / Udyam related databases where available
* PLI beneficiary lists
* State industrial development corporation directories like MIDC, GIDC, TSIIC, KIADB
* Export promotion council data

These sources are useful because they give stronger verification signals like R&D, registration, location, and industry classification.

3. Expo and Trade Fair Exhibitor Lists

I would use exhibitor directories from events like:

* IMTEX
* Auto Expo Components
* CPHI
* ChemTech
* PlastIndia
* India Manufacturing Show
* Electronics and EV expos

Exhibitors are useful because companies that participate in expos usually have growth intent, customer acquisition intent, and a stronger business presence.

4. Business Databases

If tools or licences are available, I would use:

* Tofler
* ZaubaCorp
* Tracxn
* Apollo
* Crunchbase
* LinkedIn Sales Navigator
* IndiaMART and TradeIndia only for discovery, not final verification

These tools would help with company age, directors, employee count, industry, revenue band, and contact information.

5. Search Engine and Website-Based Discovery

I would run targeted search strings by city, segment and signal.

Examples:

* “IATF 16949 auto components Pune”
* “AS9100 precision machining India”
* “DSIR recognized R&D engineering company”
* “CNC machining exporter India”
* “specialty chemicals manufacturer Gujarat GMP”
* “EV components manufacturer India”

This would help find strong companies that may not appear in clean directories.

2. How I Would Automate the Qualification Step

I would build a semi-automated qualification pipeline. The idea is to let automation handle repetitive checks, but not allow automation to make the final judgment without verification.

Step 1: Data Cleaning and Deduplication

First, I would clean the raw universe:

* Standardize company names
* Remove duplicates
* Normalize websites
* Remove obvious traders, dealers and distributors
* Group companies with the same website, CIN, or similar names
* Standardize city, state and segment

Tools:

* Python
* OpenRefine
* Google Sheets
* GitHub Copilot / Antigravity for automation scripts

Step 2: Website and Source Enrichment

For each company, I would collect:

* Official website
* LinkedIn company page
* Tofler/Zauba/MCA profile
* Industry association source
* Certification page if available
* Contact/location page
* Product/infrastructure page

I would use scraping tools and APIs to extract text from company websites and public pages. The extracted text would be used for first-level scoring.

Step 3: Rule-Based Pre-Filter

Before using AI, I would apply clear rules.

Auto-reject examples:

* Company is a trader, dealer, stockist, importer, distributor
* No website and no strong alternate evidence
* No clear manufacturing/service capability
* Wrong city or wrong segment
* Too large or too small for the ICP
* Dead website or outdated/no business evidence

Auto-prioritize examples:

* Has IATF 16949, AS9100, ISO 13485, GMP, DSIR, or export certification
* Shows factory/plant/manufacturing facility
* Has technical products
* Has founder/MD/director visibility
* Has recent hiring, expansion, certification or export signal

Step 4: AI-Assisted Scoring

After pre-filtering, I would use AI to score companies against the ICP criteria.

For each company, AI would receive only extracted evidence, not just the company name. The prompt would ask AI to score based on evidence and return:

* Manufacturing validity
* Location fit
* Segment fit
* Differentiation
* Decision-maker quality
* Growth signals
* Systems maturity
* Succession / leadership depth
* Confidence score
* Missing information
* Suggested verdict

I would use cheaper/faster models like Claude Haiku or Gemini Flash for first-pass scoring. For borderline cases, I would use a stronger model like Claude Sonnet or GPT-4.1/GPT-5 class models.

Important guardrail: AI would not be allowed to invent facts. If evidence is not present in the extracted sources, the output should say “not publicly verified.”

3. Quality Control Plan

Quality control is the most important part because a wrong list of 1000 names is not useful.

1. Source-Based Evidence Requirement

Every qualified company should have at least two evidence sources where possible:

* Company website as primary evidence
* LinkedIn / Tofler / Zauba / association directory / certification page as supporting evidence

For important claims like certification, location, exports, founder background, or ERP usage, I would require direct source evidence.

2. Confidence Bands

I would classify companies into four groups:

A Band: Strong ICP fit

* Multiple evidence sources
* Strong manufacturing/segment fit
* Clear differentiation and growth signals

B Band: Good ICP fit

* Clear manufacturing and segment fit
* Some missing data, but enough evidence to qualify

C Band: Borderline

* Some good signals, but missing important proof
* Sent for manual review

D Band: Reject

* Trader, wrong segment, weak evidence, no clear ICP fit

Only A and strong B companies would enter the final 1000.

3. Human QA for Borderline and High-Value Rows

I would manually review:

* All A-band companies before final inclusion
* All C-band borderline companies
* Companies with conflicting evidence
* Companies where AI found strong claims but source quality is weak
* Random sample of B-band companies for quality audit

Manual review would check:

* Is the company actually operating?
* Is the factory/location correct?
* Is the company a manufacturer or just a trader?
* Is the certification visible and relevant?
* Is the ICP score justified?
* Is the personalization hook specific and true?

4. False Positive Control

Common false positives:

* IndiaMART traders appearing as manufacturers
* Companies with only sales office in target city
* Large enterprises outside the ICP range
* Companies with generic ISO 9001 but no real differentiation
* Old or inactive websites
* AI assuming revenue/founder background without source

To control this, I would use strict rejection rules and maintain a fail list with rejection reasons.

5. Missing Data Handling

If revenue, ERP, succession, or founder background is not public, I would not guess. I would mark it as:

* Not publicly verified
* Weak evidence
* Needs manual verification

This is better than overclaiming and reducing trust.

4. Month Plan

## Week 1: Build the Raw Universe

Goal: collect 4000–5000 company names.

Activities:

* Finalize ICP definition and scoring rubric
* Select priority sectors and cities
* Scrape/download industry association directories
* Collect companies from DSIR, PLI lists, expo directories, MCA/Tofler/Zauba, LinkedIn Sales Navigator and targeted Google searches
* Standardize company names, websites, cities and segments
* Remove obvious duplicates

Expected yield:

* 4000–5000 raw companies collected
* 3000–3500 after deduplication and basic cleaning

Deliverable:

* Clean raw universe database with source tags

Week 2: Enrichment and Automated Pre-Filtering

Goal: reduce the universe to serious candidates.

Activities:

* Find company websites and LinkedIn pages
* Extract text from About, Products, Infrastructure, Certifications, Careers and Contact pages
* Add Tofler/Zauba/MCA-style verification
* Run rule-based filters to reject obvious non-ICP companies
* Identify manufacturing, location, certification and segment signals

Expected yield:

* 3000–3500 cleaned companies
* 1800–2200 companies passing basic pre-filter

Deliverable:

* Enriched company database with evidence snippets and source URLs

Week 3: AI Scoring and Borderline Review

Goal: score companies and identify likely ICP-qualified companies.

Activities:

* Run AI-assisted scoring using evidence snippets
* Score companies against ICP criteria
* Assign A/B/C/D bands
* Use stronger AI model for borderline C-band cases
* Generate missing-data flags
* Generate first version of personalization hooks

Expected yield:

* 1800–2200 pre-filtered companies
* 1200–1400 A/B companies
* 400–600 borderline companies
* 800–1000 rejects

Deliverable:

* Scored company database with confidence bands and reasoning

Week 4: Human QA and Final List

Goal: finalize 1000 genuinely ICP-qualified companies.

Activities:

* Manually review all A-band companies with high impact
* Review borderline companies needed to reach 1000
* Audit a sample of B-band companies
* Remove false positives
* Improve personalization hooks
* Validate source links
* Prepare final CSV and fail list
* Create summary report on yield, rejection reasons and confidence levels

Expected yield:

* 1200–1400 likely qualified companies
* 1000 final ICP-qualified companies
* 300–500 rejected/backup companies

Deliverable:

* Final 1000-company list
* Evidence sources
* Score bands
* Rejection/fail list
* Methodology and QA report

5. Realistic Funnel and Yield

My expected funnel would be:

* 5000 raw companies sourced
* 3500 after deduplication and basic cleaning
* 2200 after removing obvious non-ICP companies
* 1400 after AI-assisted scoring
* 1200 after source verification
* 1000 final ICP-qualified companies after human QA

This means the final yield from the raw universe would be around 20%. I would rather start with a large universe and reject aggressively than start with a small list and force-fit weak companies.

6. Tools I Would Use

* Google Sheets / Airtable for database management
* Python for scraping, cleaning, deduplication and rule-based filtering
* Claude / Gemini / GPT for AI-assisted scoring and evidence summarization
* GitHub Copilot / Antigravity for building scripts faster
* LinkedIn Sales Navigator for decision-maker and employee signals
* Tofler / Zauba / MCA-style databases for company verification
* Apollo / Clay / Clearbit-type tools for enrichment if available
* SerpAPI / Google Custom Search API for scalable search
* Firecrawl / Playwright / BeautifulSoup for website extraction
* GitHub for version control and documentation

7. Final Quality Principle

My main principle would be that AI can assist with speed, but it should not replace judgment. AI-generated claims would be treated as leads, not final evidence. A company would enter the final 1000 only if there is enough public evidence to justify why it fits the ICP.

The final output should not only answer “who are the 1000 companies?” but also “why do we believe these are the right 1000 companies?”
