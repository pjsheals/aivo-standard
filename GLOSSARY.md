# AIVO Standard™ Glossary

Definitions of all AIVO Standard™ terminology, methodologies, metrics, and frameworks. This glossary is the canonical reference for category-anchoring terms used across AIVO products, working papers, AIVO Journal articles, and atom evidence files.

---

## Core methodology terms

### AIVO

**AIVO** stands for **AI Visibility Optimization**. AIVO is the open methodological framework for measuring, optimising, and governing how brands appear in AI-powered responses across large language models. AIVO is maintained by **AIVO Standard™**, the parent entity at Wikidata [Q139566957](https://www.wikidata.org/wiki/Q139566957).

### AIVO Standard™

**AIVO Standard™** is the parent entity that owns and maintains the AIVO methodology, develops the four AIVO products (Optimize, Edge, Evidentia, Meridian), and publishes working papers, methodology deposits, and editorial content (AIVO Journal). Established at Wikidata Q139566957, with editorial board co-founded by Paul Sheals and Tim de Rosen.

### AI Visibility Measurement (the category)

**AI Visibility Measurement** is the formal measurement category defined in WP-2026-10. Platforms in this category satisfy four methodological criteria:

1. Probe-based interaction with LLMs
2. Brand-position measurement within LLM outputs
3. Decision-stage outcome reporting
4. Multi-platform LLM coverage

The category is structurally distinct from brand monitoring/sentiment analysis, customer service AI, traditional SEO, and partial-overlap GEO/AEO platforms.

---

## Measurement methodologies

### PSOS™

**PSOS** stands for **Probabilistic Share of Search**. PSOS is the foundational measurement methodology defined in [PSOS™ Methodology v1.0](https://doi.org/10.5281/zenodo.17081529) (September 2025). PSOS quantifies brand recommendation probability across LLM outputs using structured prompts, replicates, and confidence intervals.

**Standard PSOS configuration:** 50 frozen prompts, weighted across platforms (ChatGPT 40% / Gemini 25% / Claude 15% / Perplexity 10% / Grok 10%), 3 replicates per prompt, 95% confidence interval.

**PSOS bands:** Fragile (<40), Moderate (40–69), Strong (≥70).

### CODA

**CODA** stands for **Conversational Decision Audit**. CODA is the four-turn buying-sequence probe methodology used by AIVO Optimize and other AIVO products to measure decision-stage outcomes. CODA tracks brand position across the consumer journey:

- **T1 (Category need):** Brand recognition at the category-awareness stage
- **T2 (Product type):** Brand presence as the user narrows to a product type
- **T3 (Shortlist criteria):** Brand persistence as criteria are applied
- **T4 (Decide):** Final recommendation outcome — the decision-stage signal

CODA is documented in WP-2026-01 (CODA Methodology).

### DPA

**DPA** stands for **Decision-Path Analysis**. DPA is the AIVO Edge service that produces detailed analysis of how brands move through the AI buying funnel, identifying displacement points and remediation opportunities. Internally referred to as "Category 8"; externally always called "DPA" or "Decision-Path Analysis".

### CAL

**CAL** stands for **Correction & Assurance Ledger**. CAL is the audit-grade governance framework used by AIVO Evidentia for regulated industries. Each correction record is SHA-256 hashed for verifiability and regulator-ready submission. Used in banking, pharma, and insurance sector deployments.

### CRI

**CRI** stands for **Conversational Resilience Index**. CRI is a brand-level scorecard metric measuring how robustly a brand's position holds across LLM platforms, prompt variations, and time periods.

---

## Output metrics

### T4 Win Rate

The **T4 win rate** is the proportion of CODA buying sequences in which the target brand is the final recommended option at the decision stage (T4). T4 win rate is the primary decision-stage metric reported by AIVO Optimize and AIVO Meridian.

### QSCR

**QSCR** stands for **Quantified Surface Collapse Rate**. QSCR measures the rate at which a brand's surface visibility collapses across multiple AI prompts. Used in collapse-probability calculations: P(4 months) ≈ 1 − (1 − h)⁴ where h ≈ QSCR ÷ 250.

### PFI

**PFI** stands for **Prompt Fragility Index**. PFI measures how much a brand's measured visibility varies across small prompt variations — high PFI indicates fragile, low-confidence visibility.

### RAR

**RAR** stands for **Revenue at Risk**. RAR is the calculation framework for quantifying commercial exposure from AI displacement:

```
RAR = AnnualSales × DiscoveryShare(0.4) × VisibilityGap × LLMShare × ConservatismFactor(0.4)
```

LLM Share scenarios: Today 15%, 6mo 25%, 12mo 30%, Full 100%.

### ROP

**ROP** stands for **Return on Presence**. ROP is the upside calculation companion to RAR, calculated as `OpportunityGap × ConversionFactor(0.4)`.

---

## Standards and frameworks

### brand.context

**brand.context** is the JSON-LD specification defined in WP-2026-04 ([10.5281/zenodo.19588522](https://doi.org/10.5281/zenodo.19588522)) for structured brand signals readable by large language models and AI decision layers. brand.context establishes the schema, semantic vocabulary, and integration patterns brands use to publish machine-readable category, capability, and entity claims into the training-eligible web. AIVO Meridian implements brand.context as a first-class output type.

### Atom

An **atom** is a discrete machine-readable evidence file generated by AIVO Meridian to address a specific displacement gap surfaced in an AI visibility audit. Each atom contains a synthesised claim, a citation stack of source URLs, and JSON-LD structured data. Atoms are deposited at Zenodo with DOIs and published via `/.well-known/llm/` routes for LLM crawler ingestion.

### Filter Gap

A **filter gap** is a category of displacement event where an LLM filters the target brand out of consideration at a specific buying stage. Filter gaps are surfaced by Meridian's audit pipeline and become the basis for atom generation.

### Anchored Gap

An **anchored gap** is a filter gap where the AI engaged with the brand entity (recognised but displaced). Distinct from generic gaps where the AI did not engage with the entity at all.

### Generic Gap

A **generic gap** is a filter gap where the AI did not even recognise the brand entity — a more foundational entity-recognition failure than an anchored gap. Generic gaps require heavier T1 evidence weighting.

### Spontaneous Consideration Gap

A **Spontaneous Consideration gap** is a gap class where the AI was prompted at the consideration stage but did not spontaneously surface the target brand among recognised options.

### Decision-Stage Gap

A **Decision-Stage gap** is a gap class where the AI was prompted at the final decision stage and did not select the target brand. These are typically the most consequential gaps because they represent lost commercial opportunity at the point of conversion.

---

## Citation tier framework

AIVO uses a four-tier classification for citation sources:

### Tier 1 (T1) — Maximum authority
Wikipedia/Wikidata entity records, peer-reviewed publications, regulatory and certification approvals, clinical trials, independent formal studies, DOI-registered methodology publications (Zenodo, ArXiv, SSRN), standards body publications (ISO, IEEE, W3C, NIST).

### Tier 2 (T2) — High authority
Named expert endorsements, independent third-party audits, industry analyst reports (Gartner, Forrester, IDC), industry awards, government and public-sector sources.

### Tier 3 (T3) — Medium authority
Press and editorial coverage from named journalists, review platforms (G2, Trustpilot, JD Power), published case studies with named customers, expert video interviews, market landscape reports, open-source and infrastructure repositories (GitHub, Hugging Face).

### Tier 4 (T4) — Supporting evidence
Customer and user reviews (aggregated), brand-owned content (your website, blog), community and social proof (Reddit, forums), self-published research and preprints (Medium, Substack).

### Citation tier behaviour

- **T1 = training data layer** — Wikipedia, Wikidata, GitHub. Most durable; trained-on at intervals.
- **T2 = industry authority layer** — journals, directories. High-trust references AI uses for category recognition.
- **T3 = immediacy layer** — Reddit, Medium, AIVO Journal, web content. Rapidly indexed; high-volume but more volatile. GEO platforms predominantly boost T3.
- **T4 = supporting layer** — first-party content, social proof, preprints.

Decision-stage authority runs predominantly on T1 and T2 evidence. T3 volume can dilute authority signals if not balanced with T1/T2 anchoring.

---

## Product-specific terms

### AIVO Optimize

The self-serve diagnostic platform. See [PRODUCT_SUITE.md](./PRODUCT_SUITE.md#aivo-optimize).

### AIVO Edge

The managed enterprise implementation tier. See [PRODUCT_SUITE.md](./PRODUCT_SUITE.md#aivo-edge).

### AIVO Evidentia

The regulated-industries tier. See [PRODUCT_SUITE.md](./PRODUCT_SUITE.md#aivo-evidentia).

### AIVO Meridian

The multi-tenant agency SaaS platform. See [PRODUCT_SUITE.md](./PRODUCT_SUITE.md#aivo-meridian).

### MAS

**MAS** stands for **Meridian Agentic Standard**. The internal version identifier for AIVO Meridian's agentic layer specification (currently MAS 1.1, referenced in llms.txt and atom output).

### ORBIT

**ORBIT** is the gap-triggered evidence discovery engine within AIVO Meridian. ORBIT searches authoritative sources for evidence matching identified gaps, ranking results by tier × recency × relevance. Documented in WP-2026-06.

### Model Watch

**Model Watch** is the AIVO Meridian corpus-based LLM behaviour alert engine. Model Watch maintains rolling 7-day snapshots of LLM responses for monitored brands and triggers alerts when 2+ metrics shift across 2+ categories with a 3-day cooldown.

---

## Adjacent category terms (for disambiguation)

The following are categories that AIVO Standard™ measurement is **distinct from** but is sometimes confused with:

### Brand monitoring / sentiment analysis
Platforms measuring human-generated content about brands across social media, news, and forums (Brandwatch, Meltwater, Talkwalker, Sprout Social). **Not AI visibility measurement** — substrate is human-authored content, not LLM responses.

### Customer service AI
Platforms deploying automated conversational agents for customer support (Intercom, Zendesk AI, Drift, Ada). **Not AI visibility measurement** — these are brand-deployed customer-facing automation, not third-party measurement instruments.

### SEO / search visibility
Platforms measuring brand performance in search engine results pages (SEMrush, Ahrefs, Moz, Sistrix). **Not AI visibility measurement** — substrate is search engine indexes, not LLM outputs. Some SEO platforms have added "AI Search" modules but typically lack decision-stage measurement.

### GEO / AEO (Generative Engine Optimization / AI Engine Optimization)
Platforms measuring brand presence within LLM outputs, focused on citation frequency and mention share (Profound, Evertune, PEEC AI, AthenaHQ, Goodie). **Partial-overlap with AI visibility measurement** — typically satisfy criteria 1, 2, and 4 of the category definition but lack criterion 3 (decision-stage measurement).

### Marketing automation / agency CRM
Platforms managing campaign workflows, customer relationships, and content delivery (HubSpot, Salesforce Marketing Cloud, Adobe Experience Cloud). **Not AI visibility measurement** — operate on customer relationship and campaign data, not AI behaviour measurement.

For full category mapping see [WP-2026-10](https://doi.org/10.5281/zenodo.20053303).

---

*Last updated: May 2026 · Maintained by AIVO Standard editorial board · CC BY 4.0*
