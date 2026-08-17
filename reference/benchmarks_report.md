# Real Founder Case Study Data Analysis Report

> Dataset size: 5,145 business profiles · 3,233 full interviews · 26,123 tool-business relations · 4,202 category list rows
> Statistics as of: 2026-08
> Note: every number in this report is an actual computed value; each is annotated with sample size and method, and sources of bias are noted.

---

## 0. Core Conclusions (the key points first)

1. **Revenue benchmarks must be stratified by founding year, otherwise they systematically mislead.** The all-sample median monthly revenue is $45K, but projects founded in 2020 have a median of only $8.5K — a 5x difference. Evaluating a new project against all-sample numbers is like demanding a 10-year-old company's report card from someone just starting out.

2. **Team size is the strongest revenue predictor, but this is correlation, not causation.** Solo: median $15K; 2 people: $50K; 3 people: $150K. Bigger teams are a *result* of revenue, not a *cause*.

3. **The real distribution of acquisition channels differs greatly from media narratives.** SEO and paid ads tie for first (~47% mention each); podcasts rank third (42.8%) and are severely underrated; while Product Hunt (5.2%), cold email (13.9%), and ASO (3.0%) — channels hyped to the skies — are actually niche in real cases.

4. **The "indie developer myth" needs a discount.** Of the cases where a solo founder reached $100K+/month, 22.6% are actually old companies founded before 2010 whose founder counts simply weren't updated in the data.

5. **Monetization is highly convergent: subscriptions dominate.** 416 profiles with monetization data use subscriptions — 2.5x the runner-up (one-time purchases).

---

## 1. Dataset Size and Quality

| Metric | Value |
|---|---|
| Business profiles (new + old format) | 5,145 |
| Full interviews | 3,233 |
| Tool-business relations | 26,123 |
| Category list rows | 4,202 |
| **Profiles with revenue data** | **1,489 (28.9%)** |
| Median Q&A per interview | 10 questions |

### ⚠️ Key data-quality findings

- **Revenue coverage is only 28.9%**: more than 70% of profiles have no revenue figure. Every revenue conclusion therefore represents only the "29% willing to publish their revenue".
- **Revenue is self-reported/estimated**: the site explicitly states "not independently verified", and most are point-in-time historical figures, not current.
- **Sample selection bias (most important)**: this dataset only includes *profitable* businesses. A whole batch of "failed/unprofitable" projects is simply not in the data, so all revenue distributions are **systematically optimistic**.
- **Data pollution**: some "solo" profiles are actually old companies (see Section 3).

**Conclusion**: this data answers *"what do successful people look like and what methods did they use"*, not *"what is the startup success rate or my expected revenue"*.

---

## 2. Revenue Analysis

### 2.1 Overall Distribution (1,489 profiles with revenue)

| Percentile | Monthly Revenue |
|---|---|
| P10 | $2,000 |
| P25 | $10,000 |
| **P50 (median)** | **$45,000** |
| P75 | $220,000 |
| P90 | $750,000 |
| P95 | $1,730,000 |
| P99 | $8,300,000 |

- Profiles with monthly revenue ≥ $10K: 1,129; ≥ $100K: 552.
- Highly right-skewed: median $45K but P90 is already $750K — the tail is long.

### 2.2 Stratified by Founding Year (the core correction)

| Founding Year | Sample | P25 | P50 | P75 |
|---|---|---|---|---|
| 2007 | 19 | $25K | **$400K** | $916K |
| 2009 | 28 | $65K | $185K | $650K |
| 2011 | 31 | $12K | $54K | $291K |
| 2013 | 59 | $25K | $250K | $650K |
| 2015 | 114 | $8K | $42K | $150K |
| 2017 | 125 | $7K | $30K | $110K |
| 2019 | 99 | $3.2K | $12K | $55K |
| **2020** | 77 | **$1.2K** | **$8.5K** | **$25K** |

**Reading**: monotonic downward trend — the earlier the founding year, the higher the current revenue. Two effects combine:
1. **Time compounding**: older projects have more years of growth, accumulated customers, and brand.
2. **Survivorship bias**: among old projects, the ones that are "still alive and worth including" are necessarily big winners; dead old projects aren't in the sample.

**Implication for decisions**: when evaluating a new project, the right benchmark isn't "all-sample median $45K" but "median of the same-age cohort". For example, a project started in 2024 at $3K/month, against the 2020 cohort (median $8.5K), is not a failure — it's normal-to-below-average with upside room.

### 2.3 Category Revenue Matrix (category pages, 15-24 samples/category)

| Category | n | P50 | P75 |
|---|---|---|---|
| M2M (tools for creators) | 21 | $125K | $756K |
| Weird But Profitable | 21 | $125K | $280K |
| Marketplace | 24 | $117K | $375K |
| Digital Product | 17 | $100K | $200K |
| Automation | 21 | $83K | $220K |
| Problems (solving specific pains) | 23 | $83K | $250K |
| Solo Developer | 22 | $77K | $133K |
| Niche Blog | 20 | $50K | $125K |
| Productized Services | 24 | $50K | $175K |
| No-Code | 18 | $42K | $108K |
| Niche Sites | 24 | $40K | $110K |
| Freemium/Open Source | 22 | $26K | $83K |
| **GPT Wrapper** | 19 | **$16K** | $215K |
| **Micro-SaaS** | 18 | **$16K** | $51K |
| One-Page Websites | 23 | $14K | $20K |

**Three counterintuitive findings**:
1. **"Weird But Profitable" projects have a median of $125K — nearly 8x GPT wrappers.** The most-hyped AI category in market narratives is precisely one of the lowest-revenue categories.
2. **GPT Wrapper median is $16K but P75 is as high as $215K**: extreme variance; a few hits lift the tail. It's a power-law category — winner-take-all, most are also-rans.
3. **M2M (tools for creators/developers) has the highest and most stable revenue**: median $125K, P75 $756K — the best direction segment.

### 2.4 Team Size and Revenue (founded after 2012, controlling for age effects)

| Founder Count | Sample | Median Monthly Revenue | Share ≥ $50K |
|---|---|---|---|
| 1 person | 487 | $15K | 29% |
| 2 people | 251 | $50K | 50% |
| 3 people | 64 | $150K | 61% |
| 4 people | 22 | $200K | 77% |

- Solo projects are **15.4%** of the sample; all-sample median headcount is **3 people**.
- **Judgment**: team size almost monotonically pushes revenue up, but the causal direction is "revenue grew, so the team expanded". Solo projects aren't doomed to stay small — but the "solo + high revenue" cases in the data need cleaning (below).

**The "water" in solo high-income cases**: 159 solo cases reached $100K+/month, of which **36 (22.6%) were founded before 2010** (e.g., a candy company founded in 1937 recorded as "1 founder"). The true number of "contemporary indie developers doing $100K/month solo" is about a quarter smaller than the headline number.

---

## 3. Monetization Models

| Model | Occurrences |
|---|---|
| **Recurring subscriptions** | **416** |
| One-time / lifetime | 165 |
| Usage-based | 56 |
| Services / consulting | 33 |
| Upsells / add-ons | 31 |
| Sponsorship / partnerships | 25 |
| Affiliate commissions | 21 |
| Advertising revenue | 15 |
| Course / training sales | 15 |

**Reading**: subscriptions dominate absolutely (2.5x the runner-up), and often combine with "one-time purchase", "usage-based", and "upsells". **"Subscription + one-time/upsell" hybrid monetization is the mainstream model**; pure one-time purchase ranks second but far behind.

---

## 4. Acquisition Channel Analysis (key section)

### 4.1 Mention rate across full interview texts (3,131 interviews, keyword regex match)

| Channel | Mention Rate |
|---|---|
| **SEO/search** | **47.9%** |
| **Paid ads** | **46.2%** |
| **Podcasts** | **42.8%** |
| Facebook | 41.7% |
| Influencers/affiliates | 41.3% |
| Communities/forums | 38.6% |
| Email marketing | 35.4% |
| Content/Blog | 35.3% |
| Instagram | 34.1% |
| Referrals/word of mouth | 30.0% |
| YouTube | 29.3% |
| Partnerships | 25.8% |
| LinkedIn | 22.4% |
| Twitter/X | 20.1% |
| Cold email/outreach | 13.9% |
| Trade shows/offline | 12.6% |
| TikTok | 10.6% |
| Reddit | 7.1% |
| Sales team | 6.6% |
| **Product Hunt** | **5.2%** |
| PLG/freemium | 3.4% |
| App Store ASO | 3.0% |

### 4.2 "Growth channel" field of new-format profiles (more structured, 472 profiles)

SEO 135 · Word of mouth 124 · Organic social 120 · Email 61 · Partnerships 34 · LinkedIn 27 · Social ads 26 · Affiliates 24 · Reddit 24 · Communities 24 · PPC 22 · Media PR 19 · Referrals 19 · Direct sales 18

### 4.3 Three important judgments

1. **SEO and paid ads tie for first**, and two independent datasets (interview mentions + profile fields) both confirm it. They are the two most universal legs for internet entrepreneurs.
2. **Podcasts are severely underrated** (42.8%, third). This may be the most valuable counterintuitive finding of this dataset — under the "make TikToks / run newsfeed ads" narrative, podcasts' real prevalence as an acquisition channel is far higher than imagined.
3. **Overrated channels**: Product Hunt (5.2%), cold email (13.9%), ASO (3.0%), PLG (3.4%). These appear constantly in tech media but are a small share of real profitable cases.

### ⚠️ Methodology warning

**Mention rate ≠ effectiveness ≠ attribution.** A founder casually mentioning "we did SEO" and "SEO is everything in our growth" count the same in statistics — both are 1 occurrence. Therefore:
- This data answers *"what channels do successful people use"* (exploration surface),
- **cannot** answer *"which channel is most effective"* (causal surface).
- To make causal judgments, you'd need to extract specific attribution answers like "where did your first customer come from" separately (see preliminary results in 4.4).

### 4.4 "Where the first customer came from" (preliminary clustering)

Extracted from interviews that specifically ask "how did you get your first batch of customers" (sample still being expanded). Emerging patterns: came from launch-day organic traffic, content-driven traffic, word of mouth/acquaintances, social media DMs, partnerships/media, and platform cold start.

---

## 5. Tools and Growth Infrastructure

### 5.1 Most-used tools (mentioned across 5,145 profiles)

Instagram 857 · Google Drive 765 · Twitter 600 · YouTube 465 · Facebook 421 · Google Analytics 395 · Slack 361 · MailChimp 353 · QuickBooks 337 · Google Workspace 334 · PayPal 320 · LinkedIn 283 · Facebook Ads 267 · WordPress 252 · Stripe 240 · Dropbox 233 · Canva 232 · Shopify 230

### 5.2 Discriminant analysis: what high-revenue vs low-revenue businesses use (correlation, not causation)

**Tools more associated with high-revenue (≥ $50K/month) group**:
| Tool | High-Revenue | Low-Revenue | Difference |
|---|---|---|---|
| Slack | 33.4% | 16.9% | **+16.5pp** |
| Asana | 11.1% | 5.2% | +5.8pp |
| HubSpot | 13.7% | 8.1% | +5.6pp |
| Zendesk | 6.6% | 1.7% | +4.9pp |
| Klaviyo | 12.7% | 7.9% | +4.8pp |

**Tools more associated with low-revenue (< $50K/month) group**:
| Tool | High-Revenue | Low-Revenue | Difference |
|---|---|---|---|
| Canva | 11.1% | 22.6% | -11.6pp |
| PayPal | 18.0% | 29.4% | -11.4pp |
| Google Drive | 49.6% | 60.6% | -11.1pp |
| Etsy | 2.5% | 9.3% | -6.8pp |
| Wix | 1.2% | 6.9% | -5.7pp |

**Reading**: this data **cannot** be read as "use Slack and you'll earn high revenue". The real meaning: **high-revenue companies have teams, so they use collaboration/customer-support/marketing-automation tools (Slack, HubSpot, Zendesk, Klaviyo); low-revenue solo operators use self-serve/free tools (Canva, PayPal, Wix, Etsy)**. It's a proxy for "company maturity", not a causal recipe. But there's one actionable insight: **if your business starts migrating from a "solo-operator tool stack" toward a "team tool stack", it usually means you're heading toward scale.**

---

## 6. Business Types and Profiles

### 6.1 Category tags (new-format profiles)

SaaS 352 (absolute dominance) · B2B&B2C 60 · B2B 46 · B2C 24 · Education 22 · Content 11 · Marketing 9 · Health 9 · Writing 7 · Finance 7

**Reading**: the dataset is essentially a sample of "internet software/content" businesses, with SaaS dominating. Be especially careful when using it to judge physical businesses, local services, and capital-intensive industries — coverage is severely insufficient.

### 6.2 Geographic distribution

USA 700 (absolute dominance) · Canada 67 · UK 52 · Australia 42 · India 38 · Netherlands 12 · France 10 · Singapore 10 · Germany 9

**Reading**: the sample is dominated by English-speaking countries. Discount its value for non-English markets and localized acquisition.

---

## 7. Implications for Decisions (synthesis)

1. **Benchmark by age**: new projects should set revenue expectations using their "same-age cohort", not "all-sample".
2. **Direction selection uses the category matrix**: M2M, weird-but-profitable, and automation are the highest-median directions in the data; GPT wrapper is a power-law category — low median but high ceiling, suited to people who can bear high risk.
3. **Validate the two legs of acquisition first**: SEO + paid ads are the universal base; podcasts are an undervalued high-value channel; don't mythologize Product Hunt.
4. **Prioritize subscription monetization**: products that can be designed as subscription/hybrid monetization perform best in the data.
5. **Solo isn't a dead end, but look at the cases clearly**: truly solo high-income projects need to be studied separately after removing old-company pollution.
6. **Apply a "survivorship discount" to every number**: this data shows you what winners look like, but not the cost of failing.

---

## 8. Data Limitations

1. **Survivorship bias**: only profitable businesses included; no failure samples.
2. **Self-reported/estimated revenue**: unverified, and point-in-time historical.
3. **Uneven coverage**: only 28.9% have revenue; category-page samples are small (15-24).
4. **No attribution**: channel data is mention rate, not effectiveness attribution.
5. **Industry skew**: software/content/e-commerce dominate; capital-intensive and local services are under-covered.
6. **Geographic skew**: English-speaking countries dominate.
